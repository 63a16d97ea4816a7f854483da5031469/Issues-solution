# UILocalNotification issue with iOS9

http://stackoverflow.com/questions/32901918/uilocalnotification-issue-with-ios9


	- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
	{
	// Override point for customization after application launch.
	
	[launchOptions valueForKey:UIApplicationLaunchOptionsLocalNotificationKey];
	
	if ([UIApplication instancesRespondToSelector:@selector(registerUserNotificationSettings:)])
	{
	
	    [application registerUserNotificationSettings:[UIUserNotificationSettings
	                                                   settingsForTypes:UIUserNotificationTypeAlert|UIUserNotificationTypeBadge|
	                                                   UIUserNotificationTypeSound categories:nil]];
	}
	
	return YES;