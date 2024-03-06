# Utils

## send_email 
It is used to send an email. It takes the following parameters:
- background_tasks: A BackgroundTasks object used to run tasks in the background
- subject: The subject of the email
- email_to: The recipient's email address
- body: A dictionary containing the email body data
- template_name: The name of the email template to use

Inside the function, a MessageSchema object named message is created with the following attributes:
- subject: The subject of the email
- recipients: A list of recipient email addresses
- template_body: The body of the email (HTML content)
- subtype: The subtype of the email (set to 'html')

The config object is printed, and a FastMail object named fm is created using the config object.

Finally, a task is added to the background_tasks object to send the email using the send_message method of the fm object and the specified template name.

## hash_password

Input: password (string)

Output: hashed password (string)

Description: This function takes a plain text password as input and returns the hashed version of the password using the pwd_ctx.hash method.

## verify_password

Input: plain_password (string), hashed_password (string)

Output: boolean

Description: This function takes a plain text password and a hashed password as input and verifies if the plain text password matches the hashed password using the pwd_ctx.verify method. It returns a boolean value indicating whether the passwords match or not.

## get_current_user

Input: token (string)

Output: user (object)

Description: This function retrieves the current user based on the provided token. It first verifies the access token using the verify_access_token function and throws an HTTPException with a status code of 401 if the credentials are not valid. If the credentials are valid, it queries the database to find the user with the matching email and returns the user object.

## RoleChecker

Input: allowed_roles (List of strings)

Output: None

Description: This class is used for checking if a user has the required role to perform a certain operation. It has an init method that initializes the allowed_roles attribute with the provided list of roles. It also has a call method that takes a user object as an argument, which is obtained from the get_current_user function. If the user's role is not in the allowed_roles list, it raises an HTTPException with a status code of 403 and a detail message of "Unauthorized [Role] - Operation not permitted".

## create_access_token

Input: data (dict), expires_delta (Optional[timedelta])

Output: encoded_jwt (str)

Description: This function is used to create an access token. It takes in a dictionary of data and an optional timedelta object representing the expiration time for the token. If expires_delta is provided, the token will expire after the specified time. Otherwise, it will expire after a default time of ACCESS_TOKEN_EXPIRE_MINUTES minutes. The function copies the data dictionary, adds the expiration time to it, encodes the dictionary into a JWT using the SECRET_KEY and ALGORITHM, and returns the encoded JWT.

## verify_access_token

Input: token (str), credentials_exception

Output: email (str)

Description: This function is used to verify an access token. It takes in a token string and a credentials_exception object. It decodes the token using the SECRET_KEY and ALGORITHM, retrieves the email from the decoded payload, and checks if it is None. If the email is None, it raises the credentials_exception. If there is any error decoding the token, it also raises the credentials_exception. Otherwise, it returns the email.

## generate_user_verification_code

Input: None

Output: code (str)

Description: This function is used to generate a user verification code. It generates a unique UUID using uuid.uuid1(), converts it to a string, splits it by "-" and retrieves the first part, and returns it as the verification code.