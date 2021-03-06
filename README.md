# CodeIgniter MongoDB Library
## (No longer CodeIgniter specific - use in any PHP application!)

This is a query builder inspired CodeIgniter library to integrate a MongoDB database into your application.

### Using with CodeIgniter:

1. Add the file Mongo_db.php to your /application/libraries folder.
2. Add the file mongodb.php to your /application/config folder.
3. Update the config file.

### Using in a non-CodeIgniter app

1. Put the library in an appropriate folder
2. Load the library with `require_once`
3. Pass an array into the `load()` method with the parameters from the config/mongodb.php file to connect to the database

You can now autoload the library or include it in one of your controllers at run time.

You can interact with the database using many of the active record functions that CodeIgniter provides.

	$this->mongo_db
	->where_gte('age', 18)
	->where(array(
		'country' => 'UK',
		'like_whisky' => TRUE
	))
	->get('people');
	
The result will be an object containing matching documents.

### Select Functions

* `select`				Return select fields from returned documents
* `where`				Where section of the query
* `where_in`				Where something is in an array of something
* `where_in_all`			Where something is in all of an array of * something
* `where_not_in`			Where something is not in array of something
* `where_gt`				Where something is greater than something
* `where_gte`				Where something is greater than or equal to something
* `where_lt`				Where something is less than something
* `where_lte`				Where something is less than or equal to something
* `where_ne`				Where something is not equal to something
* `where_near`				Where something is near to something (2d geospatial search)
* `order_by`				Order the results
* `limit`				Limit the number of returned results

### Insert Function

* `insert`				Insert a new document into a collection

### Update Functions

* `inc`					Increments the value of a field
* `dec`					Decrements the value of a field
* `set`					Sets a field to a value
* `unset_field`				Unsets a field
* `addtoset`				Adds a value to an array if doesn't exist
* `push`				Pushes a value into an array field
* `pop`					Pops a value from an array field
* `pull`				Removes an array by the value of a field
* `rename_field`			Rename a field
* `update`				Update a single document in a collection
* `update_all`				Update all documents in a collection

### Delete Functions

* `delete`				Delete a single document in a collection
* `delete_all`				Delete all documents in a collection

### Index Functions

* `set_index`				Creates a new index
* `delete_index`			Deletes an index

### Database Functions

* `drop_db`				Drops a database
* `switch_db`				Switch to a different database

### Collection Functions

* `drop_collection`			Drops a collection