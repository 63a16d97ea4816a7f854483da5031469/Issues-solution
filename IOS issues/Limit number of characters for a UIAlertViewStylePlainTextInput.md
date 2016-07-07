#Limit number of characters for a UIAlertViewStylePlainTextInput

First add UITextFieldDelegate

	UIAlertView *dialog = [[UIAlertView alloc]init];// Setup your alert 
	[dialog setAlertViewStyle:UIAlertViewStylePlainTextInput];
	[dialog textFieldAtIndex:0].placeholder = @"";//add this if you need
	[dialog textFieldAtIndex:0].delegate = self;
	and add textfield delegate as per Check this Answer
	
	- (BOOL)textField:(UITextField *)textField shouldChangeCharactersInRange:(NSRange)range replacementString:(NSString *)string {
	    NSUInteger newLength = [textField.text length] + [string length] - range.length;
	    return (newLength > 25) ? NO : YES;
	}