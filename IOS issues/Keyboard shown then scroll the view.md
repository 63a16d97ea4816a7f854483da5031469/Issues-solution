#Keyboard shown then scroll the view

    [[NSNotificationCenter defaultCenter] addObserver:self
                                             selector:@selector(keyboardWasShown:)
                                                 name:UIKeyboardDidShowNotification
                                               object:nil];
    
    [[NSNotificationCenter defaultCenter] addObserver:self
                                             selector:@selector(keyboardWillBeHidden:)
                                                 name:UIKeyboardWillHideNotification
                                               object:nil];
                                               
	                                               
	                                               
	- (void)keyboardWasShown:(NSNotification *)notification {
	    
	    NSDictionary* info = [notification userInfo];
	    
	    CGSize keyboardSize = [[info objectForKey:UIKeyboardFrameBeginUserInfoKey] CGRectValue].size;
	    
	    CGPoint buttonOrigin = self.backBeaconId.frame.origin;
	    
	    CGFloat buttonHeight = self.backBeaconId.frame.size.height;
	    
	    CGRect visibleRect = self.view.frame;
	    
	    visibleRect.size.height -= keyboardSize.height;
	    
	    if (!CGRectContainsPoint(visibleRect, buttonOrigin)){
	        
	        CGPoint scrollPoint = CGPointMake(0.0, buttonOrigin.y - visibleRect.size.height + buttonHeight + 20);
	        
	        [self.scrollView setContentOffset:scrollPoint animated:YES];
	        
	    }
	    
	}
	
	- (void)keyboardWillBeHidden:(NSNotification *)notification {
	    
	    CGPoint point=CGPointMake(0, -80);
	    [self.scrollView setContentOffset:point animated:YES];
	    //CGPointZero
	    
	}
