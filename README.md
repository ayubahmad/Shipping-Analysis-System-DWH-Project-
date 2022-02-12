




***Term Project***

***Subject:***		*Data Warehouse*

***Topic:**		Shipping Analysis System*

***Submitted to***

Professor Nadeem Zafar

***Submitted by***

*Ayub Ahmad		115-BSCS-18*

*Samia Saif		079-BSCS-18*

***Section:**		A*




***Computer Science Department,***

***GC University Lahore***


# *Table of Contents*
[Acknowledgement	4](#_Toc95059741)

[Executive summary	5](#_Toc95059742)

[1.	Introduction	6](#_Toc95059743)

[2.	Analysis	6](#_Toc95059744)

[2.1. Source System Analysis (SSA)	6](#_Toc95059745)

[2.2. Source Entity Analysis	7](#_Toc95059746)

[2.	7](#_Toc95059747)

[4.	8](#_Toc95059748)

[6.	8](#_Toc95059749)

[7.	8](#_Toc95059750)

[1.	9](#_Toc95059751)

[2.	9](#_Toc95059752)

[3.	Data Quality Metrics	10](#_Toc95059753)

[4.	Requirements	11](#_Toc95059754)

[4.1.	Data Warehouse Business Requirements (WBR)	11](#_Toc95059755)

[4.2.	Data Warehouse Data Requirements (WDR)	11](#_Toc95059756)

[4.3.	Data Warehouse Query Requirements (WQR)	12](#_Toc95059757)

[4.4.	Data Warehouse Technical Requirements (WTR)	12](#_Toc95059758)

[5.	Architecture	13](#_Toc95059759)

[5.1. Technical Architecture	13](#_Toc95059760)

[6.	Data Models	13](#_Toc95059761)

[6.1. Data Modeling Standards	13](#_Toc95059762)

[6.2. Information Packages	13](#_Toc95059763)

[6.3. Conceptual Model	14](#_Toc95059764)

[6.4. Logical Model	15](#_Toc95059765)

[7.	Analysis Snapshots	15](#_Toc95059766)









**List of Figures**

- *Data Models*
- *Conceptual Model*
- *Logical Model*
- *Information Packages*


**List of Tables**

- *Items*
- *Staff*
- *Branches*
- *City*
- *Region*
- *Salary*
- *Shipping*












#
# ***Acknowledgement***
Achievement of this task would have been impossible without the help and constant guidance of Sir Nadeem Zafar. It is due to his efforts that we are able to complete this project. We would like to thank him. We are obliged to him for the valuable information provided by them in their respective fields. We are grateful for his cooperation during the period of our assignment.


























# ***Executive summary***
A multi-National Shipping Management System named “SMS” was established in 2015 and it is developing its business by leaps and bounds. Today SMS has more than 100 branches all over the world. In order to critically watch the wheels of business turn, “SMS” needs a data warehouse. The function of “SMS” system is to take shipping order and ship the desired item through employee from the nearest branch. Owner of SMS wants to analyze the salary of his staff; and shipping in rupee cost and units shipped. The customer visits the website, browses through brands and select the item he wants to be shipped. A staff member, who actually is the employee of the SMS takes the order and ship the item. SMS keeps first name, last name, phone number, email and CNIC of staff member for their record. SMS has setup the hierarchy as: one city has many branches and there is more than one city in one region. Internally the website keeps more detail of the item than shown to the customer. The detail includes item name, brand, and type. City includes city name and region assigned. Region includes region name. The hotel wants to analyze and generate daily, monthly, quarterly and yearly report showing how much salary was given and how much items were shipped by the staff with cost.

















1. ## **Introduction**
The task assigned to us was making a system to perform an analysis on. We have constructed a Shipping Management System to perform our analysis on aspects of SMS:

- Salary 
- Shipping
- Items
- Staff
- Branches

The above-mentioned aspects belong both to the dimensional as well as factual data. The analysis being performed considers relationships amongst various dimensions and the resultant factors such as orders, regions, etc. There are one to many relationships among different dimensions that are examined while performing the analysis.

1. ## **Analysis**
The data for our analysis system has been collected and assembled by the members themselves. Several dimensions have been created using the collected data which are interconnected with respect to their conformed dimension. There are over thousand records that have been manually assembled by the team members and from these records, information packages, dimension tables and fact tables have been created. We will discuss them in detail in the following document.

### **2.1. Source System Analysis (SSA)**
This software package is developed using visual programming and Microsoft SQL to store the database.

- **Operating System:** Windows 
- **Database:** Microsoft SQL Server 
- **System Type:** 64-bit OS
- **Processor:** Intel(R) Core(TM) m3-7Y30 CPU @ 1.00GHz 1.61GHz
- **Hard Disk:** 40GB
- **RAM:** 4GB or more
- **Available:** 24 hours




### **2.2. Source Entity Analysis**
**Tables:**

***Dimension Tables***

**1.**

|**Branch**|**Data Type**|
| :-: | :-: |
|<p></p><p>Branch ID</p><p>Branch Name</p><p>City ID</p>|<p></p><p>int</p><p>varchar</p><p>int</p>|

## **2.**

|**Item**|**Data Type**|
| :-: | :-: |
|<p></p><p>Item ID</p><p>Item Name</p><p>Brand</p><p>Type</p>|<p></p><p>int</p><p>varchar</p><p>varchar</p><p>varchar</p>|
`	`**3.**

|**Staff**|**Data Type**|
| :-: | :-: |
|<p>Staff ID</p><p>First Name</p><p>Last Name</p><p>Email</p><p>CNIC</p><p>Phone Number</p>|<p>int</p><p>varchar</p><p>varchar</p><p>varchar</p><p>varchar</p><p>varchar</p>|
##
## **4.**

|**City**|**Data Type**|
| :-: | :-: |
|<p></p><p>City ID</p><p>City Name</p><p>Region ID</p>|<p></p><p>int</p><p>varchar</p><p>int</p>|
## **6.**

|**Region**|**Data Type**|
| :-: | :-: |
|<p></p><p>Region ID</p><p>Region Name</p>|<p></p><p>int</p><p>varchar</p>|
## **7.**

|**Time**|**Data Type**|
| :-: | :-: |
|<p>PK Date</p><p>Date Name</p><p>Year</p><p>Year Name</p><p>Quarter</p><p>Quarter Name</p><p>Month</p><p>Month Name</p><p>Day of Year</p><p>Day of Year Name</p><p>Day of Quarter</p><p>Day of Quarter Name</p><p>Day of Month</p><p>Day of Month Name</p><p>Month of Year</p><p>Month of Year Name</p><p>Month of Quarter</p><p>Month of Quarter Name</p><p>Quarter of Year</p><p>Quarter of Year Name</p><p></p>|<p>datetime</p><p>nvarchar</p><p>datetime</p><p>nvarchar</p><p>datetime</p><p>nvarchar</p><p>datetime</p><p>nvarchar</p><p>int</p><p>nvarchar</p><p>int</p><p>nvarchar</p><p>int</p><p>nvarchar</p><p>int</p><p>nvarchar</p><p>int</p><p>nvarchar</p><p>int</p><p>nvarchar</p>|
***Factual Tables***
## **1.**

|**Shipping**|**Data Type**|
| :-: | :-: |
|<p></p><p>Item ID</p><p>Time ID</p><p>Staff ID</p><p>Rupee Cost</p><p>Units Shipped</p>|<p></p><p>int</p><p>int</p><p>int</p><p>float</p><p>int</p>|
## **2.**

|**Salary**|**Data Type**|
| :-: | :-: |
|<p></p><p>Branch ID</p><p>Time ID</p><p>Staff ID</p><p>Salary</p>|<p></p><p>int</p><p>int</p><p>int</p><p>float</p>|










1. ## **Data Quality Metrics**
Evaluating data quality and moving to a proactive capability requires thoughtful data quality metrics. Improving data fitness requires using short, repeatable processes and a thoughtful set of metrics to measure progress.

` `Below is a list of important measurement areas:

- Availability
- Accuracy
- Integrity
- Completeness
- Frequency

**Availability** includes the delivery or receipt of the data by the service level agreement stipulated time of day.

**Accuracy** refers to the content of the data matching or reflecting the actual transaction (e.g. wire transfer) or status change (e.g. customer change of address) as they occur in the course of business events.  Absent source documents (e.g. change of address orders from customers) accuracy must be measured using either sampling and interviews or independent confirmation techniques.

**Integrity** refers to the data content matching the rules and structural requirements imposed in the data model or other formal management form. Examples include numeric only values in a numeric field, no nulls in key or other required fields add unique entries for key fields.

**Completeness** refers to the data values having a full entry in each record.  It also refers to record level entries having all required fields populated.  The use of default or repeating values is easily identified in the profiling results. Even though they meet the basic requirement of completeness you may wish to measure their presence differently. Completeness may also refer to the total of records provided, for example, if a set of records represent all active customers or all new customers in the last 30 days.

**Frequency** refers to the timing of process cycles or other production activities that deliver or make the data available for use.  This is a time-based unit of measure typically expressed in hours or days.






1. ## **Requirements**
Different dimensions have different requirements. On the basis of the data and dimensions we have made, every aspect has a different requirement based on its nature.

Following are the dimensions and requirements of these dimensions of our system.
1. ### **Data Warehouse Business Requirements (WBR)**
Our business requirements include:

- Completion time span—Two months
- Can hold large amount of archived data
- Can obtain reports on a daily basis, weekly, monthly and annually
- Can perform analysis on Salary
- Can perform analysis on the basis of Shipping
  1. ### **Data Warehouse Data Requirements (WDR)**
***Staff***
The requirements for staff members are listed below:

- ID
- First Name
- Last Name 
- CNIC
- Email Address
- Phone

***Shipping***
The requirements for shipping are listed below

- Item ID
- Staff ID
- Rupee Cost
- Units Shipped

***Salary***
The requirements for salary are listed below:

- Staff ID
- Branch ID
- Salary

***Items***

- Item ID
- Item Name
- Brand
- Type

***Branches***
The requirements for branches are listed below:

- Branch ID
- Branch Name
- Branch City

***City***
The requirements for city are listed below:

- City ID
- City Name

***Region***
The requirements for region are listed below:

- Region ID
- Region Name
  1. ### **Data Warehouse Query Requirements (WQR)**
Based on our system, analysis can be performed to find solution too many queries within our business perspective. From item to staff to branch, our system will be able to resolve a reasonable number of queries that the user has. Some of the queries that our system would have the ability to resolve have been listed below:

- Units shifts by the staff
- Salaries given to the staff of different branches
- Items of amount shipped during a time
  1. ### **Data Warehouse Technical Requirements (WTR)**
Technical requirements with respect to business are listed below: 

- System should provide fast results
- System should provide accurate results 
- System should be capable of complex queries 
- System should be designed so that it plays an effective role in decision making i.e. provide all types of analysis that is in need of business 








1. ## **Architecture**
### **5.1. Technical Architecture**
In this system, we have used 2-Level Architecture. The tools we have used include:

- SQL Server 2021 (Database Engine & Analysis Service)
- Microsoft Visual Studio 2013 (Business Intelligence)
- Flat Files (Notepad)
1. ## **Data Models**
Following is a graphical representation of various models and components that have been created from the system that we have constructed.

### **6.1. Data Modeling Standards**
The three levels of data modeling,

- Conceptual Data Model
- Logical Data Model
- Physical Data Model

We will discuss them in detail in the following document.

**6.2. Information Packages**

***Salary Information Package***

|**BRANCH**|**STAFF**|**TIME**|
| :-: | :-: | :-: |
|branchId|staffId|PK\_Date |
|bracnchName|First Name|Daily|
|cityId|Last Name|Month |
||CNIC|Year|
||Email|Quarter |
||Phone||
|Fact: Salary|




***Shipping Information Package***

|**ITEM**|**STAFF**|**TIME**|
| :-: | :-: | :-: |
|itemId|staffId|PK\_Date |
|itemName|First Name|Daily|
|Brand|Last Name|Month |
|Type|CNIC|Year|
||Email|Quarter |
||Phone||
|Fact: Rupee Cost, Units Shipped|

### **6.3. Conceptual Model**




### **6.4. Logical Model**


1. ## **Analysis Snapshots**




























1. ## **References**
- The Data Warehouse Toolkit by **Ralph Kimball**
- Data Warehousing Fundamentals by **Paulraj Ponniah**



19

