# Querying-Data-in-S3

<h1>Querying Data in S3 with Amazon Athena</h1>


<h2>Description</h2>
Consider a retail company managing a vast repository of customer transaction data in S3. With this project, the company can seamlessly query and analyze purchasing patterns, identify popular products, and optimize inventory management. The SQL querying capabilities of Amazon Athena provide actionable insights, enabling the company to make informed decisions for business growth.Company ABC is deploying a new web application that helps customers to upload files to S3 Bucket. As a part of the infrastructure, the Administrator needs to be notified via Email whenever an object is put into their S3 bucket. 


h2>Languages and Utilities Used</h2>
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
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
