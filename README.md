# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling for invalid input.  Specifically, the `/users/:id` route does not handle cases where the `id` parameter is not a valid number.

## Bug

The `bug.js` file contains the erroneous code.  The handler attempts to parse the `id` parameter as an integer without checking if it's actually a valid integer. If a non-numeric id is provided, `parseInt(userId)` will return `NaN`, leading to a `user` variable that is null. The subsequent check `if (!user)` fails resulting in an error or unexpected behavior.

## Solution

The `bugSolution.js` file demonstrates the corrected code. The solution explicitly checks if `parseInt(userId)` results in a valid integer using `isNaN()`.  If the `id` parameter is not a valid integer, the handler returns an appropriate error response (400 Bad Request).

This example highlights the importance of robust error handling in Express.js applications to ensure reliability and prevent unexpected behavior.