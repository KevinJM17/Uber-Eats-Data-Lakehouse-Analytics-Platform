# Uber Eats Data Lakehouse & Analytics Platform

## ADF Linked Services

### 1. `LS_SQL_Src`

Linked service used by **Azure Data Factory (ADF)** to connect to the source **Azure SQL Database**.

The ADF managed identity must be granted access to the Azure SQL Database.

Run the following SQL commands in the query editor:

```sql
CREATE USER [ubereatadf-kevin] FROM EXTERNAL PROVIDER;

ALTER ROLE [db_datareader]
ADD MEMBER [ubereatadf-kevin];
```

> **Note:** Replace `ubereatadf-kevin` with the name of your Azure Data Factory managed identity.

---

### 2. `LS_ADLS_Sink`

Linked service used by **Azure Data Factory (ADF)** to connect to the sink **Azure Data Lake Storage (ADLS)** account.

To grant ADF access:

1. Open the **ADLS Storage Account** in the Azure Portal.
2. Navigate to **Access Control (IAM)**.
3. Click **Add role assignment**.
4. Assign the **Storage Blob Data Contributor** role.
5. Select the **managed identity** associated with your Azure Data Factory instance.
