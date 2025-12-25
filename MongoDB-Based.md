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

Field- Field are Key-value pair inside docoment 

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

What is findOne and find()

FindOne - FindOne fetch first matching docoment , even if multiple matches 

db.coll.findOne({condition},{projection})

Find - Find fetch all docoment if no condition applied or fetch all condition matching docoment 

db.coll.find() or db.find({condition},{proj..})

What is projection

Projection control which field of docoment want to show instead of all

find({condition},{field1:1,field2:0})
1-mean show 0-mean don't show


Condition Operator 

$eq-->Equal to 
$ne-->Not equal 
$gt-->Greater than
$gte-->Greater than or equal
$lt1-->Less than
$lte-->Less than or equal
$in-->Match values in array
$nin-->Not in array


Logical Operators


$and-->All conditions true {$and:[{cond1},{2}]}
$or-->Any condition true {$or:[{cond1},{2}]}
$not-->Negates condition {age:{$not:{$gt:4}}}


Update operator

set-->Update/add field{$set:{field1:neval}}
$inc-->Increment number{$inc:{fInc1:1,fDec2:-1}
$unset-->Remove field {$unset:{field1:""}}

Array operator 

$push-->Add to array {$push:{field1:value}}
$pull-->Remove from array{pull:{field1:val}}
$addToSet-->Add uniq arr value {addToSet:{f:v}


string operator 


$regex-->find pattern in string

{field1:{$regex:"xyz"}}} -> contain anywhere 
{field1:{$regex:"xyz$"}}} -> end with
{field1:{$regex:"^xyz"}}} -> start with

$option:'i' --> to ignore case sensitive 


What is sort

Sort used to order the docoment in ascending or descending order based on field

db.coll.find().sort({field:1}) -> ascending 
db.coll.find().sort({field:-1}) -> decending 

what is limit

Limit used to restrict the number of docoment  to return from resut

db.coll.find().limit(number)
examp db.coll.find().limit(5) only show first 5


what is skip

skip used to skip specific number of docoment from the results 

db.coll.find().skip(5) will skip first five








