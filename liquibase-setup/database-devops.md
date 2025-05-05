# QuickStart Guide
Welcome to the Harness Database DevOps (DB DevOps) onboarding guide. This guide introduces you to the robust capabilities of Harness DB DevOps, providing a streamlined approach to managing and securing your database operations. By integrating database changes into your CI/CD pipelines, Harness DB DevOps bridges the gap between application delivery and database management, enabling faster and more reliable software releases.
[![Diagram](https://mermaid.ink/img/pako:eNqdVdtu2zgQ_RWCQRYp1nZjyfJF2AaQKNcJ6rRFHOzD2vtAS2OZCE2qJLWJGwToP_QP-yWlKFuo3W6ARk_izJxDnjMc6RGnMgMc4hWX9-maKoNu44VYCIROT9GEGXQDhdTMSLVFbTSTpUoBzQzNAZ3FvIRXVakul7mixRpNrm7nC3wIW-B_qxqEMqYgNUwKt0UVieZT9qlkS6oBkTUVOXCZ_7VUry_S_aqz3XD0J9Kf-I5Fmy0HFKEV4zw8SVMIVquWNkreQXji-6NRs2zfs8ysQ694qJAgskbXJVUCtEYJ_Peh0FYXuXpNEkSkWLH8_9VdRjfvx7OZVdgQxDuOZ0TG3XlNXCpw2rqdCjdL17ChLuC5wJXQhgrrrq0WlkOqHWXszRNYMQHoIyuAVy_3zKxRVBR8u-Oxh4biwKG4-9sWNVDvBVC7X7t9YbH7Q6M3by7Qu-Hs2Px35RKsewY0IrzUBlTVgASNHyAtnXNnEwUgDr23RNb3n7G_MH56U0dId_5RZqG7xYRLa9sf9pZBeidLswMRry65KS2suYrO2H2FX1cQybnlR1OZ64qHAxXloeNk73jWgyyjjW3ekA56wbOOE-_lUP8FUFI3i3h7G1yziN8sq2wSH7fulqocDEqooc6oNnrLBOV2BgoutxsQphoeA7_sYBLbBh4xPDM2yfxsX-WG5NuXr0l0G8XRbIxm5HJ8HR2HyWX0fjKefpi4xKuD3iS_bdKPuomSWrcbJVMm7nSVipxtu89CFUgaH3EL54plOFxRrqGFN6A2tFrjR4Tqky2wsaNrPQjta-1G6zD1N1WMLjnYz0v4WGfq7JKmd7mSpT2jQ5-s3GMJfqxK6xGJpcqqQXGF5-45Kqy-KfaCy-OiuuZpIZ6coIKKf6Tc4NCo0kqy--frRmBZZLbzCaPWo00TVdZGUMSe1OCw74-6jsWqwQ847Pp-ZzAKgmF_GPiDvuf7LbzFYdDvdIeD85HNBP7IC_q9pxb-7DY-7wyC4XkwCPxef9TrD7r9Foas-s1c178x9zd7-g4fkCSB?type=png)](https://mermaid.live/edit#pako:eNqdVdtu2zgQ_RWCQRYp1nZjyfJF2AaQKNcJ6rRFHOzD2vtAS2OZCE2qJLWJGwToP_QP-yWlKFuo3W6ARk_izJxDnjMc6RGnMgMc4hWX9-maKoNu44VYCIROT9GEGXQDhdTMSLVFbTSTpUoBzQzNAZ3FvIRXVakul7mixRpNrm7nC3wIW-B_qxqEMqYgNUwKt0UVieZT9qlkS6oBkTUVOXCZ_7VUry_S_aqz3XD0J9Kf-I5Fmy0HFKEV4zw8SVMIVquWNkreQXji-6NRs2zfs8ysQ694qJAgskbXJVUCtEYJ_Peh0FYXuXpNEkSkWLH8_9VdRjfvx7OZVdgQxDuOZ0TG3XlNXCpw2rqdCjdL17ChLuC5wJXQhgrrrq0WlkOqHWXszRNYMQHoIyuAVy_3zKxRVBR8u-Oxh4biwKG4-9sWNVDvBVC7X7t9YbH7Q6M3by7Qu-Hs2Px35RKsewY0IrzUBlTVgASNHyAtnXNnEwUgDr23RNb3n7G_MH56U0dId_5RZqG7xYRLa9sf9pZBeidLswMRry65KS2suYrO2H2FX1cQybnlR1OZ64qHAxXloeNk73jWgyyjjW3ekA56wbOOE-_lUP8FUFI3i3h7G1yziN8sq2wSH7fulqocDEqooc6oNnrLBOV2BgoutxsQphoeA7_sYBLbBh4xPDM2yfxsX-WG5NuXr0l0G8XRbIxm5HJ8HR2HyWX0fjKefpi4xKuD3iS_bdKPuomSWrcbJVMm7nSVipxtu89CFUgaH3EL54plOFxRrqGFN6A2tFrjR4Tqky2wsaNrPQjta-1G6zD1N1WMLjnYz0v4WGfq7JKmd7mSpT2jQ5-s3GMJfqxK6xGJpcqqQXGF5-45Kqy-KfaCy-OiuuZpIZ6coIKKf6Tc4NCo0kqy--frRmBZZLbzCaPWo00TVdZGUMSe1OCw74-6jsWqwQ847Pp-ZzAKgmF_GPiDvuf7LbzFYdDvdIeD85HNBP7IC_q9pxb-7DY-7wyC4XkwCPxef9TrD7r9Foas-s1c178x9zd7-g4fkCSB)

## Prerequisites

Before beginning the walkthroughs in this guide, ensure you have:


| Item | Details / Link |
| ---- | ---- |
|Harness account | Database DevOps Feature flag enabled (see “Enabling Feature Flags”) |
| Kubernetes cluster | Cluster ≥ v1.18, Harness Delegate installed (link to Delegate setup guide)|
| Database credentials | JDBC‑compatible database; user with DDL/DML privileges |



## Setting Database DevOps
### 1. Create a Liquibase changelog

> **Note**: If you already use liquibase, you can skip to the section `Configuring Your DB Schema`.

1. Create Git Repo to store your DB schema files.
2. Under repo, create folder sql/ and add ordered *.sql files
3. Add changelog.yml at root with:

```yaml
databaseChangeLog:
  - includeAll:
      path: sql
```
> **Tip**: Use semantic file names ("V1__init.sql", "V2__add_table.sql").

### 2. Configure your Database Schema 
1. On the module picker, choose `DB DevOps` in your harness account.
<img width="752" alt="Screenshot 2025-05-05 at 3 08 28 PM" src="https://github.com/user-attachments/assets/a533066a-6f70-4fae-9364-d6ec24bf477e" />

2. In the left hand nav, choose `DB Schemas` and Click `Add New DB Schema`.
<img width="1720" alt="Screenshot 2025-05-05 at 3 15 02 PM" src="https://github.com/user-attachments/assets/1672312f-d440-4bd3-b944-2aec1acfb90a" />

  - **Name** - A Schema Name to identify the database configuration.
  - **Connector** - Code Repositories hosted on either GitHub, Azure, GitLab, BitBucket or etc..

### 3. Connect with Database Instance
Before we can deploy our Database Schema, we need to connect a database instance to which we can deploy it. Here’s how:

1. Under "DB Instances", click  "Add New DB Instance".
2. Select main (or your environment branch).
3. Click New Connector and Enter Name, JDBC URL & credentials, select the harness delegate, then Save and Finish. Learn more [here](https://developer.harness.io/docs/database-devops/use-database-devops/set-up-connectors/)
4. Click Add Database Instance.

### 4. Configure your Deployment Pipeline
A deployment pipeline deploys your database changes when it runs. In addition to deploying your database, it can also deploy application changes, and have other logic such as requiring a manual approval. Here are some steps on how to create a simple pipeline that deploys a schema change to a database instance anytime it changes in git:

1. Under Pipelines, Click "Create a Pipeline".
2. Click on Add Stage and Choose "Custom stage".
3. Choose Add step group and Turn on "Enable Containerized Stage".
4. Choose the Kubernetes cluster you'd like to run on.
5. Click Add Step and Choose the DBSchemaApply step under DB DevOps.
6. For the step name, enter ‘Apply Database Schema’.
<img width="599" alt="image" src="https://github.com/user-attachments/assets/ab6d86be-d9ed-4e5d-a5f2-c7d471cd0f9c" />

  - **Name**: Name of the step, by default the name is "DBSchemaApply_1". 
  - **Timeout**: The timeout limit is the maximum allowable time a stage or pipeline can run.
  - **Select DB Schema**: The DB Schema we created on Step 2.
  - **Select DB Instance**: The Instance we created on Step 3.
  - **Tag (Optional)**: You can add custom tags to each deployment. In case it is left empty, harness will add the tag during the deployment.
7. Click "Apply Changes" and Save the Pipeline.
8. Now, click on "Run" and wait for your pipeline to complete.
<img width="1604" alt="image" src="https://github.com/user-attachments/assets/57c8e999-eb77-4939-90f7-5e3f74ca32e8" />

