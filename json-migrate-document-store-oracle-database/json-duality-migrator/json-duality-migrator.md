# 🤖 Automated Migration Using JSON-to-Duality Migrator

## Introduction

The JSON-to-Duality Migrator is Oracle's intelligent tool that analyzes collections of JSON documents and automatically generates an optimized relational schema along with duality views. This tool examines field frequency, data types, and relationships to create the most efficient database structure.

  ![Oracle JSON](images/json_oracle.png)

Estimated Lab Time: -- minutes

### Objectives

* Use Oracle's JSON-to-Duality Migrator to analyze document structure
* Automatically generate optimized relational schema
* Create JSON Relational Duality Views for bidirectional data access
* Understand the migration process and generated objects

## Task 1: Run the JSON-to-Duality Migrator

```sql
<copy>
DECLARE
  schema_sql clob;
BEGIN
  schema_sql := dbms_json_duality.infer_and_generate_schema(
    json('{"tableNames"     : [ "COFFEE" ],
          "useFlexFields"   : true,
          "updatability"    : true,
          "minFieldFrequency"  : 20,
          "minTypeFrequency"  : 20,
          "sourceSchema"    : "ADMIN"}'));
  
  dbms_output.put_line('Generated DDL Script:');
  dbms_output.put_line(schema_sql);
  
  -- Execute the generated DDL
  execute immediate schema_sql;
  
  -- Import data from JSON collection to duality view
  dbms_json_duality.import_all(table_name => 'COFFEE', view_name => 'COFFEE_DUALITY');
END;
/
</copy>
```

## Task 2: Analyze Generated Objects

```sql
<copy>
-- Examine newly created objects
select * from user_objects 
where created > sysdate-1/240 
order by object_type desc;

-- Inspect the root table structure
desc COFFEE_ROOT;
</copy>
```

## Task 3: Understand the Generated Schema

1. Examine the `COFFEE_ROOT` table structure
 
 <🚧🦺 UNDER CONSTRUCTION> 
2. Understand the purpose of the `ORA$COFFEE_DUALITY_FLEX` column
 
 <🚧🦺 UNDER CONSTRUCTION> 
3. Note how Oracle handles reserved keywords (`ORA$DATE`, `ORA$SIZE`)
 
 <🚧🦺 UNDER CONSTRUCTION> 
4. Explore the relationship between the original JSON collection and new objects
 
 <🚧🦺 UNDER CONSTRUCTION> 

### Expected Outcomes

- Automated relational schema generation
- Understanding of Oracle's intelligent field mapping
- Functional duality view enabling JSON and relational access

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
