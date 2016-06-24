#Applications are expected to have a root view controller at the end of application launch

Replace in AppDelegate

	 [window addSubview:[someController view]];
	to
	
	  [self.window setRootViewController:someController];
