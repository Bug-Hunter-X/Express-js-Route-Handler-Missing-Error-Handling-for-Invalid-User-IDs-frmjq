# Express.js Route Handler Missing Error Handling for Invalid User IDs

This repository demonstrates a common error in Express.js route handlers:  failure to handle cases where user input (in this case, a user ID) is invalid.  The provided code attempts to parse a user ID from the request parameters without validating it as a number. If a non-numeric ID is provided, the `parseInt` function will return `NaN`, causing the `users.find` method to fail silently or even throw an error. 

## Bug
The `bug.js` file contains the erroneous code.  It attempts to find a user based on their ID, but doesn't handle the case where the ID is not a valid number.

## Solution
The `bugSolution.js` file shows the corrected code.  It includes error handling to check if `parseInt(userId)` results in a valid number before proceeding.