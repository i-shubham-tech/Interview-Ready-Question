What is MongoDB

Mongo DB is a NO-SQL,Document oriented database
where data store in JSON Like structure instead of table and row

IT is schema-flexible i.e each document have different field

What is BSON

BSON stand for Binary Json
It is data format used mongo db used to store documents 

BSON is similar to JSON but it store in Binary form which make it faster to write and read 


What is Database,collection,docoment,field

Database-IT is top level container,that contain multiple collection

collection - It is a group of docoment inside a database

Docoment - It is the single record in a collection .it contains field 

Field- Field are property of docoment in Key-value pair

What is _id

_id is the unique identifier that is automatically generated for each docoment in mongo db

It unique identify each docoment in collection 

By default is value is Objectid

what is Objectid 

Object id is the 12 digit unique identifier that is used by mongo db for _id value

What is insertOne and insertMany?

INSERT ONE- Insert One used to insert single record into a collection 

db.collectionname.insertOne({•••••})

INSERT MANY- Insertmany used to insert multiple record into a collection at Once

db.collectionname.insertMany([{••},{••}])

What is Update one and update Many?

UPDATEONE->Update one is used to update first condition matching docoment 

db.collection.updateOne({condion},{$set:{field name:NewValue}})

UpdateMany->Update many used to update all conditions matching docoment in the collection 

db.coll.updateMany({condition},{$set:{field:NewValue}})


What is Delete one and DeleteMany?

DeleteOne->Delete one is used to delete first condition matching docoment 

db.collection.deleteOne({condion})

DeleteMany->Delete many used to delete all conditions matching docomentin the collection 

db.coll.deleteMany({condition})






