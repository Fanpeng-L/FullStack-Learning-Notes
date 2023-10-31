# No-sql vs. sql

<img src="../images/Back-end/sql vs nosql.png" width="500">

# Mongodb

the following are Mongo Shell commands:

## 1. collection

`use <collection name>`

`show collections`

## 2. C -- create

```js
db.collection.insert([
  { name: "charlie", age: 3, dogFriendly: true },
  { name: "Tony", age: 17, dogFriendly: false },
]);
```

## 3. R -- find sth

`db.cats.find()`
`db.cats.find({name:cookie})`

## 4. U -- update

need to provide 2 arguments:

```js
// update one:
db.cats.updateOne({ name: "charlie" }, { $set: { age: 5 } });
```

update many:

`db.cats.updateMany()`

## 5. D -- delete

`db.cats.deleteOne()`
`db.cats.delateMany()`

<br>

# Mongoose - ODM

object data mapper

Solving mongoose.connect issues
If you are using the latest versions of Node.js with mongoose, and you get a connection refused ECONNREFUSED error message when connecting your app to the database, then you might need to change localhost to 127.0.0.1 in your mongoose.connect database connection string:

mongoose.connect('mongodb://127.0.0.1:27017/your_database_name_here')
Also, in the currently newest mongoose versions you don't need to pass the options object as the second argument to the mongoose.connect method.
