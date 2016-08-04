#Singleton

	#import <UIKit/UIKit.h>
	
	
	@interface GoogleDriveHelper : NSObject
	
	+ (instancetype)sharedInstance;
	
	@end





	#import "GoogleDriveHelper.h"
	
	@interface GoogleDriveHelper ()
	
	@end
	
	@implementation GoogleDriveHelper
	
	+ (instancetype) sharedInstance {
	    static GoogleDriveHelper *__sharedInstance;
	    static dispatch_once_t onceToken;
	    
	    dispatch_once(&onceToken, ^{
	        __sharedInstance = [[GoogleDriveHelper alloc] init];
	    });
	    
	    return __sharedInstance;
	}
	
	@end


Why does Apple recommend to use dispatch_once for implementing the singleton pattern under ARC?

Because it will only run once. So if you try and access it twice from different threads it won't cause a problem.

Mike Ash has a full description in his Care and Feeding of Singletons blog post.

Not all GCD blocks are run asynchronously.


dispatch_once() is absolutely synchronous. Not all GCD methods do things asynchronously (case in point, dispatch_sync() is synchronous). 

The benefit of dispatch_once() over this is that it's faster. It's also semantically cleaner, because it also protects you from multiple threads doing alloc init of your sharedInstance--if they all try at the same exact time. It won't allow two instances to be created. The entire idea of dispatch_once() is "perform something once and only once", which is precisely what we're doing.

https://www.bignerdranch.com/blog/dispatch_once-upon-a-time/