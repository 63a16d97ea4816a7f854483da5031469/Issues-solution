#UIActionSheet


http://9gato.com/ios-iphone-action-sheet-popup-uiactionsheet-objective-c-iphone-ipad/


Show the items:

	                          UIActionSheet *sheet = [[UIActionSheet alloc] initWithTitle: @ "Select Item"
	                                                                delegate: self
	                                                       cancelButtonTitle: @ "Cancel"
	                                                  destructiveButtonTitle: @ "Item 0"
	                                     // DestructiveButtonTitle: nil
	                                                                otherButtonTitles: @ "Item 1", @ "Item 2", @ "Item 3", @ "Item 4", nil];
	                            // Show the sheet
	                            [sheet showInView: self.view];
	                            
	                                  
Handle Events:

	 - (void) actionSheet: (UIActionSheet *) actionSheet didDismissWithButtonIndex: (NSInteger) buttonIndex.
	 {
	     switch (buttonIndex) {
	         case 0:
	             lblResult.text = @ "Your Selected Item 0";
	             break;
	         case 1:
	             lblResult.text = @ "Your Selected Item 1";
	             break;
	         case 2:
	             lblResult.text = @ "Your Selected Item 2";
	             break;
	         case 3:
	             lblResult.text = @ "Your Selected Item 3";
	             break;
	         case 4:
	             lblResult.text = @ "Your Selected Item 4";
	             break;
	         default:
	             break;
	     }
	 }	                            
	                            