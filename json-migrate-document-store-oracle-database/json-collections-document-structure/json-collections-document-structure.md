# 🛠️ Setting Up JSON Collections and Understanding Document Structure

## Introduction

Coffee shop POS systems typically store transaction data as JSON documents, with each document representing a menu item, order, or inventory record. These documents often have varying schemas - some items may have additional fields like old_price, brand, or complex nested arrays for bundled products.

Estimated Time: -- minutes

### Objectives

In this lab, you will:

* Create and populate JSON collection tables in Oracle Autonomous Database
* Understand JSON document structure and schema flexibility
* Explore Oracle's native JSON data type and storage format (OSON)
* Learn about JSON collection table features and constraints

## Task 1: Environment Setup

1. Access your Oracle Autonomous Database instance
* <🚧🦺 UNDER CONSTRUCTION>
2. Connect to Database Actions SQL interface
* <🚧🦺 UNDER CONSTRUCTION>
3. Verify JSON functionality is enabled
* <🚧🦺 UNDER CONSTRUCTION>


## Task 2: Create JSON Collections Table


  ```sql
    <copy>
    -- Clean up any existing objects
    DROP TABLE IF EXISTS COFFEE PURGE;
    DROP TABLE IF EXISTS COFFEE_ROOT PURGE;
    DROP VIEW IF EXISTS COFFEE_DUALITY;

    -- Create JSON collection table
    CREATE JSON COLLECTION TABLE IF NOT EXISTS COFFEE;

    -- Verify table structure
    DESC COFFEE;
    </copy>
  ```

## Task 3: Populate with Coffee Shop Data

Execute the provided INSERT statements to populate the COFFEE collection with 12 diverse coffee products:

 ```sql
    <copy>
   -- Insert coffee products with varying schemas

  insert into COFFEE values ('{ "_id" : 1, "item" : "Espresso", "price" : 5, "size": "Short", "quantity" : 22, "date" : "2024-01-15T08:00:00Z",
   "CoffeeItems" : [{ "Details"     : { "Description" : "Italian Espresso",
                                "UnitPrice"   : 5,
                                "Code"        : 28995},
                   "Quantity" : 9.0 },
                 { "Details"     : { "Description" : "Finnish Espresso",
                                "UnitPrice"   : 5,
                                "Code"        : 28996},
                   "Quantity" : 11.0 } ] }');
  insert into COFFEE values ('{ "_id" : 2, "item" : "Cappuccino", "price" : 6, "size": "Short","quantity" : 12, "date" : "2024-08-16T09:00:00Z" }');
  insert into COFFEE values ('{ "_id" : 3, "item" : "Latte", "price" : 10, "size": "Grande","quantity" : 25, "date" : "2024-02-14T09:05:00Z" }');
  insert into COFFEE values ('{ "_id" : 4, "item" : "Mocha", "price" : 8,"size": "Tall", "quantity" : 11, "date" : "2024-02-17T08:00:00Z" }');
  insert into COFFEE values ('{ "_id" : 5, "item" : "Americano", "price" : 1, "size": "Grande","quantity" : 12, "date" : "2024-02-18T21:06:00Z" }');
  insert into COFFEE values ('{ "_id" : 6, "item" : "Cortado", "price" : 7, "size": "Tall","quantity" : 20, "date" : "2024-02-20T10:07:00Z" }');
  insert into COFFEE values ('{ "_id" : 7, "item" : "Macchiato", "price" : 9,"size": "Tall", "quantity" : 30, "date" : "2024-02-21T10:08:00Z" }');
  insert into COFFEE values ('{ "_id" : 8, "item" : "Turkish Coffee", "price" : 20, "old_price" : 15, "size": "Short","quantity" : 21, "date" : "2024-02-22T14:09:00Z" }');
  insert into COFFEE values ('{ "_id" : 9, "item" : "Ice Coffee", "price" : 15, "size": "Grande","quantity" : 17, "date" : "2024-08-23T14:09:00Z" }');
  insert into COFFEE values ('{ "_id" : 10, "item" : "Dirty Chai", "price" : 12, "size": "Tall","quantity" : 15, "date" : "2024-08-25T14:09:00Z" }');
  insert into COFFEE values ('{ "_id" : 11, "item" : "Decaf", "price" : 4, "size": "Normal", "quantity" : 2, "date" : "2024-01-16T11:01:00Z", "brand":"Relax" }');
  insert into COFFEE values ('{ "_id" : 12, "item" : "Finlandia", "price" : 50, "old_price" : 40, "size": "Grande","quantity" : 107, "date" : "2025-01-10T10:00:00Z",
   "CoffeeItems" : [{ "Details"     : { "Description" : "Coffee from Helsinki",
                                "UnitPrice"   : 50,
                                "Code"        : 35801},
                   "Quantity" : 50.0 },
                 { "Details"     : { "Description" : "Coffee from Tampere",
                                "UnitPrice"   : 50,
                                "Code"        : 35802},
                   "Quantity" : 40.0 } ,
                 { "Details"     : { "Description" : "Coffee from Turku",
                                "UnitPrice"   : 50,
                                "Code"        : 35803},
                   "Quantity" : 17.0 }] }');

commit work;
select * from COFFEE;

    </copy>
  ```

## Task 4: Explore Document Variations

* Query documents to observe schema differences
 
 <🚧🦺 UNDER CONSTRUCTION> 
* Identify documents with nested arrays (CoffeeItems)

 <🚧🦺 UNDER CONSTRUCTION>
* Note optional fields like old_price and brand

 <🚧🦺 UNDER CONSTRUCTION>
* Understand how Oracle handles schema flexibility

 <🚧🦺 UNDER CONSTRUCTION>

**Expected Outcomes**

* JSON collection table created and populated with 12 coffee products
* Understanding of document schema variations
* Familiarity with Oracle's JSON storage capabilities

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
