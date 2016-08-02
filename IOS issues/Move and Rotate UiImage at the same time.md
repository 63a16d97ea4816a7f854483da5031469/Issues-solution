#Move and Rotate UiImage at the same time

   _rotateRecogniser = [[UIRotationGestureRecognizer alloc] initWithTarget:self action:@selector(handleRotate:)];
 
    [_rotateRecogniser setDelegate:self];
    [self addGestureRecognizer:_rotateRecogniser];

	
	- (IBAction) handleRotate:(UIRotationGestureRecognizer*)recogniser {
	    if (recogniser.state == UIGestureRecognizerStateBegan) {
	
	    recogniser.view.transform = CGAffineTransformRotate(recogniser.view.transform, recogniser.rotation);
	    recogniser.rotation = 0;
	    
	    UIView *piece = recogniser.view;
	    CGPoint locationInView = [recogniser locationInView:piece];
	    CGPoint locationInSuperview = [recogniser locationInView:piece.superview];
	    
	    CGPoint translatedCenter = CGPointMake(locationInSuperview.x,locationInSuperview.y);
	    [self setCenter:translatedCenter];
	    }
	    
	}