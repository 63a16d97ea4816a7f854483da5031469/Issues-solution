# IOS issues

###iOS 9 Xcode 7 - Application appears with black bars on top and bottom

>* Errors get from the xcode:  

>> An error occured : Error Domain=NSURLErrorDomain Code=-1022 "The resource could not be loaded because the App Transport Security policy requires the use of a secure connection." 

>>Error Domain=NSURLErrorDomain Code=-1200 "An SSL error has occurred and a secure connection to the server cannot be made.  
>CFNetwork SSLHandshake failed (-9824)

http://stackoverflow.com/questions/32641240/ios-9-xcode-7-application-appears-with-black-bars-on-top-and-bottom

**My App does not use a launch image. Setting the "Launch Screen File" to my "main.storyboard" file fixed the issue for me.**

This setting can be found under "Target->General->App Icons and Launch Images"

Use the following link for more information: http://oleb.net/blog/2014/08/replacing-launch-images-with-storyboards/


###The resource could not be loaded because the App Transport Security policy requires the use of a secure connection

	 <key>NSAppTransportSecurity</key>  
	  <dict>  
 	   <key>NSAllowsArbitraryLoads</key>  
 	   <true/>  
 	  </dict>  
  