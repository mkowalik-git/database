# 🪞 Working with Dual Data Access Patterns

## Introduction

JSON Relational Duality Views enable applications to access the same data as either JSON documents or relational tables. This dual access pattern is perfect for migration scenarios where some parts of the application can be modernized while others continue using familiar JSON interfaces.

Estimated Time: -- minutes

### Objectives

- Insert and update data through both relational tables and JSON views
- Understand data synchronization between access patterns
- Explore the flexibility of dual data access
- Learn best practices for mixed access patterns

## Task 1: Insert Data via Relational Table

```sql
<copy>
-- Add new coffee item directly to relational table
insert into COFFEE_ROOT values (
  13, 
  systimestamp, 
  'Ristretto', 
  'Short', 
  4, 
  0, 
  '{"color":"dark"}'
);
</copy>
```

## Task 2: Update Data via JSON View

```sql
<copy>
-- Update existing document through duality view
update COFFEE_DUALITY cd 
set cd.data = json_transform(cd.data, set '$.color' = 'light') 
where cd.data."_id" = 3;
</copy>
```

## Task 3: Insert via JSON View

```sql
<copy>
-- Insert new document via duality view
insert into COFFEE_DUALITY (data) values (
  '{ "_id" : 14, "item" : "Cafe Creme", "price" : 0, "size": "Short",
     "quantity" : 0, "date" : "2025-01-01T10:00:00Z", "color":"light" }'
);
</copy>
```

## Task 4: Verify Data Synchronization

```sql
<copy>
-- Verify data appears in both views
select * from COFFEE_ROOT order by _id;
select json_serialize(data pretty) from COFFEE_DUALITY order by json_value(data, '$._id');
</copy>
```

### Expected Outcomes

- Understanding of bidirectional data synchronization
- Practical experience with dual access patterns
- Confidence in mixed development approaches

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
