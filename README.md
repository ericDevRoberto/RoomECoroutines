Sumary
==================================

Creating the DataBase
------------------------

Define your tables as data classes annotated with @Entity. Define properties annotated with @ColumnInfo as columns in the tables.

Define a data access object (DAO) as an interface annotated with @Dao. The DAO maps Kotlin functions to database queries.

Use annotations to define @Insert, @Delete, and @Update functions.

Use the @Query annotation with an SQLite query string as a parameter for any other queries.

Create an abstract class that has a getInstance() function that returns a database.

Use instrumented tests to test that your database and DAO are working as expected. You can use the provided tests as a template.
