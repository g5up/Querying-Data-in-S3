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

<h2>Task 4: Create a table in Glue:</h2>
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

<h2>Task 5: Query table in Athena:</h2>

SQL query capabilities of Amazon Athena to interact with and analyze the data stored in the created table. By executing SQL statements in the Athena Query Editor.

Make sure you are in the N.Virginia Region.

Navigate to Services menu in the top, then click on Athena in the Analytics section.

In the left sidebar, Click on Query Editor

Switch the G5UPWorkgroup at the top right.

<br/><p align="center"><br/><img src="https://imgur.com/04aZb9P.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

To get the results of all expenses types under expense_category of Food, paste the following SQL statement into the query editor

SELECT * FROM "g5upgluedb"."g5up-sample-table" WHERE expense_category = 'Food';

<br/><p align="center"><br/><img src="https://imgur.com/a4Hrfb1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

Note: To execute the queries through the keyboard directly, use the shortcut Ctrl + Enter (For windows) or Tab + Enter (For Mac)

You can play around with some queries like:

If you want to list all distinct expense categories Foood, Shipping,, Transportation and Office, along with their respective counts, you can type the following code

SELECT expense_category, COUNT(DISTINCT expense_type) AS expense_type_count
FROM "g5upgluedb"."g5up-sample-table"
WHERE expense_category IN ('Food', 'Shipping', 'Transportation', 'Office')
GROUP BY expense_category;

<br/><p align="center"><br/><img src="https://imgur.com/vlZgdtn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><br/> 

If you want to get a total number of rows present by running the following SQL statement:

SELECT count(*) FROM "g5upgluedb"."g5up-sample-table";

<h2>Do You Know?:</h2>
Athena's serverless nature allows users to analyze data stored in S3 without the need for any infrastructure provisioning or management. This means that users can focus solely on querying and analyzing their data without worrying about setting up and maintaining servers or clusters. The pay-per-query pricing model of Amazon Athena ensures cost efficiency, as users are only charged for the actual queries they run. This flexibility and cost-effectiveness make Amazon Athena a powerful and convenient tool for data analysis tasks in AWS.

<h2>Recommendations:</h2>
<ol>
  <li><b>Optimize Data Storage:</b> Consider optimizing the storage format and structure of your data in Amazon S3, as it can impact query performance. Formats like Parquet or ORC may provide better performance than CSV, especially for large datasets.</li>

  <li><b>Partitioning Data:</b> If your dataset is large, consider partitioning it based on certain columns. This can significantly improve query performance by allowing Athena to skip irrelevant data when querying.</li>

  <li><b>Cost Management:</b> Keep an eye on costs, especially if your queries involve large amounts of data. Athena follows a pay-per-query pricing model, so optimizing your queries and managing the data structure can help control costs.</li>

  <li><b>Regular Data Catalog Updates:</b> Ensure that the AWS Glue Data Catalog is regularly updated to reflect changes in your S3 data. This ensures that Athena has accurate metadata for efficient query execution.</li>

  <li><b>Query Performance Tuning:</b> Monitor and analyze query performance regularly. Identify and optimize frequently executed or resource-intensive queries to improve overall system efficiency.</li>
</ol>

<h2>Lessons Learned:</h2>
<ol>
  <li><b>Understanding Workgroups:</b> Creating a separate workgroup (G5UPWorkgroup) provides a way to customize query execution environments. Understanding workgroup settings, such as result location and encryption, is essential for efficient query execution.</li>

  <li><b>Database and Table Creation in Glue:</b> The process of creating databases and tables in AWS Glue is crucial for organizing and managing metadata. Consistent naming conventions and accurate configurations facilitate seamless interaction with Athena.</li>

  <li><b>Column and Data Type Considerations:</b> When creating tables in Glue, careful consideration of column names and data types is essential. This directly impacts the accuracy of queries and the overall effectiveness of data analysis.</li>

  <li><b>Utilizing Athena Query Editor:</b> The Athena Query Editor provides a convenient way to interactively run SQL queries. Understanding its features, shortcuts, and how to switch between workgroups is beneficial for a smooth querying experience.</li>

  <li><b>Exploring Querying Capabilities:</b> Experimenting with various SQL queries helps in exploring the full querying capabilities of Amazon Athena. Understanding how to filter, group, and aggregate data provides valuable insights for data analysis.</li>
</ol>


















 
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
