# Understanding Data Modeling in Power BI: Joins, Relationships, and Schemas Explained

## Introduction
Data modeling is a key step when working with Power BI. Before creating dashboards, data must be structured in a clear and logical way. A good data model improves performance, reduces errors, and makes analysis easier.

This article explains data modeling, SQL joins, Power BI relationships, schemas, and how to create them step-by-step.

---

## What is Data Modeling?
Data modeling is the process of organizing data into tables and defining how those tables are connected.

It involves:
- Structuring tables  
- Defining keys  
- Creating relationships  

### Why it matters
- Faster reports  
- Accurate calculations  
- Better organization  

---

## SQL Joins (With Diagrams)

Assume two tables:
- Customers (ID, Name)  
- Orders (ID, CustomerID)  

---

### 1. INNER JOIN
Returns only matching records.

**Example:** Customers who made orders  

![INNER JOIN Diagram](https://www.programiz.com/sites/tutorial2program/files/inner-join-in-sql.png)

---

### 2. LEFT JOIN
Returns all records from the left table and matching ones from the right.

**Example:** All customers, including those without orders  

![LEFT JOIN Diagram](https://www.programiz.com/sites/tutorial2program/files/left-join-in-sql.png)

---

### 3. RIGHT JOIN
Returns all records from the right table and matching ones from the left.

**Example:** All orders, even if customer details are missing  

![RIGHT JOIN Diagram](https://www.programiz.com/sites/tutorial2program/files/right-join-in-sql.png)

---

### 4. FULL OUTER JOIN
Returns all records from both tables.

**Example:** All customers and all orders  

![FULL OUTER JOIN Diagram](https://learn.microsoft.com/en-us/power-query/media/merge-queries-full-outer/full-outer-join-operation.png)

---

### 5. LEFT ANTI JOIN
Returns rows from the left table with no match.

**Example:** Customers who never ordered  

![LEFT ANTI JOIN Diagram](https://learn.microsoft.com/en-us/power-query/media/merge-queries-left-anti/left-anti-join-operation.png)

---

### 6. RIGHT ANTI JOIN
Returns rows from the right table with no match.

**Example:** Orders without customers  

![RIGHT ANTI JOIN Diagram](https://i0.wp.com/blog.jooq.org/wp-content/uploads/2015/10/wiki-anti-join.png?resize=519,149&ssl=1)

---

## Creating Joins in Power BI (Step-by-Step)

1. Open Power BI Desktop  
2. Click **Transform Data**  
3. Select a table  
4. Click **Merge Queries**  
5. Select the second table  
6. Choose matching columns  
7. Select join type (Inner, Left, Right, Full, Anti)  
8. Click **OK**  
9. Expand columns
10. * Merge Queries window showing join type selection 
![Merge Queries window showing join type selection](https://www.sqlshack.com/wp-content/uploads/2020/04/verify-join-type.png)

---

## Power BI Relationships

Relationships connect tables without merging them.

### Types of Relationships

**1. One-to-Many (1:M)**  
One record relates to many  
**Example:** One customer → many orders  

**2. Many-to-Many (M:M)**  
Both tables contain repeated values  

**3. One-to-One (1:1)**  
Each record matches exactly one  

---

### Active vs Inactive
- Active: Used automatically  
- Inactive: Used only when specified  

---

### Cardinality
Defines how tables relate:
- One-to-many  
- Many-to-many  

---

### Cross Filter Direction
- Single direction  
- Both directions  

---

## Creating Relationships in Power BI (Step-by-Step)

### Method 1: Model View
1. Open **Model View**  
2. Drag a column from one table to another  

* showing connected tables (1:M relationship)  
![1:MRelationships](https://learn.microsoft.com/en-us/power-bi/guidance/media/relationships-many-to-many/bank-account-customer-model-related-tables-1.svg)
---

### Method 2: Manage Relationships
1. Click **Manage Relationships**  
2. Click **New**  
3. Select tables  
4. Select columns  
5. Set cardinality  
6. Choose cross-filter direction  
7. Click **OK**  

* Relationship configuration dialog box
![ Relationship configuration dialog box](https://howto.caspio.com/wp-content/uploads/2023/04/relationship_join_type.png)

---

## Joins vs Relationships

| Joins | Relationships |
|------|--------------|
| Combine tables | Link tables |
| Power Query | Model View |
| Used in data preparation | Used in analysis |

---

## Fact vs Dimension Tables

### Fact Table
Contains numeric data used for analysis.

Examples:
- Sales  
- Revenue  

---

### Dimension Table
Contains descriptive data.

Examples:
- Customer  
- Product  
- Date  

---

## Data Schemas

### Star Schema
- One central fact table  
- Connected dimension tables  

**Use case:** Best for Power BI performance  

![STAR SCHEMA Diagram](https://dotnettutorials.net/wp-content/uploads/2020/01/word-image-195.png)

---

### Snowflake Schema
- Dimension tables split into smaller related tables  

**Use case:** Complex datasets  

![SNOWFLAKE SCHEMA Diagram](https://media.datacamp.com/cms/ad_4nxcythn-86q_c4ey8jj_4uqlcszyxj6ihckm-4kajmbkaqu1fdnleti2ma43fwva6ed9urbjfo4-oi7ckr1ap5iurgizdumsthlszrzhotcqnmqoxzyjj5nzlyk4npififk-oru1ua.png)

---

### Flat Table (DLAT)
- All data in one table  

**Use case:** Small or simple datasets  

![FLAT TABLE Diagram](https://cdn.prod.website-files.com/65d605a3b4417479c154329f/65f024b6b51652f355e8fc55_Table-16-Zebra-Stripes-Chaos.svg)

---

## Role-Playing Dimensions
A single dimension used multiple times.

**Example:**
- Order Date  
- Ship Date  
- Delivery Date  

---

## Common Data Modeling Issues
- Duplicate keys  
- Incorrect relationships  
- Many-to-many confusion  
- Circular relationships  
- Poor performance  

---

## Best Practices
- Use star schema  
- Keep models simple  
- Avoid unnecessary joins  
- Validate relationships  

---

## Conclusion
Data modeling is the foundation of Power BI. Understanding joins, relationships, and schemas helps build accurate, efficient, and scalable reports.
