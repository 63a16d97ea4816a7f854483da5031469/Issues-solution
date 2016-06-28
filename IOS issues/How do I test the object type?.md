#How do I test the object type?

If your object is myObject, and you want to test to see if it is an NSString, the code would be:

	[myObject isKindOfClass:[NSString class]]
	
Likewise, if you wanted to test myObject for a UIImageView:

	[myObject isKindOfClass:[UIImageView class]]
	
	

<b><font color=blue>isKindOfClass:</font></b> Returns a Boolean value that indicates whether the receiver is an instance of given class or an instance of any class that inherits from that class.

<b><font color=blue>isMemberOfClass:</font></b>  Returns a Boolean value that indicates whether the receiver is an instance of a given class.


	@interface A : NSObject 
	@end
	
	@interface B : A
	@end
	
	...
	
	id b = [[B alloc] init];
	then
	
	[b isKindOfClass:[A class]] == YES;
	[b isMemberOfClass:[A class]] == NO;