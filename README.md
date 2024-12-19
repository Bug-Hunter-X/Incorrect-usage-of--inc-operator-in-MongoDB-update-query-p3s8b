# Incorrect Usage of $inc Operator in MongoDB Update Query

This repository demonstrates a common error in MongoDB update operations: the misuse of the `$inc` operator with a string value instead of a numeric value.

## Problem
The following code snippet shows an incorrect update operation that attempts to increment a counter field with a string value.
```javascript
db.collection('myCollection').updateOne({"_id":ObjectId("someId")},{$inc:{ "counter":'1'}})
```
This operation will not produce the expected result because the `$inc` operator expects a number, not a string. The result might be unexpected behavior or a MongoDB error.

## Solution
The solution is to use a numeric value with the `$inc` operator.
```javascript
db.collection('myCollection').updateOne({"_id":ObjectId("someId")},{$inc:{ "counter":1}})
```
This corrected operation ensures that the `counter` field is correctly incremented by 1.