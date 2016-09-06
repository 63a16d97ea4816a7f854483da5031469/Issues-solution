#How can I show the text with different fonts in textView in ios?

UITextView and UILabel are tested with below code: it works:

But this will change the whole string's font as it does not set the global fontsize and attributes for other substrings:

UITextView *textView = [[UITextView alloc] initWithFrame:CGRectMake(50, 50, 200, 100)];

textView.text = @"Vijay Apple Dev";

NSString *textViewText = textView.text;

NSMutableAttributedString *attributedText = [[NSMutableAttributedString alloc] initWithString:textViewText];

[attributedText addAttribute:NSFontAttributeName
                       value:[UIFont fontWithName:@"Courier" size:20]
                       range:[textViewText rangeOfString:@"Apple"]];


[attributedText addAttribute:NSFontAttributeName
                       value:[UIFont fontWithName:@"Verdana" size:20]
                       range:[textViewText rangeOfString:@"Vijay"]];

textView.attributedText = attributedText;

[self.view addSubview:textView];

How to set global font size and attributes:

NSMutableAttributedString *attrString = [[NSMutableAttributedString alloc] initWithString:stringToHighlight
                                                                               attributes:@{
                                                                                            NSFontAttributeName: [UIFont systemFontOfSize:14.0]
                                                                                            }];





For UILable:

Hi OHAttributelabel is good way for this.You can refer sample code with below link https://github.com/AliSoftware/OHAttributedLabel Import OHAttribute framwork from it and you can set your label as below

	 OHAttributedLabel *lblText;
	 lblText = [[OHAttributedLabel alloc] initWithFrame:CGRectMake(10,10,100,19)];
	 lblText.backgroundColor = [UIColor clearColor];
	    lblText.textAlignment = UITextAlignmentCenter;
	    lblText.font = [UIFont fontWithName:@"BoschSans-Regular" size:10];
	    NSString *strText=@"Tom: Some message.";
	    NSMutableAttributedString* attrStr = [NSMutableAttributedString attributedStringWithString: strText];
	    NSRange rangeOfSubstring = [strVersion rangeOfString:@“Tom:];
	    if (rangeOfSubstring.location != NSNotFound) {
	        [attrStr setFontName:@"BoschSans-BOLD" size:10.0 range:rangeOfSubstring];
	    }
	    else {
	    }
	
	    lblText.attributedText = attrStr;
	    [self.View addSubview: lblText];




Another way without using the library:

	UIFont *arialFont = [UIFont fontWithName:@"arial" size:18.0];
	 NSDictionary *arialDict = [NSDictionary dictionaryWithObject: arialFont forKey:NSFontAttributeName];    
	 NSMutableAttributedString *aAttrString = [[NSMutableAttributedString alloc] initWithString:title attributes: arialDict];
	
	 UIFont *VerdanaFont = [UIFont fontWithName:@"verdana" size:12.0];
	 NSDictionary *verdanaDict = [NSDictionary dictionaryWithObject:VerdanaFont forKey:NSFontAttributeName];
	 NSMutableAttributedString *vAttrString = [[NSMutableAttributedString alloc]initWithString: newsDate attributes:verdanaDict];    
	 [vAttrString addAttribute:NSForegroundColorAttributeName value:[UIColor blackColor] range:(NSMakeRange(0, 15))];
	
	 [aAttrString appendAttributedString:vAttrString];
	
	
	 lblText.attributedText = aAttrString;






More detail:

http://kalyanchakravarthy.net/blog/using-nsattributedstring-on-ios.html
	
	NSString *userName = @"Tex";
	NSString *stringToHighlight = [NSString stringWithFormat:@"Hello there human. Are you %@ ?", userName];
	
	// Set global fontsize on the string
	NSMutableAttributedString *attrString = [[NSMutableAttributedString alloc] initWithString:stringToHighlight
	                                                                               attributes:@{
	                                                                                            NSFontAttributeName: [UIFont systemFontOfSize:14.0]
	                                                                                            }];
	// Compute the range of the string that needs a different font
	NSRange *userNameRange = [stringToHighlight rangeOfString:userName];
	
	// Apply new attributes for a specific range
	[attrString setAttributes:@{
	                            NSFontAttributeName:[UIFont boldSystemFontOfSize:14],
	                            NSForegroundColorAttributeName:[UIColor grayColor]
	                           }
	                    range:userNameRange];
	
	// Make UILabel use attributedString as source
	UILabel *label = [[UILabel alloc] initWithFrame:self.view.frame];
	label.attributedText = attrString;
	
	
	
	

To make part of string becomes 'bold':

	NSString *boldFontName = [[UIFont boldSystemFontOfSize:12] fontName];
	NSString *yourString = ...;
	NSRange boldedRange = NSMakeRange(22, 4);
	
	NSMutableAttributedString *attrString = [[NSMutableAttributedString alloc] initWithString:yourString];
	
	[attrString beginEditing];
	[attrString addAttribute:kCTFontAttributeName 
	                   value:boldFontName
	                   range:boldedRange];
	
	[attrString endEditing];








Real case:

	  UITextView *contentView = [[UITextView alloc] initWithFrame:CGRectMake(0,0,100,200)];
	        contentView.text = self.message;

	        NSString *textViewText = contentView.text;
	  
	        NSMutableAttributedString *attributedText = [[NSMutableAttributedString alloc] initWithString:textViewText
	                                                                                       attributes:@{
	                                                                                                    NSFontAttributeName: JCAlertViewContentFont,
	                                                                        NSForegroundColorAttributeName:JCAlertViewContentColor                              }];
	        
	        
	        [attributedText addAttributes:@{
	                                                   NSFontAttributeName: JCAlertViewContentFont,
	                                                   NSForegroundColorAttributeName:JCAlertViewContentColor
	                                                   }
	
	                               range:[textViewText rangeOfString:@"1. Scope of our Service"]];
	        
	        contentView.attributedText = attributedText;
	        
	        
	        
	        
	        [self addSubview:contentView];
