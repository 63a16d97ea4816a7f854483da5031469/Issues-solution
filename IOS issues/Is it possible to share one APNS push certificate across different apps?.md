#Is it possible to share one APNS push certificate across different apps?

http://stackoverflow.com/questions/26445719/is-it-possible-to-share-one-apns-push-certificate-across-different-apps

Unfortunately no, you need to create a Push Certificate for each app you make if you are planning to have push notifications in your app.

The reason for this is because each APNS certificate is tied to a specific application so that only that certificate is verified by Apple to connect to Apple Push Notification Services to send notifications to that specific app.

Here is a simple guide on how to create a push notification certificate.

http://quickblox.com/developers/How_to_create_APNS_certificates