# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  The example shows a route that fetches a user by ID.  The code attempts to parse the ID as an integer, but it doesn't handle the case where the ID is not a number, which can lead to errors.

## Bug
The `bug.js` file contains the erroneous code.  The route handler attempts to parse `req.params.id` as an integer using `parseInt()`, but it does not handle the scenario where `req.params.id` is not a valid integer. This can lead to unexpected errors, such as `NaN` being used in comparisons, or even a crash if the error is not caught.

## Solution
The `bugSolution.js` file demonstrates the corrected code.  It includes a check to verify that the parsed ID is a valid integer before using it. If it's not a valid integer, it sends an appropriate error response.

## How to run
1. Clone this repository.
2. Navigate to the repository directory.
3. Install dependencies: `npm install express`
4. Run the bugged code: `node bug.js` (and test with invalid inputs)
5. Run the solution code: `node bugSolution.js` (and test with invalid inputs)