# 🗃️ Creating JSON Collection Views and Query Optimization

## Introduction

JSON Collection Views provide a powerful way to create filtered, business-focused views of your JSON data. They enable security, simplify complex queries, and provide logical data organization for different application needs.

Estimated Lab Time: -- minutes

### Objectives

- Create filtered JSON collection views
- Implement business logic through views
- Optimize query performance
- Understand view-based security patterns

## Task 1: Create Filtered Collection View

```sql
<copy>
-- Create view for budget-friendly coffee options
create or replace JSON Collection View CHEAP_COFFEE as 
select * from COFFEE_DUALITY cd 
where cd.data.price <= 5;
</copy>
```

## Task 2: Query the Collection View

```sql
<copy>
-- Query the filtered view
select json_serialize(data pretty) from CHEAP_COFFEE;

-- Count items in view
select count(*) from CHEAP_COFFEE;
</copy>
```

## Task 3: Create Complex Views

```sql
<copy>
-- Create view for premium coffee items
create or replace JSON Collection View PREMIUM_COFFEE as 
select * from COFFEE_DUALITY cd 
where cd.data.price > 10;

-- Create view for items with nested CoffeeItems
create or replace JSON Collection View BUNDLED_COFFEE as 
select * from COFFEE_DUALITY cd 
where json_exists(cd.data, '$.CoffeeItems');
</copy>
```

### Expected Outcomes

- Functional filtered views for different business needs
- Understanding of view-based data organization
- Practical experience with JSON query optimization


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
