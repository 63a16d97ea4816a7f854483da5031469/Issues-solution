#Check whether the string contain some kinds of characters:

http://stackoverflow.com/questions/1671605/how-to-check-if-a-string-only-contains-alphanumeric-characters-in-objective-c


	NSCharacterSet *alphanumericSet = [NSCharacterSet characterSetWithCharactersInString:@"abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ1234567890"];
	NSString *result = [self stringByTrimmingCharactersInSet:alphanumericSet];
	
	return [result isEqualToString:@""];