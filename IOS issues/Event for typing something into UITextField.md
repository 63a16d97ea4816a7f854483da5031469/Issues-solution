#Event for typing something into UITextField
	- (BOOL)textField:(UITextField *)textField shouldChangeCharactersInRange:(NSRange)range replacementString:(NSString *)string
	{
	    if(textField.tag==1000){
	    NSString * str = [textField.text stringByReplacingCharactersInRange:range withString:string];
	    self.navigationItem.rightBarButtonItem.enabled = str.length > 0;
	    }
	    
	    return YES;
	}
