## The MongoDB CRUD Database Operations🍃

This article explains MongoDB CRUD operations to you, the four primary database operations in any database. They enable you to Create, Read, Update and Delete data from your Database. The CRUD acronym stands for;

C- Create

R -Read

U -Update

D -Delete

**Create**

The C stands for Create. This is how you add new items to your Database. The items may be objects or individual items. If the collection doesn’t exist, this operation will create a new one for you. Collection, in this case, refers to the name of your Database. Below is an example of how you insert items into a database called students. You can insert one or many at the same time.

_db.collection.insertOne()_

_db.collection.insertMany()_

**Read**

This operation enables us to read the information available in our Database from the name itself. We use a method called to find to do this.

_db.collection.find()_

find with no query inside returns the entire database.

_db.collection.find(query)_

Inside the bracket, you feed the specific item you are looking for.

**Update**

This operation helps one make changes to an already existing database. Inside the brackets, you will specify the value pairs you are interchanging or the ones you’re adding inside.

_db.collection.updateOne()_

_db.collection.updateMany()_

**Delete**

Delete the object or items that you do not want in your collection. MongoDB provides the following methods for deleting. Similar to the insert command, you can delete one or delete many simultaneously.

_db.collection.deleteOne()_

_db.collection.deleteMany()_

I hope this makes your life easier.

Happy Coding!🍃​☕​