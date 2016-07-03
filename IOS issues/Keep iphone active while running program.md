#Keep iphone active while running program

http://stackoverflow.com/questions/493495/keep-iphone-active-while-running-program

	// avoid sleeping when this application is running
	UIApplication *application = [UIApplication sharedApplication];
	application.idleTimerDisabled = YES;
	// Or simpler
	[[UIApplication sharedApplication] setIdleTimerDisabled: YES];