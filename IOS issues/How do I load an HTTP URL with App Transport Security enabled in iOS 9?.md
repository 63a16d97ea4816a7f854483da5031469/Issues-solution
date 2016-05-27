#How do I load an HTTP URL with App Transport Security enabled in iOS 9? [duplicate]

From Apple's document:  
https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/

All connections using the NSURLConnection, CFURL, or NSURLSession APIs use App Transport Security default behavior in apps built for iOS 9.0 or later, and OS X v10.11 or later. Connections that do not follow the requirements will fail. For more information on various the connection methods, see NSURLConnection Class Reference, CFURL Reference, or NSURLSession Class Reference.

	 <key>NSAppTransportSecurity</key>  
	  <dict>  
 	   <key>NSAllowsArbitraryLoads</key>  
 	   <true/>  
 	  </dict>  
