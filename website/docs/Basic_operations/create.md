---
sidebar_position: 2
---

# Insert operation

The insert operation adds a new document to a collection.

## Insert a single document

The `insertOne()` command is used to add a single document into a collection, using this syntax format:

```sh
db.collection.insertOne({field1: value1, field2: value2,.... fieldN: valueN})
```

The example below depicts how a single document can be added to a collection.
If a collection does not exist, the insert command automatically creates one.

```sh
db.scientists.insertOne({
    name: {
        firstname: "Thomas",
        lastname: "Edison"
    },
    born: 1847,
    invention: "lightbulb"
})
```

If the operation is successful, you will get a response with acknowledged set to true, and the autogenerated ObjectId of the document that looks like this:

```sh
{
  acknowledged: true,
  insertedId: ObjectId("6346fcafd7a4a1b0b38eb2db")
}
```

## Insert multiple documents at once

A collection can contain multiple documents.
Using the `insertMany()` command, you can add multiple documents to a collection at once.

```sh
db.collection_name.insertMany([{document1}, {document2},... {documentN}])
```

The following example shows how to insert multiple documents into a collection:

```sh
db.scientists.insertMany([
    {
        name: {
        firstname: "Alan",
        lastname: "Turing"
        },
        born: 1912,
        invention: "Turing Machine"
    },
    {
        name: {
        firstname: "Graham",
        lastname: "Bell"
        },
        born: 1847,
        invention: "telephone"
    },
    {
        name: {
        firstname: "Ada",
        lastname: "Lovelace"
        },
        born: 1815,
        invention: "computer programming"
    }
])
```

You can retrieve all the documents in the collection with this command: `db.scientists.find({})`
