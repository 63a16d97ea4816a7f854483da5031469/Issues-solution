#Objective-C - Finding a URL within a string

RegexKitLite
http://regexkit.sourceforge.net/RegexKitLite/

http://stackoverflow.com/questions/5998969/objective-c-finding-a-url-within-a-string

I'd use RegexKitLite for this:

	\#import "RegExKitLite.h"
	NSString * urlString = @"blah blah blah http://www.google.com blah blah blah http://www.stackoverflow.com blah blah balh http://www.apple.com";
	NSArray *urls = [urlString componentsMatchedByRegex:@"http://[^\\s]*"];
	NSLog(@"urls: %@", urls);


Prints:

	urls: (
	    "http://www.google.com",
	    "http://www.stackoverflow.com",
	    "http://www.apple.com"
	)