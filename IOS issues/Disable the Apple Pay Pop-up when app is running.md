#Disable the Apple Pay Pop-up when app is running

http://stackoverflow.com/questions/32945213/disable-apple-pay-ui-when-13-56mhz-detection

After opening a private query to the Apple Developer Technical Support (DTS) they told me I had to request a specific entitlement for this purpose via email. In that email I had to justify why should I use this PassKit functionality and how would it be utilized.

Once they made this entitlement available (after some weeks) it was just enough to add it to our provisioning profiles and the requestAutomaticPassPresentationSuppressionWithResponseHandler method would work without any problem.

More details from Apple:
https://developer.apple.com/support/technical/