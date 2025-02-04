# Express.js Route Handler Error

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input. Specifically, the route `/users/:id` fails to handle cases where `req.params.id` is not a valid number.

## Bug

The `bug.js` file contains the erroneous code.  The handler attempts to parse `req.params.id` as an integer using `parseInt()`, but doesn't check if the result is actually a number.  If the ID is not a number (e.g., a string), the `users.find()` method will not function correctly potentially leading to unexpected results or errors.

## Solution

The `bugSolution.js` file provides a corrected version. It includes explicit error handling to check if `parseInt(userId)` results in a valid number before proceeding. If not, it sends an appropriate error response.