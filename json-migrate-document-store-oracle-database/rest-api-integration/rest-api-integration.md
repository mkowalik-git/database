# 💻 REST API Generation and Integration

## Introduction

Oracle REST Data Services (ORDS) can automatically generate RESTful APIs for JSON collections and duality views, enabling easy integration with modern applications while maintaining the flexibility of both JSON and relational access patterns.

Estimated Lab Time: -- minutes

### Objectives

- Enable Oracle REST Data Services (ORDS) for JSON collections
- Generate RESTful APIs automatically
- Test CRUD operations via REST
- Understand API security and authentication

## Task 1: Enable ORDS for Collections

```sql
<copy>
-- Enable REST access for JSON collections
BEGIN
  ORDS.ENABLE_SCHEMA(
    p_schema => 'ADMIN',
    p_url_mapping_type => 'BASE_PATH',
    p_url_mapping_pattern => 'admin',
    p_auto_rest_auth => FALSE
  );
END;
/
</copy>
```


## Task 2: Test REST Endpoints

Using a REST client or browser:

```
GET /ords/admin/coffee/
GET /ords/admin/coffee/1
POST /ords/admin/coffee/
PUT /ords/admin/coffee/1
DELETE /ords/admin/coffee/1
```

## Task 3: Query via REST

```
GET /ords/admin/coffee/?q={"price":{"$lte":5}}
GET /ords/admin/coffee/?q={"item":"Espresso"}
```

### Expected Outcomes

- Functional REST APIs for JSON collections
- Understanding of API-based data access
- Integration readiness for modern applications


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
