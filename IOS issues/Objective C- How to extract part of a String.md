#Objective C: How to extract part of a String (e.g. start with '#')


http://stackoverflow.com/questions/6825834/objective-c-how-to-extract-part-of-a-string-e-g-start-with


	[aString substringWithRange:NSMakeRange(13, 10)] 
	would give you substring1
	
	You can calculate the range using:
	
	NSRange startRange = [aString rangeOfString:@"#"];
	NSRange endRange = [original rangeOfString:@"1"];
	
	NSRange searchRange = NSMakeRange(startRange.location , endRange.location);
	[aString substringWithRange:searchRange] 