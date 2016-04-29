#how to convert a unix timestamp into nsdate in iphone

http://stackoverflow.com/questions/14134268/how-to-convert-a-unix-timestamp-into-nsdate-in-iphone

	NSDate *dateTraded = [NSDate dateWithTimeIntervalSince1970 :[[updates objectForKey:@"timestamp"] integerValue]];
	
	
	dateWithTimeIntervalSince1970:  ---> unit: seconds.