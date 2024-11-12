# JavaScript Promises

## Introduction

A Promise in JavaScript is an object representing the eventual completion or failure of an asynchronous operation.

## States of a Promise

1. **Pending**: Initial state, neither fulfilled nor rejected.
2. **Fulfilled**: Operation completed successfully.
3. **Rejected**: Operation failed.

## Creating a Promise

```javascript
let promise = new Promise((resolve, reject) => {
    // asynchronous operation
    if (/* success */) {
        resolve('Success!');
    } else {
        reject('Error!');
    }
});
```

## Using Promises

### `then` Method

Handles the fulfillment of the promise.

```javascript
promise.then((value) => {
    console.log(value); // Success!
});
```

### `catch` Method

Handles the rejection of the promise.

```javascript
promise.catch((error) => {
    console.error(error); // Error!
});
```

### `finally` Method

Executes code regardless of the promise's outcome.

```javascript
promise.finally(() => {
    console.log("Promise settled.");
});
```

## Chaining Promises

```javascript
promise
    .then((value) => {
        return new Promise((resolve, reject) => {
            // another asynchronous operation
        });
    })
    .then((newValue) => {
        console.log(newValue);
    })
    .catch((error) => {
        console.error(error);
    });
```

## Common Use Cases

-   Fetching data from an API
-   Reading files
-   Performing asynchronous computations

## Conclusion

Promises provide a powerful way to handle asynchronous operations in JavaScript, making code more readable and maintainable.
