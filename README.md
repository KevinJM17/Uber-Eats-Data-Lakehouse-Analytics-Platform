# Uber Eats Data Lakehouse & Analytics Platform

ADF Linked Services
- LS_SQL_Src
  Linked service that allows ADF to connect to the source (Azure SQL database). Give authorization to SQL database to allow ADF access by granting role.
  CREATE USER [ubereatadf-kevin] FROM EXTERNAL PROVIDER;

  ALTER ROLE [db_datareader]
  ADD MEMBER [ubereatadf-kevin];
- LS_ADLS_Sink
  Linked service that allows ADF to connect to the sink (ADLS). Go to the storage account and add the STORAGE BLOB DATA CONTRIBUTOR role.
