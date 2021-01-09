# auth-buster

Some ideas:
- When you register, save the zone/location you registered from, and when you login verify that you are logging in from that zone. Protects from hackers in Russia or China hacking you. Could be totally optional and passed into the config objects for register and login. If login is from different zone, send back a 403 with the message to verify their email address before logging in. 
- Having a config for most of the auth methods would be good, for example `verifyToken` could be a super shallow check if thats all the consumer wants, or it could be super in-depth.
