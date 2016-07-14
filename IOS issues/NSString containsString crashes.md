#NSString containsString crashes


Are you running on an iOS lower than 8? The containsString: method was only added in iOS 8


	- (BOOL)containsString:(NSString *)str NS_AVAILABLE(10_10, 8_0);
	
	
	#define NS_AVAILABLE(_mac, _ios) CF_AVAILABLE(_mac, _ios)
	
Solution:
compare rangeOfString with NSNotFound

	NSRange range = [self rangeOfString:other];
	if(range.location != NSNotFound){
	    //do something
	}