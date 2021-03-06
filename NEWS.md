DatabaseConnector 2.4.1
=======================

Changes:

1. Adding ability to set the path where the DLL is located for Windows Integrated Authentication for SQL Server and PDW.

Bugfixes:

1. No longer dropping '#' prefix for temp table names when inserting data for RedShift.

DatabaseConnector 2.4.0
=======================

Changes:

1. Adding runAsBatch argument to executeSql and renderTranslateExecuteSql functions to allow running as a batch (often faster).

Bugfixes:

1. Not adding '#' prefix when performing insert into RedShift.

2. Disabling autocommit when sending updates to RedShift to prevent errors with new JDBC driver.

3. Preventing 'FeatureNotSupportedError' from terminating query on platforms that do no support autocommit.

4. Fixing some errors related to insertTable when determining correct field type for columns.

DatabaseConnector 2.3.0
=======================

Changes:

1. Adding support for SQLite through RSQLite (mainly for demonstration and testing)

2. Adding convenience functions renderTranslateExecuteSql, renderTranslateQuerySql, and renderTranslateQuerySql.ffdf

3. Dropping Starschema BigQuery driver (in favor of newer Simba driver)

4. Added support for inserting BIGINTs (large integers stored as numeric in R)

5. Applying CTAS hack to improve insertion performance for RedShift (was already used for PDW)

Bugfixes:

1. Executing multi-statement SQL where one statement returns results no longer causes error.


DatabaseConnector 2.2.1
=======================

Changes:

1. Now supporting proper insertion and extraction of DATETIME fields

Bugfixes:

1. Closing output stream when writing to zip file to avoid orphan file locks
2. Fixed the problem that Jar file is not detected when setting JDBC driver manually

DatabaseConnector 2.2.0
=======================

Changes:

1. Checking number of inserted rows after bulk upload, throwing error if not correct
2. Added convenience function for cross-platform zipping of files and folders


DatabaseConnector 2.1.4
=======================

Changes:

1. Faster inserts by building batches in Java instead of R


DatabaseConnector 2.1.3
=======================

Changes:

1. Updated to DBI specification 1.0
2. Defaulting connect arguments to NULL to prevent missing argument warnings in RStudio

Bugfixes:

1. Now generating unique display names for RStudio's Connections tab to prevent problems when opening two connections to the same server.

DatabaseConnector 2.1.2
=======================

Changes: initial submission to CRAN
