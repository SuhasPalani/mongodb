# Crud operation

`show dbs` - to display all the available databases

![alt text](image-1.png)

``use x`` - x is db name--> no need to write command for creating as this automatically creates a db  

``db.flightData.insertOne({})`` --- db is the database, flightData is the like the table, insertOne is inserting one row of data 

![alt text](image-2.png)

``db.flightData.find()`` --- to show all the contents in the table

![alt text](image.png)


### ``CRUD OPERATIONS``
 ![alt text](image-3.png)


- `updateOne()`
![alt text](image-4.png)

- `updateMany()`
![alt text](image-5.png)

- `deleteMany()`
![alt text](image-6.png)

- `insertMany()`
![alt text](image-7.png)

-  `find` - filter
![alt text](image-8.png)

- ### `db.flightData.find({distance: {$gt: 10000}})`
![alt text](image-9.png)


- `db.flightData.findOne({distance: {$gt: 100}})`    - finds only first one
![alt text](image-10.png)


-  `db.flightData.updateOne({ _id: ObjectId('665bf5867cd5f0d45ccdcdf9')}, {$set: {delayed:true}})` 
![alt text](image-11.png)


- `db.flightData.update({ _id: ObjectId('665bf5867cd5f0d45ccdcdf9')}, {$set: {delayed:false}})` 
![alt text](image-12.png)

- `replaceOne()` - safer way to replace data


- `db.passengers.find().toArray()` - this gives all the values in the document but find() gives only top 20
![alt text](image-13.png)
![alt text](image-14.png)


- `db.passengers.find().forEach((passData) => {printjson(passData)})` - for react for large documents 




- `db.passengers.find({}, {name: 1})` - projection - filters columns
![alt text](image-15.png)



- `db.passengers.find({}, {name: 1, _id: 0})` - 1 if we need column, 0 if not needed
![alt text](image-16.png)



- ` db.flightData.updateMany({}, {$set: {status: {decription: 'on-time', lastUpdated: '1 houir ago'}}})` - embedded documents
![alt text](image-17.png)


- `db.passengers.updateOne({name:'Albert Twostone'},{$set :{hobbies:['sports','cooking']}})` - working with arrays
![alt text](image-18.png)

![alt text](image-19.png)

- `db.passengers.findOne({name: 'Albert Twostone'}).hobbies`  - accessing structure Data
![alt text](image-20.png)



- `db.passengers.find({hobbies: 'sports'})` - find thru keyword
![alt text](image-21.png)