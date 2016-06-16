#UITextView

Change the Font of the Text inside the UITextView:
[textView setFont:[UIFont boldSystemFontOfSize:15]];

Limit the length of wording:	

	- (BOOL)textView:(UITextView *)textView shouldChangeTextInRange:(NSRange)range replacementText:(NSString *)text{
	    
	    
	    if([text isEqualToString:@"\b"]){
	        
	        return YES;
	    }else if([[textView text] length] > 140){
	        
	        return NO;
	    }
	    
	    return YES;
	}
	
Delegate:
UITextViewDelegate



	-(void)textViewDidChange:(UITextView *)textView
	{
	    self.navigationItem.rightBarButtonItem.enabled = textView.text.length > 0;
	    UITextField * timeLengthtextField = (UITextField *)[self.tableView viewWithTag:1111];
	    timeLengthtextField.placeholder=[NSString stringWithFormat:@"%lu",(unsigned long)textView.text.length];
	}	



