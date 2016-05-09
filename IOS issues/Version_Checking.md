#Version Checking

	-(BOOL) needsUpdate{
	    NSDictionary* infoDictionary = [[NSBundle mainBundle] infoDictionary];
	    NSString* appID = infoDictionary[@"CFBundleIdentifier"];
	    NSLog(@"the appId:%@",appID);
	    NSURL* url = [NSURL URLWithString:[NSString stringWithFormat:@"http://itunes.apple.com/lookup?bundleId=%@", appID]];
	    NSData* data = [NSData dataWithContentsOfURL:url];
	    NSDictionary* lookup = [NSJSONSerialization JSONObjectWithData:data options:0 error:nil];
	    
	    if ([lookup[@"resultCount"] integerValue] == 1){
	        NSString* appStoreVersion = lookup[@"results"][0][@"version"];
	        NSString* currentVersion = infoDictionary[@"CFBundleShortVersionString"];
	        NSLog(@"the app store version:%@  the current version:%@",appStoreVersion,currentVersion);
	        if (![appStoreVersion isEqualToString:currentVersion]){
	            NSLog(@"Need to update [%@ != %@]", appStoreVersion, currentVersion);
	            return YES;
	        }
	    }
	    return NO;
	}
	
Another solution:	
###https://github.com/apptality/ATAppUpdater#installation