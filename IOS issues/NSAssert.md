NSAssert

http://iosdevelopertips.com/debugging/working-with-assertions.html

NSAssert and its kin – NSAssert1, NSAssert2, etc – are used inside methods. NSAssert is defined as follows:

#define NSAssert(condition, desc)

condition is the expression we are interested to evaluate and desc is the message displayed on the console when the assertion fails.

Looking a little further, in NSException.h we can see the full definition:

	#define NSAssert(condition, desc, ...) \
	    do {			\
		if (!(condition)) {	\
		    [[NSAssertionHandler currentHandler] handleFailureInMethod:_cmd \
			object:self file:[NSString stringWithUTF8String:__FILE__] \
		    	lineNumber:__LINE__ description:(desc), ##__VA_ARGS__]; \
		}			\
	    } while(0)