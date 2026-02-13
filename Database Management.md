# Granting and revoking access to a view

```Postgresql
GRANT privilege(s) ON object TO role
REVOKE privilege(s) ON object FROM role
```
- Privileges: SELECT , INSERT , UPDATE , DELETE , TRUNCATE , REFERENCES , TRIGGER , CREATE , CONNECT ,TEMPORARY , EXECUTE , and USAGE. (in PostgreSQL)
- Objects: table, view, schema, etc.
- Roles: a database user or a group of database users
---
# Database roles

- Manage database access permissions
- A database role is an entity that contains information that:
	- Define the role's privileges
		- Can you login?
		- Can you create databases?
		- Can you write to tables?
	- Interact with the client authentication system
	- Password
- Roles can be assigned to one or more users
- Roles are global across a database cluster installation

## Create AND Alter a role

```postgresql
CREATE ROLE role_name WITH someAttributesLIKE(PASSWORD '' VALID UNTIL);
ALTER ROLE role_name WITH someAttributesLIKE(PASSWORD '' VALID UNTIL);
```

---
# Table partitioning

## Vertical partitioning
Separate the table into many small tables even if the table is normalized

## Horizontal Partitioning
EX:
```postgresql
CREATE TABLE sales (
...
timestamp DATE NOT NULL
)
PARTITION BY RANGE (timestamp);
CREATE TABLE sales_2019_q1 PARTITION OF sales
FOR VALUES FROM ('2019-01-01') TO ('2019-03-31');
...
CREATE TABLE sales_2019_q4 PARTITION OF sales
FOR VALUES FROM ('2019-10-01') TO ('2020-01-31');
CREATE INDEX ON sales ('timestamp');
```

---
