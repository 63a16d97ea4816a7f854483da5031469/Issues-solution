#Get UDID of your IPhone


http://stackoverflow.com/questions/31652359/get-udid-of-ios-device-programmatically

NSString* Identifier = [[[UIDevice currentDevice] identifierForVendor] UUIDString]; // IOS 6+
  NSLog(@"output is : %@", Identifier);
additional reference

Apple is apparently starting to remove access to the UDID (Unique Device IDentifier) in iOS5. In any event, the best you can now do for identification purposes is to use a UUID (Universally Unique IDentifier). This has to be on a per-app basis. That is, there is no way to identify the device any longer, but you can identify an app on a device.As long as the user doesn’t completely delete the app, then this identifier will persist between app launches, and at least let you identify the same user using a particular app on a device. Unfortunately, if the user completely deletes and then reinstalls the app then the ID will change, but this is the best anyone can do going forward.





	https://github.com/theiostream/lockdown-uiduid



	http://iphonedevwiki.net/index.php/Lockdownd

lockdownd is a daemon that provides system information to clients using liblockdown.dylib, e.g. the IMEI, UDID, etc. Every information provided by lockdownd can be obtained via other means, e.g. the IMEI can be found using IOKit. The only advantage of using lockdownd is it has root privilege, hence avoiding having to assume super user.
See also LibMobileGestalt.dylib (which you should use if you need a device's UDID).



/usr/libexec/lockdownd
The lockdown daemon, always running on the iPhone, in charge of monitoring activation status, Carrier Debug status, and FairPlay stuff, amongst other things.

For more information, see lockdownd on iPhoneDevWiki.



####Download the lockdownd:
	https://github.com/kennytm/iphone-private-frameworks/blob/master/liblockdown.h


	https://github.com/kennytm/iphone-private-frameworks/tree/master

