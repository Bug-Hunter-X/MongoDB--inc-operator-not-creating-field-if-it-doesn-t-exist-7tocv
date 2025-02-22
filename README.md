# MongoDB $inc Operator Bug
This repository demonstrates a common error when using the `$inc` operator in MongoDB update operations.  The `$inc` operator, unlike `$set`, does not create a field if it doesn't already exist. This can result in unexpected behavior, especially when attempting to increment counters that may not be present in all documents. 

## Bug Description
The provided `bug.js` file contains a MongoDB update operation that uses `$inc` to decrement a counter. However, if the 'counter' field does not exist in the document, the update will fail silently, leaving the document unchanged.

## Solution
The `bugSolution.js` file demonstrates a corrected approach. It utilizes the `$setOnInsert` operator to create and initialize the counter field if it doesn't already exist.  This ensures reliable incrementing behavior. 

## How to Reproduce
1. Clone this repository.
2. Ensure a MongoDB instance is running.
3. Run `bug.js` and `bugSolution.js` (modify connection strings as needed). Observe the differences in results after running both. 
