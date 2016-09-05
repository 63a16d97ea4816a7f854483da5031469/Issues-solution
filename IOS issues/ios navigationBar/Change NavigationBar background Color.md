#Change NavigationBar background Color

	NSArray *ver = [[UIDevice currentDevice].systemVersion componentsSeparatedByString:@"."];
	if ([[ver objectAtIndex:0] intValue] >= 7) {
	    // iOS 7.0 or later   
	    self.navigationController.navigationBar.barTintColor = [UIColor redColor];
	    self.navigationController.navigationBar.translucent = NO;
	}else {
	    // iOS 6.1 or earlier
	    self.navigationController.navigationBar.tintColor = [UIColor redColor];
	}