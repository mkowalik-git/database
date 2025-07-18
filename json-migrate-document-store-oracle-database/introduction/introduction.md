# Introduction

Modern applications increasingly rely on document stores for their flexibility and ease of development. However, as businesses grow, they often encounter limitations with NoSQL databases including transaction consistency, analytical query performance, and data integrity constraints. Oracle Database 23ai bridges this gap with revolutionary JSON Relational Duality Views, allowing applications to work with data as both JSON documents and relational tables simultaneously.

This workshop uses a coffee shop inventory and sales system as a practical example, demonstrating how to migrate JSON document collections to Oracle Database while maintaining application compatibility and gaining enterprise-grade features.
Key Technologies Covered

* **Oracle Autonomous Database**: Cloud-native database platform
* **JSON Collection Tables**: Native JSON document storage
* **JSON Relational Duality Views**: Bidirectional JSON-relational data access
* **JSON-to-Duality Migrator**: Automated migration tool
* **Advanced JSON Indexing**: Multi-value, partial, and search indexes
* **Oracle REST Data Services (ORDS)**: RESTful API generation

## About this Workshop

This hands-on workshop demonstrates how to migrate document-oriented data from any NoSQL document store to Oracle Database using Oracle Database 23ai's advanced JSON capabilities, JSON Relational Duality Views, and the JSON-to-Duality Migrator.

### _**Real-World Problem: Coffee Shop POS System Migration**_

**The Challenge**

GlobalBean Coffee operates a chain of coffee shops across multiple locations, each running independent point-of-sale (POS) systems that store transaction data in MongoDB collections. The company faces several critical challenges:

**Business Pain Points**:

* **Data Silos**: Each coffee shop's MongoDB instance operates independently, making cross-location analytics impossible
* **Limited Query Capabilities**: Complex analytical queries across multiple collections are slow and resource-intensive
* **Transaction Limitations**: MongoDB's limited ACID transaction support creates data consistency issues during peak hours
* **Scalability Concerns**: Growing transaction volumes strain the existing MongoDB infrastructure
* **Compliance Requirements**: New financial regulations require stronger data integrity and audit trails

**Technical Challenges**:

* **Schema Evolution**: Adding new fields to documents requires application-level schema management
* **Data Consistency**: Lack of referential integrity between related collections leads to orphaned records
* **Performance Issues**: Large aggregation queries for business intelligence reports cause system slowdowns
* **Backup Complexity**: Maintaining consistent backups across multiple MongoDB instances is operationally challenging

### **The Solution**

Oracle Database 23ai with JSON Relational Duality Views provides the perfect solution, offering:

* **Best of Both Worlds**: Maintain JSON document flexibility while gaining relational data integrity
* **Seamless Migration**: Use the JSON-to-Duality Migrator to automatically generate optimized relational schemas
* **Enhanced Performance**: Leverage Oracle's advanced indexing and query optimization
* **Enterprise Features**: Built-in backup, security, and compliance capabilities


Estimated Workshop Time: 3 - 4 hours (This estimate is for the entire workshop - it is the sum of the estimates provided for each of the labs included in the workshop.)

*You may add an option video, using this format: [](youtube:YouTube video id)*

  [](youtube:zNKxJjkq0Pw)

### Objectives

Through this workshop, you will learn to:

* **Migrate Document Store Data**: Transform a MongoDB-style coffee shop inventory system into Oracle Database 23ai using automated migration tools
* **Implemented Dual Access Patterns**: Create applications that can access the same data as both JSON documents and relational tables
* **Optimized Performance**: Implement advanced indexing strategies specifically designed for JSON data access patterns
* **Built Modern APIs**: Generate RESTful APIs that enable integration with contemporary applications

### Prerequisites

This lab assumes you have:
* An Oracle account
* Basic SQL knowledge and access to Oracle Autonomous Database

## Learn More

* [JSON Developer's Guide](https://docs.oracle.com/en/database/oracle/oracle-database/23/adjsn/)
* [JSON Relational Duality Views](https://docs.oracle.com/en/database/oracle/oracle-database/23/jsnvu/)
* [Oracle REST Data Services](https://docs.oracle.com/en/database/oracle/oracle-rest-data-services/)

This workshop represents just the beginning of your journey with Oracle Database 23ai. The platform's rich feature set and comprehensive capabilities provide a solid foundation for building modern, scalable applications that can grow with your business needs.

**Training and Certification**

* Oracle Database 23ai New Features Training
* Oracle Cloud Infrastructure Autonomous Database Certification
* JSON and NoSQL Database Migration Best Practices

## Acknowledgements
* **Author** - Matt Kowalik, Senior Product Manager
* **Contributors** -  Julian Dontcheff, Principal Product Manager
* **Last Updated By/Date** - Matt Kowalik, July 2025
