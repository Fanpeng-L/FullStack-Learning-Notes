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

node -i -e "$(< index.js)"

```js
const mongoose = require("mongoose");
mongoose.connect("mongodb://127.0.0.1:27017/movieApp");

main().catch((err) => console.log(err));

async function main() {
  await mongoose.connect("mongodb://127.0.0.1:27017/test");
}

// define schema:
const movieSchema = new mongoose.Schema({
  title: String,
  year: Number,
  score: Number,
  rating: String,
});

const Movie = mongoose.model("Movie", movieSchema);

// creating movies
const amadeus = new Movie({
  title: "Amadeus",
  year: 1986,
  score: 9.2,
  rating: "R",
});

amadeus.save();

// another way of adding movies:
Movie.insertMany([
  { title: "Alien", year: 1979, score: 8.1, rating: "R" },
  { title: "Stand By Me", year: 1986, score: 8.6, rating: "R" },
]);
```

define schema with validation🔐:

```js
const movieSchema = new mongoose.Schema({
  name: {
    type: String,
    required: true,
    maxlength: 20,
  },
  price: {
    type: Number,
    required: true,
    min: 0,
  },
  onShow: {
    type: Boolean,
    default: false,
  },
});
```
