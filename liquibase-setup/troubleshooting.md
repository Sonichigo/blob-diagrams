# First Time Common Errors

## 1. `searchPath` parameter

While the below works fine with liquibase with Spring boot, same throw error with db-devops
```yaml
databaseChangeLog:
  - include:
      file: db/changelog/changes/001-create-users-table.yaml
  - include:
      file: db/changelog/changes/002-add-sample-data.yaml
```

> access the files mentioned above [here](https://gitlab.com/Sonichigo/demo-db/-/tree/main/src/main/resources/db/changelog/changes)

this is due to how liquibase handles the filepath - relative path and absolute path.

### error message:

<img width="1728" alt="Screenshot 2025-04-30 at 5 07 29 PM" src="https://github.com/user-attachments/assets/98cea87e-e54b-4b56-a86e-0defe7e99233" />

best and simplest way is to use `sql` folder and and add it as the path.

### how to solve:
- step 1. convert the schema file from YAML to SQL files.
- step 2. modify the `changelog.yml` :

```yml
databaseChangeLog:
  - includeAll:
      path: sql
```

> access the above `sql` file [here](https://gitlab.com/Sonichigo/demo-db/-/tree/main/src/main/resources/db/changelog/sql)

<img width="1302" alt="Screenshot 2025-05-05 at 11 49 45 AM" src="https://github.com/user-attachments/assets/53b98b46-882d-4a68-8c53-0a43b7a1cb3d" />

## 2. JDBC connection timeout

Default Timeout is set to `10m`, but running on first seems to throw the timeout error due the network latency sometimes.

### error message:
<img width="1597" alt="Screenshot 2025-04-30 at 12 55 59 PM" src="https://github.com/user-attachments/assets/e003f5e4-4036-4d95-ad53-c9c7c61b1884" />

### how to solve:

there are two way to resolve the error:
- a. increase timeout duration.
- b. simply re-run the pipeline.

<img width="1321" alt="Screenshot 2025-04-30 at 2 13 15 PM" src="https://github.com/user-attachments/assets/95bb3cb7-5c76-4816-afa2-f569d34e51c8" />


## 3. Issue with harness delegate (with kubernetes manifest)

Harness Delegate can be used on LocalMachine(Minikube/Kind) , AWS, Azure, GCP. By default the delegate pod is stuck in Pending state due to: - `0/1 nodes are available: 1 Insufficient memory.` this is becaue the delegate pod requests 2Gi of memory and 500m of CPU, as declared here:

```yaml
resources:
          limits:
            memory: "2048Mi"
          requests:
            cpu: "0.5"
            memory: "2048Mi"
```

but while running local clusters (minikube/kind) the docker desktop has maximum only 1959MB memory.

### how to solve:

update the resource request to something more conservative i.e. 512Mi–1Gi. 

```yaml
resources:
  limits:
    memory: "2048Mi"
  requests:
    cpu: "0.5"
    memory: "1024Mi"
```
