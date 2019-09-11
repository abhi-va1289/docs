---
title: "Database Services Overview"
id: "database-services"
---
---

A database is the most common form of data storage for any enterprise and apps that need to interact with these databases to define the workflow.

WaveMaker makes it easy to create web-based forms that are connected to an underlying database. To access a database from your WaveMaker application, you first create a new data model or import an existing data model into the project.

Import or creation of database within a WaveMaker app results in the generation of REST APIs. Each of the services integrated into your app is converted to a RESTful service and is consumed through their respective REST APIs. These REST APIs are exposed via the [API Designer](http://[supsystic-show-popup id=110]) and can be tested and reconfigured as per the application needs.

## Quick Start Guide

|No.| To | See |
|---|---|---|
|1.|Learn working with Databases | [Working with Databases](/learn/app-development/services/database-services/working-with-databases)|
|2.|Learn about Data Modelling|[Data Modelling](/learn/app-development/services/database-services/data-modelling)|
|3.|Learn about database schema and import modes|[Database Schema Import Modes](/learn/app-development/services/database-services/database-schema-import-modes)|
|4.|Learn about database schema|[Database Schema](/learn/app-development/services/database-services/working-database-schema)|
|5.|Learn about temporal support|[Temporal Support](/learn/app-development/services/database-services/temporal-support)|
|6.|Learn about database access services|[Database Access](/learn/app-development/services/database-access)|
|7.|Learn working with queries|[Working with Queries](/learn/app-development/services/database-services/working-with-queries)|
|8.|Learn working with stored procedures| [Working with Stored Procedures](/learn/app-development/services/database-services/working-stored-procedures)|
|9.|Learn about versioning queries procedures|[Versioning Queries Procedures](/learn/app-development/services/database-services/versioning-queries-procedures)|
|10.|Learn about blob support for queries|[Blob Support](/learn/app-development/services/database-services/blob-support-queries-procedures)|
|11.|Learn about invoking query procedures java services|[Invoking Query Procedures Java Services](/learn/app-development/services/database-services/invoking-queriesprocedures-java-services)|
|12.|Learn about database views|[Database Views](/learn/app-development/services/database-services/database-views)|
|13.|Learn about database tools|[Database Tools](/learn/app-development/services/database-tools)|
|14.|Learn about ORM artifacts (Object-relational mapping|[ORM Artifacts](/learn/app-development/services/database-services/orm-artifacts)|               


## Database Integration Process

The following figure gives an overview of the Database integration process within WaveMaker App.[![](../../../assets/db_concepts.png)](../../../assets/db_concepts.png)

1. Database Schema from an external RDBMS is imported into the app. This import includes the Data Model consisting of Tables, Columns, Relationships between tables and Constraints.
2. An ORM layer is auto-generated from the above DB Schema using Hibernate and JPA. A service layer is also auto-generated using Spring.
3. You, as an App Developer, can access the Entities from the ORM Layer, write custom queries, procedures and Java Services to extend the database functionality.
4. For each entity, query, procedure and Java service, a REST API is auto-generated using Spring-REST and Swagger.
5. Variables need to be created to interact with the REST API layer to access the database services. These variables will, in turn, be bound to Widgets to allow user interaction with the data.

## Database Workflow

When you integrate your WaveMaker app with any database, you set up the connection details and enable your app to interact with the Database. There are two forms of Database interaction:

- during design time to generate files for use within the app, and
- during runtime to access the data and work with it.

[![](../../../assets/db_integrate_process.png)](../../../assets/db_integrate_process.png) **Design Time Studio App behavior**: From the WaveMaker app:

1. when you add DB to WaveMaker app, it results in a request for metadata to the corresponding external Database, based upon the connection settings,
2. the external Database returns the metadata,
3. this returned metadata is used to generate files which will be used within the app.

:::note
The database is not replicated or copied into the Studio.
:::

### Run Time Studio App behavior
During the run mode, when database call is triggered by user interaction:

1. a database call in the form of a CRUD operation is made by the app
2. the call is forwarded to the external Database with the help of the generated files

For more understanding of the ORM generated layers, their functionality and code generated for the Database Integration, see [ORM Artifacts](/learn/app-development/services/database-services/orm-artifacts/).

## Supported Databases and Versions

WaveMaker supports the following databases and versions and the same can be used within your app.

| Database Name | Version | Driver Jar |
| --- | --- | --- |
|[![](../../../assets/MariaDB.png)](../../../assets/MariaDB.png)| 10.2 | Available in Maven Repo |
|[![mysql](../../../assets/mysql.png)](../../../assets/mysql.png)|- 5.5<br>- 5.6<br>- 5.7 | Available in Maven Repo |
|[![PostgreSQL](../../../assets/PostgreSQL.png)](../../../assets/PostgreSQL.png) PostgreSQL |- 9.4<br>- 9.5 | Available in Maven Repo |
| [![Oracle](../../../assets/Oracle.png)](../../../assets/Oracle.png) |- 11.2 <br>- 12.1 <br>- 12.2 |- [download ojdbc6.jar from here](http://www.oracle.com/technetwork/database/features/jdbc/index-091264.html) <br> - [download ojdbc7.jar from here](http://www.oracle.com/technetwork/database/features/jdbc/index-091264.html) <br> - [download ojdbc8.jar from here](http://www.oracle.com/technetwork/database/features/jdbc/index-091264.html)|
| [![SQLServer](../../../assets/SQLServer.png)](../../../assets/SQLServer.png) SQL Server | 2014 <br> Azure SQL Database [Connect to Azure](/learn/how-tos/connect-azure-sql-server/) | [Steps to Download sqljdbc4.2.jar](/learn/app-development/services/database-services/download-jdbc-driver-jar/) <br> (you can use JDBC driver 4.2, 6.0, 6.1 or 6.2, ensure that you import  **sqljdbc42.jar** or any Java ver 8 compatible jar file) |
| [![DB2](../../../assets/DB2.png)](../../../assets/DB2.png) |- 10.1 <br> - 11.1| [db2jcc4.jar](http://www-01.ibm.com/support/docview.wss?uid=swg21363866) |
| [![HSQLDB](../../../assets/HSQLDB.png)](../../../assets/HSQLDB.png) |- 2.3.3 <br> - 2.3.4| Available in Maven Repo |
