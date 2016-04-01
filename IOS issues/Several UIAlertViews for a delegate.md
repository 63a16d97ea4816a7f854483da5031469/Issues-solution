#Several UIAlertViews for a delegate

http://stackoverflow.com/questions/2338546/several-uialertviews-for-a-delegate


Tag the UIAlertViews like this:

	\#define kAlertViewOne 1
	\#define kAlertViewTwo 2
	
	UIAlertView *alertView1 = [[UIAlertView alloc] init...
	alertView1.tag = kAlertViewOne;
	
	UIAlertView *alertView2 = [[UIAlertView alloc] init...
	alertView2.tag = kAlertViewTwo;
	and then differentiate between them in the delegate methods using these tags:
	
	- (void)alertView:(UIAlertView *)alertView clickedButtonAtIndex:(NSInteger)buttonIndex {
	    if(alertView.tag == kAlertViewOne) {
	        // ...
	    } else if(alertView.tag == kAlertViewTwo) {
	        // ...
	    }
	}