#How to check if NSString begins with a certain character

http://stackoverflow.com/questions/2503436/how-to-check-if-nsstring-begins-with-a-certain-character


	Objective-C:
	
	NSString* output = nil;
	if([string hasPrefix:@"*"]) {
	    output = [string substringFromIndex:1];
	}
	Swift:
	
	var output:String?
	if string.hasPrefix("*") {
	    output = string.substringFromIndex(string.startIndex.advancedBy(1))
	}