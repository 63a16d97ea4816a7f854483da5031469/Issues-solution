##UIAlertView three buttons
    UIAlertView *alert = [[UIAlertView alloc]
                          initWithTitle:@"Refresh"
                          message:@"Are you want to Refresh Data"
                          delegate:self
                          cancelButtonTitle:nil
                          otherButtonTitles:@"OK", @"Done",@"Cancel", nil];
    [alert show];

	- (void)alertView:(UIAlertView *)alertView clickedButtonAtIndex:(NSInteger)buttonIndex {
	    if (buttonIndex == 0) {
	        //@"OK"
	        NSLog(@"%ld",(long)buttonIndex);
	    }
	    else if (buttonIndex == 1) {
	        //Done
	        NSLog(@"%ld",(long)buttonIndex);
	
	    }
	    else if (buttonIndex == 2) {
	        //Cancel
	        NSLog(@"%ld",(long)buttonIndex);
	
	    }
	    else if (buttonIndex == 3) {
	        //
	        NSLog(@"%ld",(long)buttonIndex);
	
	    }
	}