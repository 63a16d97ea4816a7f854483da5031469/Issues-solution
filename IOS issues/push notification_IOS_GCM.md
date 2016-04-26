#Push Notification

https://developers.google.com/mobile/add?platform=ios&cntapi=gcm&cntapp=Default%20Demo%20App&cnturl=https:%2F%2Fdevelopers.google.com%2Fcloud-messaging%2Fios%2Fstart%3Fconfigured%3Dtrue&cntlbl=Continue%20with%20Try%20Cloud%20Messaging

Development APNS Certificate (P12 format)

http://quickblox.com/developers/How_to_create_APNS_certificates





 



Uploading APNS Certificate for Google Service Configuration

<font color="red">Has issue: The certificate environment did not match. Ensure that you got the right development or production APNS certificate.</font>

I had the same issue and here's what I did to solve.

The issue was because I generate both Development APNS Certificate and Production APNS Certificate using the same certificate signing request file (the file that you got from Keychain Access > Certificate Assistant > Request a Certificate From a Certificate Authority). Apparently, the certificate signing request file should not be the same.

<font color="green">To solve this problem:

Create a new certificate signing request (Keychain Access > Certificate Assistant > Request a Certificate From a Certificate Authority)
From the Push Notification section of your app, Create Certificate using the .certSigningRequest file you just created
Re-upload the .p12 to GCM
</font>




####After everything is fine, but could not receive the message:

Need to modify the project''s settings:
(1)Capabilities:  Push notification
(2)Background Modes: Remote notification






