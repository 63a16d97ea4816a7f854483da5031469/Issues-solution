#Working With Background Fetch in iOS 7

http://www.appcoda.com/ios7-background-fetch-programming/




####Best One:

http://hayageek.com/ios-background-fetch/

<img src="iOS Background Fetch example.png"/>


#####Another:
http://blog.csdn.net/jymn_chen/article/details/19143533




It is not specified by Apple how long UIApplicationBackgroundFetchIntervalMinimum time is, however in practice it is around 10 minutes for iOS 6.


More details:

http://stackoverflow.com/questions/22061897/background-fetch-calling-once-ios7



	-(BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
	{
	    [[UIApplication sharedApplication] setMinimumBackgroundFetchInterval:UIApplicationBackgroundFetchIntervalMinimum];
	
	    return YES;
	}
	
The default value is UIApplicationBackgroundFetchIntervalNever, so if you fail to set the value on launching, your app will never be woken up to perform background fetches. The value you provide is the minimum number of seconds between wakes; do note, however, that the value is merely advisory—your application may perform fetches less or more often.

Setting UIApplicationBackgroundFetchIntervalMinimum will ensure your application is called as regularly as possible, but in reality the system will decide ultimately.