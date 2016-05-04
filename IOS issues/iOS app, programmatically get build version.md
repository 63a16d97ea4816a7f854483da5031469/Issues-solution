#iOS app, programmatically get build version

	NSDictionary *infoDictionary = [[NSBundle mainBundle]infoDictionary];
	
	NSString *version = infoDictionary[@"CFBundleShortVersionString"];
	NSString *build = infoDictionary[(NSString*)kCFBundleVersionKey];
	NSString *bundleName = infoDictionary[(NSString *)kCFBundleNameKey]; 