# User Registration Validation API using MuleSoft
# Project Overview
This project demonstrates a User Registration Validation REST API built using MuleSoft 4. The API validates incoming user registration details such as name, email, and role using MuleSoft Validation components and returns meaningful HTTP error responses for invalid inputs.
This project is designed for entry-level MuleSoft practice and showcases validation, error handling, and DataWeave expressions.

# Features
Validates mandatory fields (name, email, role)
Email format validation using MuleSoft is-email
Role validation (only admin or user allowed)
Centralized error handling
Proper HTTP 400 Bad Request responses for validation errors
Clean and readable MuleSoft flow design

# Tools & Technologies Used
MuleSoft 4
Anypoint Studio
DataWeave 2.0
Validation Module
HTTP Listener
REST API
Postman (for API testing) 

# API Details
Endpoint
POST /registerUser

# Sample Request
{
"name": "jenifer",
"email": "jenifer@test.com",
"role": "admin"
}

# Validations Implemented
# Field	      # Validation Rule
  name	         Must not be null
  email          Must be a valid email format
  role           Must be either admin or user

# Flow Explanation
1.HTTP Listener receives the POST request.
2.Validation checks are performed:
  is-not-null for name
  is-email for email
  is-true condition to validate role
3.If validation fails, control moves to the global error handler.
4.Custom error message is returned with HTTP 400 status.
5.If all validations pass, success response is returned.

# Role Validation Expression Used
#[ if ((payload.role == "admin") or (payload.role == "user")) true else false ]

# Sample Error Response
{
"error": "Invalid Email"
}
{
"error": "Role must be Admin or User"
}

# HTTP Status Codes
200 OK – Validation successful
400 Bad Request – Validation error

# How to Run the Project
Import the project into Anypoint Studio.
Update the HTTP Listener port if required.
Run the application.
Test the API using Postman or any REST client.

# Future Enhancements
Add mobile number validation using regex
Store validated user data in a database
Implement API specification using RAML

# Author
Jenifer Roseline James
