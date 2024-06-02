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