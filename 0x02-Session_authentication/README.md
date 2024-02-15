Project: Session authentication
Author: Samuel Atiemo

Project Tasks:

0. Et moi et moi et moi!
mandatory
Copy all your work of the 0x06. Basic authentication project in this new folder.

1. Empty session
mandatory
Create a class SessionAuth that inherits from Auth. For the moment this class will be empty. It’s the first step for creating a new authentication mechanism:

2. Create a session
mandatory
Update SessionAuth class:

Create a class attribute user_id_by_session_id initialized by an empty dictionary

3. User ID for Session ID
mandatory
Update SessionAuth class:

Create an instance method def user_id_for_session_id(self, session_id: str = None) -> str: that returns a User ID based on a Session ID:

4. Session cookie
mandatory
Update api/v1/auth/auth.py by adding the method def session_cookie(self, request=None): that returns a cookie value from a request:

5. Before request
mandatory
Update the @app.before_request method in api/v1/app.py:

6. Use Session ID for identifying a User
mandatory
Update SessionAuth class:

7. New view for Session Authentication
mandatory
Create a new Flask view that handles all routes for the Session authentication.

8. Logout
mandatory
Update the class SessionAuth by adding a new method def destroy_session(self, request=None): that deletes the user session / logout:

9. Expiration?
#advanced
Actually you have 2 authentication systems:

10. Sessions in database
#advanced
Since the beginning, all Session IDs are stored in memory. It means, if your application stops, all Session IDs are lost.




