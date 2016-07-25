#Setup Local Notification

Below code is able to work under <font color =blue>IOS 9.2 </font>

####AppDelegate:

	 [launchOptions valueForKey:UIApplicationLaunchOptionsLocalNotificationKey];
	    
	    if ([UIApplication instancesRespondToSelector:@selector(registerUserNotificationSettings:)])
	    {
	        
	        [application registerUserNotificationSettings:[UIUserNotificationSettings
	                                                       settingsForTypes:UIUserNotificationTypeAlert|UIUserNotificationTypeBadge|
	                                                       UIUserNotificationTypeSound categories:nil]];
	    }
	    
	    
	    UILocalNotification *notification = [launchOptions objectForKey:UIApplicationLaunchOptionsLocalNotificationKey];
	 	
	//added new method for Local Notification: --begin
	- (void)application:(UIApplication *)application didReceiveLocalNotification:(UILocalNotification *)notification {
	//    NSDictionary *infoDict = notification.userInfo;
	    
	    [self showAlarm:@"Info" MessageBody:notification.alertBody];
	
	    application.applicationIconBadgeNumber = 0;
	    NSLog(@"AppDelegate didReceiveLocalNotification %@", notification.userInfo);
	}
	
	- (void)showAlarm:(NSString*)titleText MessageBody:(NSString *)text {
	    UIAlertView *alertView = [[UIAlertView alloc] initWithTitle:titleText
	                                                        message:text delegate:nil
	                                              cancelButtonTitle:@"OK"
	                                              otherButtonTitles:nil];
	    [alertView show];
	}
	//added new method for Local Notification: --end
	
	    
	    
####In the view you want to post the local notification:

	
	- (void)setupLocalNotificationsForReminder{
	    
	    NSLog(@"setup local notification!");
	    
	    UILocalNotification *localNotification = [[UILocalNotification alloc] init];
	    
	    NSDate *now = [NSDate date];
	    now= [now dateByAddingTimeInterval:10];
	    
	    localNotification.fireDate = now;
	    NSString* myalertMessage=[NSString stringWithFormat:@"Help"];
	    localNotification.alertBody = myalertMessage;
	    localNotification.soundName = UILocalNotificationDefaultSoundName;
	        [UIApplication sharedApplication].applicationIconBadgeNumber++;
	    
	    //    localNotification.applicationIconBadgeNumber = [[UIApplication sharedApplication] applicationIconBadgeNumber]+1;
	    
	    //Can use userInfo to save some Parameters
	//    NSDictionary *infoDict = [NSDictionary dictionaryWithObjectsAndKeys:@"wifi", @"wifi",nil];
	//    localNotification.userInfo = infoDict;
	 
	        [[UIApplication sharedApplication] scheduleLocalNotification:localNotification];
	
	}
		    
	    