# Telegram

## Controllers

- get_user(user_id): Retrieves a user from the database based on their Telegram ID.
- get_full_user(user_id): Retrieves a user from the database based on their Telegram ID, including their pass and course requests.
- register_user(user_id, email="", fullname="", handle=""): Creates a new user in the database with the provided Telegram ID, email, full name, and handle.
- update_user(user_id, email="", fullname="", handle=""): Updates the information of a user in the database based on their Telegram ID, including their email, full name, and handle.
- update_user_alias(user_id, handle): Updates the handle (alias) of a user in the database based on their Telegram ID.
- get_user_with_settings(user_id): Retrieves a user from the database based on their Telegram ID.
- get_user_with_course(user_id): Retrieves a user from the database based on their Telegram ID, including their course requests.
- print_request(request): Generates a formatted string representation of a request's details.
- print_request_result(request): Generates a formatted string representation of the result of a request.
- get_pass_request(user_id): Retrieves pass requests made by a user from the database based on their Telegram ID.
- get_course_request(user_id): Retrieves course requests made by a user from the database based on their Telegram ID, including elective course details.
- get_pass_request_by_id(request_id): Retrieves a pass request from the database based on its ID.
- get_course_request_by_id(request_id): Retrieves a course request from the database based on its ID.
- clear_pass_request_history(user_id): Deletes pass requests with "APPROVED" or "REJECTED" status made by a user from the database based on their Telegram ID.
- clear_course_request_history(user_id): Deletes course requests with "APPROVED" or "REJECTED" status made by a user from the database based on their Telegram ID.
- update_user_courses(user_id, course_id): Updates the courses of a user in the database based on their Telegram ID, connecting a new course based on its Telegram ID.
- get_pending_elective_request(user_id): Retrieves pending elective course requests made by a user from the database based on their Telegram ID, including elective course details.
- get_pending_pass_requests(user_id): Retrieves pending pass requests made by a user from the database based on their Telegram ID, including user details.

- clear_pending_elective_request(user_id): Deletes pending elective course requests made by a user from the database based on their Telegram ID.
- get_elective_courses(): Retrieves all elective courses from the database.
- get_elective_by_name(elective_name): Retrieves an elective course from the database based on its name.
- request_elective(elective, user_id): Creates a new elective course request in the database with the provided elective name and user ID.
- clear_elective_courses(user_id, ids_to_disconnect): Updates the courses of a user in the database based on their Telegram ID, disconnecting the specified elective course IDs.
- get_electives(user_id): Retrieves the elective courses of a user from the database based on their Telegram ID.
- request_pass(requested_date, description, user_id): Creates a new pass request in the database with the provided requested date, description, and user ID.
- approve_pass_request(request_id, feedback): Updates the status of a pass request in the database to "APPROVED" and adds feedback, based on the request ID.
- approve_course_request(request_id, feedback): Updates the status of a course request in the database to "APPROVED" and adds feedback, based on the request ID.
- reject_pass_request(request_id, feedback): Updates the status of a pass request in the database to "REJECTED" and adds feedback, based on the request ID.
- reject_course_request(request_id, feedback): Updates the status of a course request in the database to "REJECTED" and adds feedback, based on the request ID.
- get_pending_pass_request(user_id): Retrieves pending pass requests made by a user from the database based on their Telegram ID.
- delete_pending_pass_request(user_id): Deletes pending pass requests made by a user from the database based on their Telegram ID.