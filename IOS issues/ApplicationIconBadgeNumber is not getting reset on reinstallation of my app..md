##ApplicationIconBadgeNumber is not getting reset on reinstallation of my app.

application.applicationIconBadgeNumber = 0;


Launch to remove the number:

	- (void)applicationWillEnterForeground:(UIApplication *)application {
	    [[NSNotificationCenter defaultCenter] postNotificationName:@"beginSearching" object:nil];
	    application.applicationIconBadgeNumber = 0;
	    // Called as part of the transition from the background to the inactive state; here you can undo many of the changes made on entering the background.
	}
	
	
	