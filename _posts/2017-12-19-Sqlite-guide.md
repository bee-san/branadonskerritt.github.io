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





