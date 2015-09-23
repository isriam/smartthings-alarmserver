first go here and put in client id from oauth from smartapp
https://graph.api.smartthings.com/oauth/authorize?response_type=code&redirect_uri=http://localhost&scope=app&client_id=$clientid

copy the url
http://localhost/?code=$code

use this url with client id, secret oauth key, and code
https://graph.api.smartthings.com/oauth/token?grant_type=authorization_code&scope=app&redirect_uri=http://localhost&client_id=$clientid&client_secret=$clientsecret&code=$code

save access token, it is for the authentication
{"access_token":"7871b079-5392-4eef-a382-83fa3a3face3","token_type":"bearer","expires_in":1576799999,"scope":"app"}

Go to this url and get smartapp ID
https://graph.api.smartthings.com/api/smartapps/installations

Get all the contact sensor id's and switch id's.

alarmserver.cfg

zone closed
zoneclose1=https://graph.api.smartthings.com/api/smartapps/installations/$appid/contactsensors/$sensorid/closed?access_token=$access-token

zone open
zoneopen1=https://graph.api.smartthings.com/api/smartapps/installations/$appid/contactsensors/$sensorid/open?access_token=$access-token
