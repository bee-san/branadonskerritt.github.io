---
title: "SQLite guide in Python"
categories:
  - Maths
---

I got annoyed that there were either guides on standalone sqlite or not-so-good guides on sqlite in Python, so I decided to make a guide on sqlite in python. In this guide, we will be making a ToDo list database in order to teach Sqlite fundamentals.

# What is Sqlite?
Sqlite is a databasing standalone library which does not need to be configured before use. It has many advantages, stated here
* Does not require a seperate server to operate
* Does not need to be configured prior to use
* Very small and lightweight
* Supports most of the query language features from SQL
* Is available on all platforms and in most languages

# Diving right in

## Setting up

Our ToDo list app will have 4 columns in a single table

id | task | dateDue | dateAdded
--- | --- | --- | ---

and will look roughly like the above table. So first step is to create a database. But before that, we need to open a connection to the SQLite database.

```Python
import sqlite3
conn = sqlite3.connect("todo.db")
c = conn.cursor()
```

Now thankfully the file doesn't have to exist, if it doesn't exist SQlite will make the file. Since in this app I will be using more than just one databse object. I decided to make a database controller class and create a new object for every database we make, since I plan on making more than one database.

```Python
class Database_controller():
	def __init__(self, table_name):
		self.cursor = db.cursor()
		self.db = db
```

So using this new class, we can _instanstiate_ an object which contains the cursor and the database for the database we have chosen.

So in our example, we can just write

```Python
import sqlite3
database_handler_todo = Database_controller("todo.db")
```
and it'll allow us to control the database using an object.

I wanted to make the database controller into an object because this program is a part of a larger program and may have multiple databases open, so it was best to really differentiate the databases like this.

The next step is to create the table we defined above.
```Python
def ToDo_create():
	db_handler = Database_controller("todo.db")
	db_handler.cursor.execute("""CREATE TABLE
		todo(id INTEGER PRIMARY KEY, task TEXT,
		datetime TEXT, addedWhen TEXT)""")
    db_handler.db.commit()
```

This causes a slight problem. What if we call the create table function again? It'll error. People online have suggested using a try and except loop or seeing if the table already exists, but there's an easier way.
```Python
def ToDo_create():
	db_handler = Database_controller("todo.db")
	db_handler.cursor.execute("""CREATE TABLE IF NOT EXISTS
		todo(id INTEGER PRIMARY KEY, task TEXT,
		dateDue TEXT, dateAdded TEXT)""")
    db_handler.db.commit()
```

The "IF NOT EXISTS" part is very useful to us, since if the table does exist it doesn't recreate it. It only creates the table if it doesn't exist. Also, id is a primary key.

A primary key is a unique identifier for each _record_ in a table. A record is simply a row of data, one data object. We need to be able to identify each row uniquely, so we use a primary key. The primary key is auto-incremental, so we don't need to increment it ourselves. Also, no 2 records in the table can have the same id. Sqlite does this for us, so we don't need to worry.

Also notice how we execute commands using the cursor. Everytime we want to 'save' the database, we need to commit it using db.commit().

Most SQL commands are written in capital letters. 

Our next step is to add data to our database.
``` Python
def ToDo_add(tuple):
	# Adds new entry to todo table.
	from datetime import datetime
	task = tuple[0]
	dateCreated = tuple[2]
	db_handler.cursor.execute("""INSERT INTO todo(task, datetime, addedWhen) VALUES (?, ?, ?)""", (task, datetime1, (datetime.now())))
	db_handler.db.commit()
```

So ToDo_add receives a tuple in the format (taskName, taskConfidence, dateCreated). taskConfidence is ignored as this application is using natural language processing, however we won't delve into that here.

We take the values out of the tuples and execute an INSERT into statement.



