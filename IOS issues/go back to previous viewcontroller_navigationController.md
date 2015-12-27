# Go back to previous viewController


http://stackoverflow.com/questions/16075525/navigate-back-to-previous-view-controller

	[self.navigationController popToRootViewControllerAnimated:YES];
	This will bring you back to root view controller. If you want to navigate back to previous view controller,you should implement :
	
	[self.navigationController popViewControllerAnimated:YES];