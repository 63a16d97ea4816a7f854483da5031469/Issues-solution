#Generate Random Name String

	NSString *alphabet  = @"abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXZY0123456789";
	NSMutableString *s = [NSMutableString stringWithCapacity:20];
	for (NSUInteger i = 0U; i < 20; i++) {
	    u_int32_t r = arc4random() % [alphabet length];
	    unichar c = [alphabet characterAtIndex:r];
	    [s appendFormat:@"%C", c];
	}