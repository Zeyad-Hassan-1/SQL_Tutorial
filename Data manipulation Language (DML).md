

| Query                                                                                                            | Usage                                       |
| ---------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| INSERT INTO _table_name_ (_column1_, _column2_, _column3_, ...)  <br>VALUES (_value1_, _value2_, _value3_, ...); | **Insert new records in a table.**          |
| UPDATE _table_name_  <br>SET _column1_ = _value1_, _column2_ = _value2_, ...  <br>WHERE _condition_;             | **modify the existing records in a table.** |
| DELETE FROM _table_name_ WHERE _condition_;                                                                      | **Delete existing records in a table.**     |

***Note*****: Be careful when deleting records in a table! Notice the `WHERE` clause in the `DELETE` statement. The `WHERE` clause specifies which record(s) should be deleted. If you omit the `WHERE` clause, all records in the table will be deleted!**

**SAME THING FOR UPDATE**