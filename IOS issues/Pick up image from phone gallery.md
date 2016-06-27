#Pick up image from phone gallery

###you can adjust the image size

	UIImagePickerController *cardPicker = [[UIImagePickerController alloc]init];
	cardPicker.allowsEditing=YES;
	cardPicker.delegate=self;
	cardPicker.sourceType = UIImagePickerControllerSourceTypeSavedPhotosAlbum;
	[self presentModalViewController:appDelegate.cardPicker animated:YES];
	[cardPicker release];
	And this delegate method will return the image u select from the album
	
	-(void)imagePickerController:(UIImagePickerController *)picker didFinishPickingImage:(UIImage *)img editingInfo:(NSDictionary *)editInfo 
	{
	    [picker  dismissModalViewControllerAnimated:YES];
	    noImage.image=img;
	}



	
==>added a UIImagePickerController to a UIViewController. I have also assigned the UIImagePickerControllerDelegate to that UIViewController.	


##Get the full picture:

	- (void)tapSelectAd:(id)sender
	{
	    picker = [[UIImagePickerController alloc] init];
	    picker.delegate = self;
	    picker.sourceType = UIImagePickerControllerSourceTypeSavedPhotosAlbum;
	    picker.mediaTypes = [UIImagePickerController availableMediaTypesForSourceType:picker.sourceType];
	    picker.allowsEditing = NO;
	    picker.wantsFullScreenLayout = YES;
	
	    [self presentModalViewController:picker animated:YES];
	}
	
	- (void)imagePickerController:(UIImagePickerController *) Picker didFinishPickingMediaWithInfo:(NSDictionary *)info {
	    [picker dismissModalViewControllerAnimated:YES];
	    UIImage *image=[info objectForKey:UIImagePickerControllerOriginalImage];
	    selectedImage.image = image;
	}