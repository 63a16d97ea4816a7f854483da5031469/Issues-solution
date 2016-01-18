##Running time measurement

###Objective-C:
	
	#import <QuartzCore/QuartzCore.h>
	CFTimeInterval startTime = CACurrentMediaTime();
	// perform some action
	CFTimeInterval elapsedTime = CACurrentMediaTime() - startTime;
	
	
###Swift:
	
	let startTime = CACurrentMediaTime()
	// perform some action
	let elapsedTime = CACurrentMediaTime() - startTime