##Missing Push Notification Entitlement apple --> How to enable the Push Notification Entitlement for your app.

By using this way, we can remove the warnings from Itunes Connect sent to Email address.

http://stackoverflow.com/questions/27945557/missing-push-notification-entitlement-warning/32637556#32637556

SOLVED!

You need to see 2 things: The provisioning profiles used by your account on Xcode and the ones on developer.apple

Its all about the provisioning profiles.

STEP 1: Go to https://developer.apple.com/account/ios/profile/profileList.action and see the Active iOS Distribution Provisioning Profiles you need for your app. Then click on it and make sure Enabled Services has Push Notification enabled. If it doesn't then click on edit and enable it by following the steps provided by Apple. If it is enabled then perfect.

STEP 2: Delete any Invalid Provisioning Profiles you see related to app (just the invalid ones for YOUR app). I'll tell you why in the following steps.

STEP 3: Go to Xcode -> Preference -> View Details (for your Account) -> Click refresh like 3-4 times to be on a safer side. This will remove the invalid provisioning profile locally. Click DONE.

STEP 4: Go to your app Targets -> Build Settings -> In Code Signing, expand your Provisioning Profile to show Debug and Release tabs. By default it will be on Automatic (which is why your app was probably automatically using the invalid profile that we just deleted in step 2). For Release, to be on a safer side, select the Active Provisioning Profile with enabled Push Notifications as seen on step 1.

That's it.