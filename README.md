# Unhandled Promise Rejection in Express.js Application

This repository demonstrates a common error in Express.js applications: the lack of proper error handling for asynchronous operations within request handlers.  Unhandled promise rejections can lead to application crashes or unexpected behavior, making robust error handling crucial.

## The Bug

The `bug.js` file contains an Express.js application with an asynchronous operation (`someAsyncOperation`) within a request handler.  If the asynchronous operation rejects (simulated with a 50% chance of failure), the error is not caught, resulting in an unhandled promise rejection.

## The Solution

The `bugSolution.js` file demonstrates the correct approach: using `.catch()` to handle potential errors from the asynchronous operation, ensuring a graceful response even if the operation fails.  This prevents unhandled rejections and allows for more controlled error handling.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `node bug.js` and observe the behavior (sometimes it will work, sometimes it will crash).
4. Run `node bugSolution.js` and observe the more robust behavior.