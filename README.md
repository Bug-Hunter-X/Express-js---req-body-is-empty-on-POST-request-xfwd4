# Express.js - req.body empty on POST request

This repository demonstrates a common issue in Express.js applications where `req.body` remains empty despite sending a JSON payload in a POST request.  The problem stems from the missing or incorrectly configured middleware to parse JSON request bodies.

## Bug

The `bug.js` file contains an Express.js application that attempts to handle a POST request to `/users`.  It logs the contents of `req.body`, but `req.body` will be empty due to missing middleware for JSON parsing.

## Solution

The `bugSolution.js` file demonstrates the correct way to parse the JSON request body using `express.json()`. This middleware must be used before any route handlers that expect JSON data.

## How to Reproduce

1. Clone this repository.
2. Navigate to the project directory in your terminal.
3. Run `node bug.js`.
4. Send a POST request to `http://localhost:3000/users` with a JSON payload (e.g., using Postman or curl).
5. Observe that the server logs an empty object for `req.body`.
6. Now run `node bugSolution.js` and repeat steps 4 and 5.  You should see the JSON payload logged correctly this time.
