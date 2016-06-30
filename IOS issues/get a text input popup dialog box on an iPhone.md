#Get a text input popup dialog box on an iPhone

	UIAlertView * alert = [[UIAlertView alloc] initWithTitle:@"Alert" message:@"This is an example alert!" delegate:self cancelButtonTitle:@"Hide" otherButtonTitles:nil];
	alert.alertViewStyle = UIAlertViewStylePlainTextInput;
	[alert show];
	

	- (void)alertView:(UIAlertView *)alertView clickedButtonAtIndex:(NSInteger)buttonIndex{ 
	    NSLog(@"Entered: %@",[[alertView textFieldAtIndex:0] text]);
	}

##Another:

	UIAlertView * alert = [[UIAlertView alloc] initWithTitle:@"Hello!" message:@"Please enter your name:" delegate:self cancelButtonTitle:@"Continue" otherButtonTitles:nil];
	alert.alertViewStyle = UIAlertViewStylePlainTextInput;
	UITextField * alertTextField = [alert textFieldAtIndex:0];
	alertTextField.keyboardType = UIKeyboardTypeNumberPad;
	alertTextField.placeholder = @"Enter your name";
	[alert show];



I think the easiest way to check that every character within a given string is numeric is probably:

	NSString *trimmedString = [newString stringByTrimmingCharactersInSet:[NSCharacterSet decimalDigitCharacterSet]];
	
	if([trimmedString length])
	{
	    NSLog(@"some characters outside of the decimal character set found");
	}
	else
	{
	    NSLog(@"all characters were in the decimal character set");
	}