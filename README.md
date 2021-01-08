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

Courotines & Room
-----------------

Use ViewModel, ViewModelFactory, and data binding to set up the UI architecture for the app.

To keep the UI running smoothly, use coroutines for long-running tasks, such as all database operations.

Coroutines are asynchronous and non-blocking. They use suspend functions to make asynchronous code sequential.

When a coroutine calls a function marked with suspend, instead of blocking until that function returns like a normal function call, it suspends execution until the result is ready. Then it resumes where it left off with the result.

The difference between blocking and suspending is that if a thread is blocked, no other work happens. If the thread is suspended, other work happens until the result is available.

# To implement click handlers that trigger database operations, follow this pattern:

1-Launch a coroutine that runs on the main or UI thread, because the result affects the UI.

2-Call a suspend function to do the long-running work, so that you don't block the UI thread while waiting for the result.

3-The long-running work has nothing to do with the UI, so switch to the I/O context. That way, the work can run in a thread pool that's optimized and set aside for these kinds of operations.

4 -Then call the long running function to do the work.

Use a `Transformations` map to create a string from a LiveData object every time the object changes.
