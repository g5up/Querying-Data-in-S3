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

Navigate to Services menu in the top, then type Athena and select Workgroups.
<br />
<p align="center">
<br/>
<img src="https://imgur.com/WzJ1sBK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>

Choose the type of engine : Select Athena SQL
<br/>
Upgrade Query engine: Select Automatic
<br />
<p align="center">
<br/>
<img src="https://imgur.com/JQTQMHa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
