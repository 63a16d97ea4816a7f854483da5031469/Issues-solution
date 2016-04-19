#UIAlertView (Input password or text)

    UIAlertView * alert = [[UIAlertView alloc] initWithTitle:@"Admin Panel" message:@"Please enter your password:" delegate:self cancelButtonTitle:@"Continue" otherButtonTitles:@"Cancel",nil];
    alert.alertViewStyle = UIAlertViewStyleSecureTextInput;
    UITextField * alertTextField = [alert textFieldAtIndex:0];
    alertTextField.keyboardType = UIKeyboardTypeNumberPad;
    alertTextField.placeholder = @"Enter your password";
    [alert show];
    
    
More than one input fields:    

If you want to add just two textfields to your UIAlertView, you can use UIAlertViewStyleLoginAndPasswordInput and modify the textfields as follows:

	UIAlertView *alert = [[UIAlertView alloc]initWithTitle:@"Some Title" message:@"Some Message." delegate:self cancelButtonTitle:@"Okay" otherButtonTitles:@"No, thanks", nil];
	alert.alertViewStyle = UIAlertViewStyleLoginAndPasswordInput;
	[alert textFieldAtIndex:1].secureTextEntry = NO; //Will disable secure text entry for second textfield.
	[alert textFieldAtIndex:0].placeholder = @"First Placeholder"; //Will replace "Username"
	[alert textFieldAtIndex:1].placeholder = @"Second Placeholder"; //Will replace "Password"
	[alert show];
	
	
Afterwards, in the UIAlertView delegate, you can simply get the text using:

	text1 = [alert textFieldAtIndex:0].text;
	text2 = [alert textFieldAtIndex:1].text;
	
	
##Introduction of UIAlertView with more than one TextFields
http://stackoverflow.com/questions/10389635/uialertview-with-two-textfields-and-two-buttons

Starting from iOS 5 is possible to use the property alertViewStyle of UIAlertView to get different type of alert views, also with text fields.

Possible values:

	UIAlertViewStyleDefault
	UIAlertViewStyleSecureTextInput
	UIAlertViewStylePlainTextInput
	UIAlertViewStyleLoginAndPasswordInput
	You can use the UIAlertViewStyleLoginAndPasswordInput to obtain an UIAlertView with two text fields and then you can customize some properties of the textFields:
	
	 UIAlertView *av = [[UIAlertView alloc] initWithTitle:@"Your_Title" message:@"Your_message" delegate:self cancelButtonTitle:@"Cancel" otherButtonTitles:@"OK", nil];
	[av setAlertViewStyle:UIAlertViewStyleLoginAndPasswordInput];
	
	// Alert style customization 
	[[av textFieldAtIndex:1] setSecureTextEntry:NO];
	[[av textFieldAtIndex:0] setPlaceholder:@"First_Placeholder"];
	[[av textFieldAtIndex:1] setPlaceholder:@"Second_Placeholder"];
	[av show];
	You can access the values of the text fields on the alertView:clickedButtonAtIndex: of UIAlertViewDelegate.
	
	-(void)alertView:(UIAlertView *)alertView clickedButtonAtIndex:(NSInteger)buttonIndex{
	     NSLog(@"1 %@", [alertView textFieldAtIndex:0].text);
	     NSLog(@"2 %@", [alertView textFieldAtIndex:1].text);
	}

