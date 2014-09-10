#How to make a DB?[Draft]

It will built in C as most the db in the world, and using b-tree or b+ tree to store.

* db store index and data seperately
* both data and index will store in file system as file.

Assume a record as a row is 800 byte(defined by scheme) 

FirstName     | LastName | Address
------------- | -------- | ----------
Content Cell  | bar1     |  blasdsfsd
Content Cell  | bar2     |  fsadfsdaff
Content Cell  | bar3     |  fsadfsdaff

and index file looks like
bar1, 100
bar2, 200
bar3, 300

so search the record ==> search the index in b-tree, and lseek the data file

which mean a table will have a data file and many index files(I am going to index every column)


* after have stored data and index files, using a ISAM http://en.wikipedia.org/wiki/ISAM
* then I could GET a record, and PUT a record
* then I need a SQL parser that translate SQL statement into a sequence of GETs. 
* If two table is joined, then a optimizer is need to decide which table to read first.
* Insert parse into PUT statement
* transacation manager to combine multiple INSERTs
* backup/restore....replicaion tools to read transcation log and replicate the transcation
* it will need some connection manager the handle connections, authenticate, then run the request



REF:
* http://www.sqlite.org/arch.html
* http://sqlite.org/atomiccommit.html
* http://www.sqlite.org/fileformat.html