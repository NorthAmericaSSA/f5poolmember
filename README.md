# f5poolmember
December 2020
Peter Scheffler / Peter Maranian

This will generate a compatible cookie to the one added by BIG-IP 'normally'
The client can read this cookie (stored as a Response Cookie), 
decrypt it,
base64 decode it,
and then add that as a cookie called BIGipServer<pool> which should exist on
the request already.  If need be, we can add the pool name to the cookie data
before encrypting.

The client application will need the AES key here in order to decrypt the traffic

Note:
Currently when the BIGipServer<pool> cookie is NOT encrypted the application
simply takes the information and adds it as a cookie.
All we are doing is encrypting this with a shared key
