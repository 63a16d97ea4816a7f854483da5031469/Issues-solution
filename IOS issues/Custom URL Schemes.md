#Custom URL Schemes


http://www.idev101.com/code/Objective-C/custom_url_schemes.html



http://code.tutsplus.com/tutorials/ios-sdk-working-with-url-schemes--mobile-6629



	-(IBAction) openReceiverApp:(id)sender {
	    // Opens the Receiver app if installed, otherwise displays an error
	    UIApplication *ourApplication = [UIApplication sharedApplication];
	    NSString *URLEncodedText = [self.textBox.text stringByAddingPercentEscapesUsingEncoding:NSUTF8StringEncoding];
	    NSString *ourPath = [@"readtext://" stringByAppendingString:URLEncodedText];
	    NSURL *ourURL = [NSURL URLWithString:ourPath];
	    if ([ourApplication canOpenURL:ourURL]) {
	        [ourApplication openURL:ourURL];
	    }
	    else {
	        //Display error
	        UIAlertView *alertView = [[UIAlertView alloc] initWithTitle:@"Receiver Not Found" message:@"The Receiver App is not installed. It must be installed to send text." delegate:nil cancelButtonTitle:@"OK" otherButtonTitles:nil];
	        [alertView show];
	        [alertView release];
	    }
	 
	}