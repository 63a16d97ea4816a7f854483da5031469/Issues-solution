#Take Screenshot and save to Album
	
	- (UIImage*)captureView:(UIView *)view
	{
	    CGRect rect = [[UIScreen mainScreen] bounds];
	    UIGraphicsBeginImageContext(rect.size);
	    CGContextRef context = UIGraphicsGetCurrentContext();
	    [view.layer renderInContext:context];
	    UIImage *img = UIGraphicsGetImageFromCurrentImageContext();
	    UIGraphicsEndImageContext();
	    return img;
	}
	
	- (void)saveScreenshotToPhotosAlbum
	{
	    UIImageWriteToSavedPhotosAlbum([self captureView:self.view], nil, nil, nil);
	}
  
  
	
	
High quality of screenshot:

replace

	UIGraphicsBeginImageContext(self.view.bounds.size);
with    

	UIGraphicsBeginImageContextWithOptions(self.view.bounds.size, self.view.opaque, 0.0);




Send by using email:

	- (void)emailImageWithImageData
	{
	    // CREATING MAIL VIEW
	    MFMailComposeViewController *controller = [[MFMailComposeViewController alloc] init];
	    controller.mailComposeDelegate = self;
	    [controller setSubject:@"Check this route out"];
	    [controller setMessageBody:@"Attaching a shot of covered route." isHTML:NO];
	    
	    // MAKING A SCREENSHOT
	//    UIGraphicsBeginImageContext(self.view.frame.size);
	    UIGraphicsBeginImageContextWithOptions(self.view.bounds.size, self.view.opaque, 0.0);
	    [self.view.layer renderInContext:UIGraphicsGetCurrentContext()];
	    UIImage *screenshot = UIGraphicsGetImageFromCurrentImageContext();
	    UIGraphicsEndImageContext();
	    
	    // ATTACHING A SCREENSHOT
	    NSData *myData = UIImagePNGRepresentation(screenshot);
	    [controller addAttachmentData:myData mimeType:@"image/png" fileName:@"route"];
	    
	    // SHOWING MAIL VIEW
	    [self presentModalViewController:controller animated:YES];
	}
	
	- (void)mailComposeController:(MFMailComposeViewController*)controller didFinishWithResult:(MFMailComposeResult)result error:(NSError*)error
	{
	    // Called once the email is sent
	    // Remove the email view controller
	    [self dismissModalViewControllerAnimated:YES];
	}