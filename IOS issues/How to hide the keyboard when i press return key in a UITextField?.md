#How to hide the keyboard when i press return key in a UITextField?

http://stackoverflow.com/questions/3573955/how-to-hide-the-keyboard-when-i-press-return-key-in-a-uitextfield


In viewDidLoad declare: works!

	[yourTextField setDelegate:self];
	
	Then, include the override of the delegate method:
	
	-(BOOL)textFieldShouldReturn:(UITextField *)textField
	{
	    [textField resignFirstResponder];
	    return YES;
	}

#How to dismiss number pad keyboard by tapping anywhere

http://stackoverflow.com/questions/6991085/how-to-dismiss-number-pad-keyboard-by-tapping-anywhere

Try this method: Works!

	-(void)touchesBegan:(NSSet *)touches withEvent:(UIEvent *)event
	{
	   [self.view endEditing:YES];
	}
Now tap anywhere and see keyboard will dismiss. :-)




For Swift Use Below Code

	override func touchesBegan(touches: NSSet, withEvent event: UIEvent)
	 {
	       textFiled.resignFirstResponder()
	 }