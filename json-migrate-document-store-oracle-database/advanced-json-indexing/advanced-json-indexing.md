# ⏭️ Advanced JSON Indexing Strategies

## Introduction

Effective indexing is crucial for JSON query performance. Oracle Database 23ai provides multiple indexing strategies specifically designed for JSON data, including multi-value indexes for arrays, partial indexes for conditional queries, and search indexes for full-text search.

Estimated Lab Time: -- minutes

### Objectives

- Create specialized indexes for JSON data access patterns
- Implement multi-value indexes for array elements
- Build partial indexes for filtered queries
- Understand search indexes for full-text capabilities


## Task 1: Create JSON Search Index

```sql
<copy>
-- Path subsetting index for common query patterns
CREATE SEARCH INDEX coffee_search_idx ON COFFEE (data) 
PARAMETERS ('SYNC (ON COMMIT) SEARCH_ON TEXT 
            INCLUDE ($.size, $.CoffeeItems.quantity) VALUE(VARCHAR2, NUMBER) 
            INCLUDE ($.price) VALUE(NUMBER)');
</copy>
```

## Task 2: Implement Partial Index

```sql
<copy>
-- Partial index for low-cost items
CREATE INDEX coffee_price_idx ON COFFEE(
  CASE WHEN JSON_VALUE(data, '$.price') <= 5 
       THEN JSON_VALUE(data, '$.price' RETURNING NUMBER ERROR ON ERROR) 
       ELSE NULL END
);
</copy>
```

## Task 3: Create Multi-value Indexes

```sql
<copy>
-- Multi-value indexes for nested array elements
CREATE MULTIVALUE INDEX MVI_Code ON COFFEE c (
  c.data.CoffeeItems.Details.Code.numberOnly()
);

CREATE MULTIVALUE INDEX MVI_Unit_Price ON COFFEE c (
  c.data.CoffeeItems.Details.UnitPrice.numberOnly()
);
</copy>
```

## Task 4: Test Index Performance

```sql
<copy>
-- Query using indexed paths
SELECT json_serialize(data pretty) 
FROM COFFEE 
WHERE json_value(data, '$.price') <= 5;

-- Query using multi-value index
SELECT json_serialize(data pretty) 
FROM COFFEE c 
WHERE c.data.CoffeeItems.Details.Code = 28995;
</copy>
```

### Expected Outcomes

- Optimized query performance for JSON data
- Understanding of specialized JSON indexing techniques
- Practical experience with index creation and testing

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
