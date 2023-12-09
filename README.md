# Querying-Data-in-S3 with SQL

<h1>Querying Data in S3 with Amazon Athena with SQL</h1>


<h2>Description</h2>
Consider a retail company managing a vast repository of customer transaction data in S3. With this project, the company can seamlessly query and analyze purchasing patterns, identify popular products, and optimize inventory management. The SQL querying capabilities of Amazon Athena provide actionable insights, enabling the company to make informed decisions for business growth.Company ABC is deploying a new web application that helps customers to upload files to S3 Bucket. As a part of the infrastructure, the Administrator needs to be notified via Email whenever an object is put into their S3 bucket. 


h2>Languages and Utilities Used</h2>
<br />

- <b>Athean</b> 
- <b>SQL</b>
- <b>Amazon S3</b>
- <b>Amazon Glue</b> 

<h2>Environments Used </h2>
- <b>AWS</b> 
<h2>Architecture Diagram:</h2>
<p align="center">
<br/>
<img src="https://imgur.com/bIs9YQw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
<h1>Step by Step:</h1>
<h2>Task 1: Sign in to AWS Management Console:</h2>
 Once Signed In to the AWS Management Console, make the default AWS Region as US East (N. Virginia) us-east-1.
<p align="center">
<br/>
<img src="https://imgur.com/BmKYyNr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />


<h2>Task 2: Setup workgroup:</h2>
The workgroup allows users to define specific configurations and settings for their query execution environment. By creating a workgroup, users can customize parameters such as query result location, encryption settings, and query execution options.<br />
<br />
Make sure you are in the N.Virginia Region.
<br />
<p align="center">
<br/>
<img src="https://imgur.com/XP1TTCa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

Navigate to Services menu in the top left corner, then type Athena and select Workgroups.
<br />
<p align="center">
<br/>
<img src="https://imgur.com/WzJ1sBK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>


Provide details to create a workgroup:

Workgroup Name: Enter G5UPWorkgroup

Description: Enter WWorkgroup for G5UP Athena group
<br />
<p align="center">
<br/>
<img src="https://imgur.com/ZGZDGK3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>

Choose the type of engine : Select Athena SQL
<br/>
Upgrade Query engine: Select Automatic
<br />
<p align="center">
<br/>
<img src="https://imgur.com/JQTQMHa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
 
Query result configuration: Select the S3 bucket adiop-cloud by clicking on Browse S3 button.

<br />
<p align="center">
<br/>
<img src="https://imgur.com/Fm0NRjM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
 
Leave other settings as default

Click on the Create Workgroup button.
<br />
<p align="center">
<br/>
<img src="https://imgur.com/qcB63cY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>

<h2>Task 3: Create a database in Glue:</h2>
AWS Glue is a fully managed extract, transform, and load (ETL) service. The database serves as a container for organizing and storing metadata related to the data tables used in Athena. It enables efficient data cataloging and data management for the subsequent tasks..<br />
<br />
Make sure you are in the N.Virginia Region.
<br />
Navigate to Services menu at the top, then click on AWS Glue in the Analytics section.
<br />
<p align="center">
<br/>
<img src="https://imgur.com/kl2miWg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>

In the left sidebar, Under Data catalog, Click on Databases 

Click on the Add database button
<br />
<p align="center">
<br/>
<img src="https://imgur.com/ou4640U.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/> 

In the pop-up menu, enter the database name as g5upgluedb and click on the Create database button.(all lower case)
<br />
<p align="center">
<br/>
<img src="https://imgur.com/hCYA1FM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/> 

The database is now created.
<br />
<p align="center">
<br/>
<img src="https://imgur.com/2agoQBq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/> 

<h2>Task 3: Task 4: Create a table in Glue:</h2>
AWS Glue represents the structure and schema of the data stored in the S3 bucket
<br/>
In the left sidebar, Under Data catalog, Click on Tables.
<br/><p align="center"><br/><img src="https://imgur.com/ZXgiuQa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

To create a table, click on the Add table button 
<br/><p align="center"><br/><img src="https://imgur.com/Ev3yThZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

In the Set table properties section, do the following:

Enter the Table name as g5up-sample-table

Database: select g5upgluedb

<br/><p align="center"><br/><img src="https://imgur.com/CckBWVj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

In the Data store section, do the following:

Select the type of source: S3 (default)

Data location is specified in: my account (default)

Include path: Select the S3 bucket name starting with adiop-cloud

Select Classification as CSV

Choose delimiter as Comma: ,

Click on the Next button.

<br/><p align="center"><br/><img src="https://imgur.com/PbZnP2T.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

In the Schema section, we will add 2 columns by clicking on Add button.

<br/><p align="center"><br/><img src="https://imgur.com/BilRY5o.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

Column # : 1

Column name: Enter Expense_Type and Column Type: Select string

Click on the Save button below.

<br/><p align="center"><br/><img src="https://imgur.com/8icoLH7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

Click on the Add button again.

Column #: 2

Column name: Enter Expense_Category and Column Type: Select string

Click on the Save button below.

<br/><p align="center"><br/><img src="https://imgur.com/o084GJW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

Click Next

<br/><p align="center"><br/><img src="https://imgur.com/mhm8L6d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

Review the configuration of the table and click on the Create button. The table is now created.

<br/><p align="center"><br/><img src="https://imgur.com/3yvql10.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

Table should be listed below if done properly

<br/><p align="center"><br/><img src="https://imgur.com/n27dgz6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

<h2>Task 3: Task 5: Query table in Athena:</h2>

SQL query capabilities of Amazon Athena to interact with and analyze the data stored in the created table. By executing SQL statements in the Athena Query Editor.




























 
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
