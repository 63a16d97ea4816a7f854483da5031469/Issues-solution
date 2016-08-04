#Popup Overlay Window

	+ (void)setPresentationStyleForSelfController:(UIViewController *)selfController presentingController:(UIViewController *)presentingController
	{
	    
	    if ([NSProcessInfo instancesRespondToSelector:@selector(isOperatingSystemAtLeastVersion:)])
	    {
	        //iOS 8.0 and above
	        presentingController.providesPresentationContextTransitionStyle = YES;
	        presentingController.definesPresentationContext = YES;
	        
	        [presentingController setModalPresentationStyle:UIModalPresentationOverCurrentContext];
	    }
	    else
	    {
	        [selfController setModalPresentationStyle:UIModalPresentationCurrentContext];
	        [selfController.navigationController setModalPresentationStyle:UIModalPresentationCurrentContext];
	    }
	}


LiveBlur:
http://whoisryannystrom.com/2013/09/17/Live-blur-in-iOS7/
	
	//  UIERealTimeBlurView.h
