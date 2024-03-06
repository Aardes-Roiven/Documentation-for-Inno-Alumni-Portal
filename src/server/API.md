# API

**Endpoint: GET /donation/**

- Description: Get all donations
- Request Method: GET
- Response Body:
  - List[schemas.DonationOutput]: A list of donation objects
- Request Headers:
  - Authorization: Bearer token for authentication
- Response Status Codes:
  - 200 (HTTP_OK): Successful request

**Endpoint: POST /donation/**

- Description: Create a new donation
- Request Method: POST
- Request Body:
  - schemas.MakeDonation: Donation details
    - message (string): The donation message
- Response Body:
  - status (int): The HTTP status code (201)
  - detail (string): Success message
  - data (dict): The created donation object
- Request Headers:
  - Authorization: Bearer token for authentication
- Response Status Codes:
  - 201 (HTTP_CREATED): Successful request

**Endpoint: GET /donation/admin**

- Description: Get the latest donation message from an admin
- Request Method: GET
- Response Body:
  - schemas.DonationOutput: The donation message object
- Request Headers:
  - Authorization: Bearer token for authentication
- Response Status Codes:
  - 200 (HTTP_OK): Successful request

**Endpoint: POST /donation/admin**

- Description: Update the donation message from an admin
- Request Method: POST
- Request Body:
  - schemas.MakeDonation: Donation details
    - message (string): The updated donation message
- Response Body:
  - status (int): The HTTP status code (202)
  - detail (string): Success message
  - data (dict): The updated donation object
- Request Headers:
  - Authorization: Bearer token for authentication
- Response Status Codes:
  - 202 (HTTP_ACCEPTED): Successful request