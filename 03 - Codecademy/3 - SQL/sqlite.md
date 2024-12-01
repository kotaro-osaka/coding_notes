# What is SQLite
- Database engine
- Software that allows user to interact with relational database
- Database is stored in single file (distinguishes it from other engines)
	- Allows for more accessibility
- <u>Drawbacks</u>
	- Many updates from different users (Data integrity)
		- Only one user can write to the file at a time
	- To ensure security requires more work
	- Doesn't offer same functions as many other database system
		- Limits some advanced features
	- Doesn't validate data types
		- Any type can be stored in any column
	- Schemas constrain type of data in each column, but don't enforce them
# Uses
- Testing, development & other use cases where it makes sense for database to be on same drive as app code