#NSString to UTF8String error when contains chinese character

	NSString *tempStr = [NSString stringWithUTF8String:[[NSString stringWithFormat:@"%s",newCStr] UTF8String]];
	
	
	