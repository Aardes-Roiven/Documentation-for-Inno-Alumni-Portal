# API

## loginRegularUser

Input: An object with properties "email" and "password"

Output: A user token (string)

Description: This function is used to login a regular user. It takes an object containing the user's email and password as input. It creates a new FormData object and appends the email and password to it. The function then creates an options object with headers and body properties, which are used for making a request to the server. If the login is successful, the function returns the user token. If there is an error, it notifies the error.

## registerRegularUser

Input:
- data: object with properties "name", "email", "password", and "confirmPassword"
- options: object (optional)

Output: RegistrationFeedback (object)

Description:
The registerRegularUser function is an asynchronous function that sends a request to the register endpoint with the provided user data. It returns a promise that resolves with the registrationFeedback if successful, or notifies any errors encountered during the process.

## registerAdminUser

Input: An object with properties name, email, and password.

Output: The registration feedback from the sendRequest function.

Description: This function is used to register an admin user. It takes an object as input with the admin user's name, email, and password. It then sends a request to the server using the sendRequest function, passing the base user path and the user data in the request body. After receiving the registration feedback, it displays a notification message indicating successful registration and returns the feedback. If an error occurs during the registration process, it displays the error message using the notify function.

## updateUserInformation

Input: updateInformation - the information to be updated

Output: updateFeedback - the feedback from the update request

Description: This function is used to update the user's profile information. It sends a request to the server with the updated information and returns the feedback from the update request. The function also displays a notification message if the update is successful, or notifies the user of any errors that occur during the update process.

## updatePasswordInformation

Input: passwordInformation - the information to update the user's password

Output: updateFeedback - the feedback from the update request

Description: This function is used to update the user's password. It sends a request to the server with the updated password information and returns the feedback from the update request. The function also displays a notification message if the update is successful, or notifies the user of any errors that occur during the update process.

## loginWithInnoSSO

Input: options - an optional object containing additional options for the login request

Output: redirectURL - the URL to redirect the user after successful login

Description: This function is used to login with InnoSSO. It sends a GET request to the specified URL BASE_USER_PATH/login_sso with the provided options. After a successful login, it displays a notification message "Login with sso Successful" and returns the redirect URL.

## getCurrentUser

Input:  accessToken  - an object containing the access token for authentication

Output: userInfo - an object containing the user information

Description: This function is used to retrieve the current user's information. It sends a GET request to the specified URL BASE_USER_PATH/ with the provided access token in the Authorization header. If the request is successful, it returns the user information. Otherwise, it displays an error notification using the notify function.

## getAllRegisteredUsers

Input: None

Output: usersInfo - an object containing information about all registered users

Description: This function is used to retrieve information about all registered users. It first retrieves the access token from the session storage. Then, it sends a GET request to the specified URL ${BASE_USER_PATH}/all with the access token in the Authorization header. If the request is successful, it returns the user information. Otherwise, it displays an error notification using the notify function.

## createPassRequest

Input:  request , options

Output: response

Description: This function is used to create a pass request. It takes an object containing the request data and an optional options object as input. The function first retrieves the access token from the session storage. It then sends a request to the server using the sendRequest function, passing the base pass path and the request data in the body. The function also adds the access token to the headers for authorization. If the request is successful, a notification message is displayed and the response is returned. If there is an error, the error is notified.

## getPassRequestHistory

Input: None

Output: passRequests

Description: This function is used to get the pass request history. It retrieves the access token from the session storage. It then sends a GET request to the server using the sendRequest function, passing the base pass path and the access token in the headers for authorization. The function returns the pass requests received from the server.

## deletePassRequest

Input: passRequestId

Output: response

Description: This function is used to delete a pass request. It retrieves the access token from the session storage. It then sends a DELETE request to the server using the sendRequest function, passing the base pass path and the pass request id in the URL. The access token is included in the headers for authorization. If the request is successful, a notification message is displayed. The function returns the response received from the server. If there is an error, it notifies the error.

## getAllPassRequestAdmin

Input: None

Output: passes

Description: This function is used to get all pass requests for the admin user. It retrieves the access token from the session storage. It then sends a GET request to the server using the sendRequest function, passing the base pass path with "/admin" appended in the URL. The access token is included in the headers for authorization. If the request is successful, it returns the passes received from the server. If there is an error, it notifies the error.

## updatePassRequest

Input: requestId, data

Output: request

Description: This function is used to update a pass request. It retrieves the access token from the session storage. It then sends a PATCH request to the server using the sendRequest function, passing the base pass path with "/?request_id=" and the requestId appended in the URL. The access token is included in the headers for authorization. The data is converted to JSON format and included in the request body. If the request is successful, it notifies the user with a success message and returns the updated request. If there is an error, it notifies the error.

## getAllElectiveCourses

Input: None

Output: electives

Description: This function is used to retrieve all elective courses from the server. It retrieves the access token from the session storage. It then sends a GET request to the server using the sendRequest function, passing the base elective path in the URL. The access token is included in the headers for authorization. If the request is successful, it returns the list of elective courses. If there is an error, it notifies the error.

## getAllElectiveCoursesAdmin

Input: None

Output: electives

Description: This function is used to retrieve all elective courses for an admin user from the server. It retrieves the access token from the session storage. It then sends a GET request to the server using the sendRequest function, passing the base elective path with "/admin" appended to it in the URL. The access token is included in the headers for authorization. If the request is successful, it returns the list of elective courses. If there is an error, it notifies the error.

## getBookedElectiveCourses

Input: None

Output: electives

Description: This function is used to retrieve all booked elective courses for a user from the server. It retrieves the access token from the session storage. It then sends a GET request to the server using the sendRequest function, passing the base elective path with "/booked" appended to it in the URL. The access token is included in the headers for authorization. If the request is successful, it returns the list of booked elective courses. If there is an error, it notifies the error.

## getAllElectiveRequests

Input: None

Output: Promise that resolves to an array of elective requests

Description: This function retrieves all elective requests from the server. It first retrieves the access token from the session storage. Then, it sends a GET request to the server with the access token in the Authorization header. The response is an array of elective requests.

## updateElectiveCourse

Input: Object with courseId and data properties

Output: Promise that resolves to the updated elective course

Description: This function updates an elective course on the server. It first retrieves the access token from the session storage. Then, it sends a PUT request to the server with the courseId as a query parameter and the data in the request body. The access token is included in the Authorization header. If the request is successful, it notifies the user with a success message and returns the updated elective course. If there is an error, it notifies the user with the error message.

## updateElectiveCourseRequest

Input: 
- requestId: The ID of the elective course request to be updated.
- data: The data containing the updated information for the elective course request.

Output: the updated elective course request.

Description: 
This function is used to update an elective course request. It sends a PATCH request to the server with the provided requestId and data. The function retrieves the access token from the sessionStorage and includes it in the Authorization header of the request. The data is serialized as JSON and sent in the request body. If the request is successful, a notification message is displayed. If there is an error, it is caught and displayed using the notify function.

## createElectiveCourse

Input:  data 

Output: elective

Description: This function creates an elective course by sending a request to the server with the provided data. It requires an access token from the session storage to authenticate the request. If the request is successful, it returns the created elective course. Otherwise, it notifies the error.

## bulkUploadElective

Input:  data 

Output: elective

Description: This function performs a bulk upload of elective courses by sending a request to the server with the provided data. It requires an access token from the session storage to authenticate the request. If the request is successful, it returns the uploaded elective courses. Otherwise, it notifies the error.

## deleteElectiveCourse

Input:  courseId 

Output: None

Description: This function deletes an elective course by sending a DELETE request to the server with the provided course ID. It requires an access token from the session storage to authenticate the request. If the request is successful, it notifies the user that the course has been successfully deleted. Otherwise, it notifies the error.

## makeElectiveRequest

Input:  courseId 

Output: response

Description: This function makes a request to the server to request an elective course. It requires a course ID as input. It retrieves an access token from the session storage to authenticate the request. If the request is successful, it notifies the user that the request was successful and is in progress. Otherwise, it notifies the error. The function returns the response from the server.

## deleteElectiveRequest

Input:  courseRequestId 

Output: response

Description: This function makes a request to the server to delete an elective course request. It requires a course request ID as input. It retrieves an access token from the session storage to authenticate the request. If the request is successful, it notifies the user that the request was successfully deleted. Otherwise, it notifies the error. The function returns the response from the server.

## getAdminDonationText

Input: None

Output: message

Description: This function sends a GET request to the server to retrieve the admin donation text. It retrieves an access token from the session storage to authenticate the request. The function returns the message received from the server.

## getAllAlumniDonations

Input: None

Output: Returns a Promise that resolves to the response message from the server.

Description: This function retrieves all alumni donations by making a GET request to the ${BASE_DONATION_PATH} endpoint. It uses the sendRequest function to send the request and includes the access token in the Authorization header. The response message from the server is returned as a Promise.

## upsertAdminDonationText

Input: Object with a donation property

Output: Returns a Promise that resolves to the response message from the server.

Description: This function is used to update or insert an admin donation text. It takes an object as input with a donation property, which contains the updated or new donation text. The function retrieves the access token from the session storage and sends a POST request to the ${BASE_DONATION_PATH}/admin endpoint. The request includes the access token in the Authorization header and the donation object as the request body, which is converted to a JSON string using JSON.stringify(). If the request is successful, a notification is displayed with the message "Donation Request Updated Successful" and the response message from the server is returned as a Promise. If there is an error, the error is notified.

## makeDonationText

Input: Object with a donation property

Output: Returns a Promise that resolves to the response from the server.

Description: This function is used to send a donation interest to the server. It takes an object as input with a donation property, which contains the donation information. The function retrieves the access token from the session storage and sends a POST request to the ${BASE_DONATION_PATH}/ endpoint. The request includes the access token in the Authorization header and the donation object as the request body, which is converted to a JSON string using JSON.stringify(). If the request is successful, a notification is displayed with the message "Donation Interest Sent Successful" and the response from the server is returned as a Promise. If there is an error, the error is notified.

## sendRequest

Input: 
- path: the path for the request
- options: optional object containing additional request options

Output: a promise that resolves to the response data in JSON format

Description: 
This function is used to send a POST request to a specified path with optional request options. It handles setting the appropriate headers, including the "Content-Type" header as "application/json; charset=UTF-8" unless the "Remove-Content-Type" header is present in the options. The function also includes the "credentials" option set to "include" to include cookies in the request.

If the response is not successful (response.ok is false), the function throws an error with the detailed error message obtained from the response data. It also displays a notification message using the notify function. If the response is successful, the function parses the response data as JSON and returns it.