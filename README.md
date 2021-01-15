# auth-buster
This project should be run as its own service. It will be a node + Postgress API that only does authentication. It will handle scenarios (not limited to):
- Registeration
- Login
- Login Security in many degrees
- Confirm email address
- Forgot password
- Password reset
- Verify user/token

It could also have a super basic UI as a utility to view all users and do the following:
- Create new user
- Edit user (except password)
- Send password reset link
- Delete user
- View all users and search, gather analytics- last login, etc.
- Kill an active token

### Some ideas:
- When you register, save the zone/location you registered from, and when you login verify that you are logging in from that zone. Protects from hackers in Russia or China hacking you. Could be totally optional and passed into the config objects for register and login. If login is from different zone, send back a 403 with the message to verify their email address before logging in. 
- Having a config for most of the auth methods would be good, for example `verifyToken` could be a super shallow check if thats all the consumer wants, or it could be super in-depth.
- Users have a JSON item called "properties" since POSTGRES can store JSON in a table value.
- b/c we will be sending emails for verifying users for actions as well as password reset, we will need to integrate w/ the sendgrid API and have the consumer provide sendgrid environment vars.
- The consumer will basically need to send in a bunch of props as environment vars to init the service.
