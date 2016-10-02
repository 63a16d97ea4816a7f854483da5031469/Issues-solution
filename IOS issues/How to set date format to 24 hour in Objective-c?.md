#How to set date format to 24 hour in Objective-c?

	NSDateFormatter* dateFormatter = [[NSDateFormatter alloc] init];
	NSLocale *locale = [[NSLocale alloc] initWithLocaleIdentifier:@"en_GB"];
	[dateFormatter setLocale:locale];