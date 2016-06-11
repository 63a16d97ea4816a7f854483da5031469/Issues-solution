#work with UIPanGestureRecognizer

Drag to move the object:

	UIPanGestureRecognizer * pan1 = [[UIPanGestureRecognizer alloc]initWithTarget:self action:@selector(moveObject:)];
	pan1.minimumNumberOfTouches = 1;
	[image1 addGestureRecognizer:pan1];
	
	-(void)moveObject:(UIPanGestureRecognizer *)pan;
	{
	 image1.center = [pan locationInView:image1.superview];
	}
	
Drag and drag begin and drag end:
	
		UIPanGestureRecognizer *pan = [[UIPanGestureRecognizer alloc] initWithTarget:self action:@selector(handlePan:)];
	[viewToAnimate addGestureRecognizer:pan];
	
	
	- (void)handlePan:(UIPanGestureRecognizer *)gesture
	{
	    static CGPoint originalCenter;
	    if (gesture.state == UIGestureRecognizerStateBegan) {
	        originalCenter = gesture.view.center;
	    } else if (gesture.state == UIGestureRecognizerStateChanged) {
	        CGPoint translate = [gesture translationInView:gesture.view];
	        gesture.view.center = CGPointMake(originalCenter.x + translate.x, originalCenter.y + translate.y); // or, if only moving horizontally, use CGPointMake(originalCenter.x + translate.x, originalCenter.y)
	    } else if (gesture.state == UIGestureRecognizerStateEnded || gesture.state == UIGestureRecognizerStateCancelled) {
	        // do whatever you want here when the user lets go, e.g. animate the rest of the way to some location
	        [UIView animateWithDuration:0.5 animations:^{
	            gesture.view.center = ... // perhaps animate to some new location
	        }];
	    }
	}