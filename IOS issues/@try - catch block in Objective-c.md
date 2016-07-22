#@try - catch block in Objective-c
	
	NSString *test = @"test";
	    unichar a;
	    int index = 5;
	
	    @try {
	        a = [test characterAtIndex:index];
	    }
	    @catch (NSException *exception) {
	        NSLog(@"%@", exception.reason);
	    }
	    @finally {
	        NSLog(@"Char at index %d cannot be found", index);
	        NSLog(@"Max index is: %d", [test length]-1);
	    }