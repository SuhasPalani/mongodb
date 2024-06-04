### Structuring the Documents

![alt text](image.png)

![alt text](image-1.png)


`db.books.aggregate([{$lookup: {from:"authors",localField: "authors", foreignField: "_id", as:"creators"}}])`