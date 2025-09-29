# DB
Notes on Databases 

# Tables

Difference between a **dbo.** and **comp.**

| dbo. : Database Object | comp : is just user defined schema |
| --- | --- |
| dbo is the default schema in SQL server. | The name `comp` is just an example; 
schemas can be named anything meaningful to the organization or the application. |
| For any new object created without specifying a schema, the dbo schema is the used | The “comp” schema serves as a separate namespace. Objects within the same schema are distinct from other objects in other schemas, even if they have the same name |
| It is typically used to store all the default database objects | This allows for better organization and separation of database objects, which can be useful for managing permissions and logical groupings of related objects. |
| Objects in the dbo schema are typically accessible to all users with database access, unless specifically restricted. | Objects in the `comp` schema can have distinct permissions, allowing for more granular control over who can access or modify the objects within that schema. |
| Using schemas allows for better organization of database objects. For example, you might have different schemas for different departments (hr.table, sales.table) or different applications within the same database.
 | Schemas help avoid naming conflicts. You can have `dbo.table` and `comp.table` in the same database without any issues. |

## Creating a Table

## Copying a Table

```sql
SELECT *
INTO newtablename  -- Specify the new table name here
FROM tablename;
```

## Changing a column field

```sql
UPDATE table_name
SET column_name = new_value
WHERE condition;
```

# Administration
