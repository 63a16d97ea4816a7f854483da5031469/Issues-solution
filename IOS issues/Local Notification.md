##Local Notification

http://www.thekspace.com/home/component/content/article/62-uilocalnotification-demystified.html







###Cancelling notifications
If your app requires cancelling any scheduled notification or notifications, you can do it by either
Cancelling all notifications that are associated to your application

You can use the following method to cancel all scheduled notifications

	[[UIApplication sharedApplication] cancelAllLocalNotifications];
 
###Cancel a particular notification

The iOS allows cancelling a specific notification using the following method, but you have to somehow obtain the notification object first.

	[[UIApplication sharedApplication] cancelLocalNotification:localNotification];
 
The question is how to retrieve the correct notification object that we want to cancel.

###Retrieve existing scheduled notification

You can get all scheduled notifications associated to your app, and then walk through them to identify the one (e.g. using the an ID you set it before) you want to cancel.

	NSArray* localNotifications = [[UIApplication sharedApplication] 
	                                              scheduledLocalNotifications];
	for (UILocalNotification *notification in localNotifications)
	{
	    NSString* notificationID = [notification.userInfo objectForKey:@"IDkey"];
	    if([notificationID isEqualToString:@"1234"])
	    {
	        [[UIApplication sharedApplication] cancelLocalNotification:notification];
	    }
	}
