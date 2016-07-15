#Objective-c adding Subviews to the bottom of view

One Solution:
	[view insertSubview:aView atIndex:0]

Two Solution:
sendSubviewToBack:

Moves the specified subview so that it appears behind its siblings.  

	- (void)sendSubviewToBack:(UIView *)view