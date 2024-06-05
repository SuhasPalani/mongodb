### Structuring the Documents

![alt text](image.png)

![alt text](image-1.png)


`db.books.aggregate([{$lookup: {from:"authors",localField: "authors", foreignField: "_id", as:"creators"}}])`

### createCollection()
The provided code creates a MongoDB collection named `posts` with a schema validator that ensures each document contains a `title`, `text`, `creator`, and `comments` field. The `title` and `text` fields must be strings, while the `creator` field must be an ObjectId. The `comments` field must be an array of objects, each containing a `text` field (string) and an `author` field (ObjectId). This schema validation enforces a consistent structure for all documents in the `posts` collection, ensuring data integrity and facilitating easier data management and querying.

`db.createCollection('posts', {
  validator: {
    $jsonSchema: {
      bsonType: 'object',
      required: ['title', 'text', 'creator', 'comments'],
      properties: {
        title: {
          bsonType: 'string',
          description: 'must be a string and is required'
        },
        text: {
          bsonType: 'string',
          description: 'must be a string and is required'
        },
        creator: {
          bsonType: 'objectId',
          description: 'must be an objectid and is required'
        },
        comments: {
          bsonType: 'array',
          description: 'must be an array and is required',
          items: {
            bsonType: 'object',
            required: ['text', 'author'],
            properties: {
              text: {
                bsonType: 'string',
                description: 'must be a string and is required'
              },
              author: {
                bsonType: 'objectId',
                description: 'must be an objectid and is required'
              }
            }
          }
        }
      }
    }
  }
});
`



### runCommand
The provided command modifies the existing `posts` collection in MongoDB to include a schema validator with the same structure and requirements as before, but with an added `validationAction` set to `warn`. This means that while the `posts` collection must still contain documents with `title`, `text`, `creator`, and `comments` fields (where `title` and `text` are strings, `creator` is an ObjectId, and `comments` is an array of objects with `text` and `author` fields as strings and ObjectIds respectively), any document that does not comply with this schema will generate a warning instead of an error, allowing non-compliant documents to be inserted or updated while still notifying the user of the schema violations.



`db.runCommand({
  collMod: 'posts',
  validator: {
    $jsonSchema: {
      bsonType: 'object',
      required: ['title', 'text', 'creator', 'comments'],
      properties: {
        title: {
          bsonType: 'string',
          description: 'must be a string and is required'
        },
        text: {
          bsonType: 'string',
          description: 'must be a string and is required'
        },
        creator: {
          bsonType: 'objectId',
          description: 'must be an objectid and is required'
        },
        comments: {
          bsonType: 'array',
          description: 'must be an array and is required',
          items: {
            bsonType: 'object',
            required: ['text', 'author'],
            properties: {
              text: {
                bsonType: 'string',
                description: 'must be a string and is required'
              },
              author: {
                bsonType: 'objectId',
                description: 'must be an objectid and is required'
              }
            }
          }
        }
      }
    }
  },
  validationAction: 'warn'
});
`
#### summary
![alt text](<WhatsApp Image 2024-06-04 at 19.33.19_18f60bdf.jpg>)




### Useful Resources & Links
Helpful Articles/ Docs:

- More Details about Config Files: https://docs.mongodb.com/manual/reference/configuration-options/

- More Details about the Shell (mongo) Options: https://www.mongodb.com/docs/manual/reference/method/

- More Details about the Server (mongod) Options: https://docs.mongodb.com/manual/reference/program/mongod/
