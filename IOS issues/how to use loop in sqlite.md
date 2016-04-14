#how to use loop in sqlite

##FMDB v2.6.2
This is an Objective-C wrapper around SQLite: http://sqlite.org/
 
https://github.com/ccgus/fmdb

##iOS SQLite Tutorial – CREATE Database, INSERT, SELECT Examples
http://hayageek.com/ios-sqlite-tutorial-create-select/

##solution:
http://stackoverflow.com/questions/16621281/how-to-use-loop-in-sqlite-for-get-name-from-certain-column


	OK first the SELECT statement:
	
	Change the statement from SELECT * ... to SELECT colname1, colname2, ... so you are then certain of the order in which columns are returned, and you won't have to refer to the schema in order to find out what order they come back in. This actually saves time.
	BroID must be included in the columns being selected.
	You'll want an ORDER BY clause in order to get consistent results.
	You can probably get the database to only include rows WHERE BroID IS NOT NULL, which might suite your needs.
	If you still need to use code to stop the fetching, then simply test for a NULL BroID column and break out of the while loop using:
	
	while (sqlite3_step(compiledStatement) == SQLITE_ROW)
	{
	    // Fetch other columns
	    if (sqlite_column_type(compiledStatement, INDEX) == SQLITE_NULL)
	        break;
	}
	Where INDEX is the column index of BroID.
	
	It's not clear if you want the row where BroID IS NULL in the result set; if you don't then perform the sqlite_column_type() test before fetching the columns, else leave it as above.
	
	Refer to the reference for details.