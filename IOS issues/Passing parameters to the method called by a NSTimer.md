#Passing parameters to the method called by a NSTimer

You can pass your arguments with userInfo:[NSDictionary dictionaryWithObjectsAndKeys:parameterObj1, @"keyOfParameter1"];

A simple example:

	[NSTimer scheduledTimerWithTimeInterval:3.0
	                                 target:self
	                               selector:@selector(handleTimer:)
	                               userInfo:@{@"parameter1": @9}
	                                repeats:NO];
	
	- (void)handleTimer:(NSTimer *)timer {
	    NSInteger parameter1 = [[[timer userInfo] objectForKey:@"parameter1"] integerValue];
	}