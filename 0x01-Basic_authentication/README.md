Project: Basic authentication
Author: Samuel Atiemo

Project Tasks:

0. Simple-basic-API
mandatory

1. Error handler: Unauthorized
mandatory
What the HTTP status code for a request unauthorized? 401 of course!

2. Error handler: Forbidden
mandatory
What the HTTP status code for a request where the user is authenticate but not allowed to access to a resource? 403 of course!

3. Auth class
mandatory
Now you will create a class to manage the API authentication.

4. Define which routes don't need authentication
mandatory
Update the method def require_auth(self, path: str, excluded_paths: List[str]) -> bool: in Auth that returns True if the path is not in the list of strings excluded_paths:

5. Request validation!
mandatory
Now you will validate all requests to secure the API:

Update the method def authorization_header(self, request=None) -> str: in api/v1/auth/auth.py:
6. Basic auth
mandatory
Create a class BasicAuth that inherits from Auth. For the moment this class will be empty.

7. Basic - Base64 part
mandatory
Add the method def extract_base64_authorization_header(self, authorization_header: str) -> str: in the class BasicAuth that returns the Base64 part of the Authorization header for a Basic Authentication:

8. Basic - Base64 decode
mandatory
Add the method def decode_base64_authorization_header(self, base64_authorization_header: str) -> str: in the class BasicAuth that returns the decoded value of a Base64 string

9. Basic - User credentials
mandatory
Add the method def extract_user_credentials(self, decoded_base64_authorization_header: str) -> (str, str) in the class BasicAuth that returns the user email and password from the Base64 decoded value.

10. Basic - User object
mandatory
Add the method def user_object_from_credentials(self, user_email: str, user_pwd: str) -> TypeVar('User'): in the class BasicAuth that returns the User instance based on his email and password.

11. Basic - Overload current_user - and BOOM!
mandatory
Now, you have all pieces for having a complete Basic authentication.

12. Basic - Allow password with ":"
#advanced
Improve the method def extract_user_credentials(self, decoded_base64_authorization_header) to allow password with :.

13. Require auth with stars
#advanced
Improve def require_auth(self, path, excluded_paths) by allowing * at the end of excluded paths.


