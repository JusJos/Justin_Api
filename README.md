# REST API Documentation

This document provides the necessary information to build and host a REST API with one endpoint that accepts requests with both GET and POST methods.

## Objective

Build and host a REST API with one endpoint that accepts requests with both GET and POST methods.

The POST method endpoint takes in the request (JSON) and returns the following:

1. Status
2. User ID
3. College Email ID
4. College Roll Number
5. Array for numbers
6. Array for alphabets

The GET method endpoint doesn't take any user input; it only returns an operation code.

Refer to Annexure (A) for request/response samples.

## Hosting

You can choose any hosting provider of your choice. If you don't have one already, you can use Heroku, Netlify, or Vercel.

## API Logic

### Route: /bfhl | Method: POST

- Endpoint: `https://testbfhl.herokuapp.com/bfhl` (Example with POST method)
- Response should always contain your `user_id` (fullname_dob) in the following format:
    - "user_id": {full_name_ddmmyyyy}
    - Example: "user_id": "john_doe_17091999"
- The response should include "is_success" to mark the status of the operation, which can be true or false.

### Route: /bfhl | Method: GET

- Endpoint: `https://testbfhl.herokuapp.com/bfhl` (Example with GET method)
- Doesn't take any input from the user. The endpoint will be hit with a GET request.
- Expected HTTP Status Code: 200
- Expected Response Body (JSON):
    ```
    {
      "operation_code": 1
    }
    ```

Please ensure you follow best practices, including exception handling and input validation.

## Submission

1. Develop the API using any of the supported languages.
2. Host your API (refer to the Hosting section).
3. Share the API endpoint in the given form.
   - Form Link: [Submit API Endpoint](https://forms.office.com/r/c1Y1Eih2eF)
4. Fastest valid submissions will be considered.
5. The URL that you submit should have the logic specified above in the "/bfhl" route.

## Annexure (A) - Request/Response Samples (POST Method)

### Example A - Request

```json
{
  "data": ["A", "1", "334", "4", "R"]
}
```

#### Response

```json
{
  "is_success": true,
  "user_id": "john_doe_17091999",
  "email": "john@xyz.com",
  "roll_number": "ABCD123",
  "numbers": ["1", "334", "4"],
  "alphabets": ["A", "R"]
}
```

### Example B - Request

```json
{
  "data": ["2", "4", "5", "92"]
}
```

#### Response

```json
{
  "is_success": true,
  "user_id": "john_doe_17091999",
  "email": "john@xyz.com",
  "roll_number": "ABCD123",
  "numbers": ["2", "4", "5", "92"],
  "alphabets": []
}
```

### Example C - Request

```json
{
  "data": ["A", "ABCD", "DOE"]
}
```

#### Response

```json
{
  "is_success": true,
  "user_id": "john_doe_17091999",
  "email": "john@xyz.com",
 

 "roll_number": "ABCD123",
  "numbers": [],
  "alphabets": ["A", "ABCD", "DOE"]
}
```

Note: The email, roll number, and user ID used in the examples above are placeholders and should be replaced with the appropriate values in the actual implementation.
