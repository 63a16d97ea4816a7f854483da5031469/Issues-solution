#Creating uitableView from google drive images IOS 7


Just wanted to share a code on how to display images from Google Drive of UitableView

	GTLDriveFile *file = [self.driveFiles objectAtIndex:indexPath.row];
	
	GTMHTTPFetcher *fetcher = [self.driveService.fetcherService fetcherWithURLString:file.downloadUrl];
	[fetcher beginFetchWithCompletionHandler:^
	(NSData *data, NSError *error)
	{
	if (error != nil)
	NSLog(@”Error retrieving actual data: %@”, error);
	else
	{
	NSData *content = [[NSData alloc] initWithData:data ];
	UIImage *imageData=[UIImage imageWithData:content];
	cell.imageView.image=imageData;
	NSLog(@”Content: %@”, [self.driveFiles objectAtIndex:indexPath.row]);
	NSLog(@”file download: %@”, file.downloadUrl);
	
	}
	
	}];
	
	
##Upload image:
	- (void)uploadPhoto:(UIImage*)image
	{
	    NSDateFormatter *dateFormat = [[NSDateFormatter alloc] init];
	    [dateFormat setDateFormat:@"'Quickstart Uploaded File ('EEEE MMMM d, YYYY h:mm a, zzz')"];
	    GTLDriveFile *file = [GTLDriveFile object];
	    file.name = [dateFormat stringFromDate:[NSDate date]];
	    file.descriptionProperty = @"Uploaded from the Google Drive iOS Quickstart";
	    file.mimeType = @"image/png";
	    
	    NSData *data = UIImagePNGRepresentation((UIImage *)image);
	    
	    GTLUploadParameters *uploadParameters = [GTLUploadParameters uploadParametersWithData:data MIMEType:file.mimeType];
	    GTLQueryDrive *query = [GTLQueryDrive queryForFilesCreateWithObject:file
	                                                       uploadParameters:uploadParameters];
	//    UIAlertView *waitIndicator = [self showWaitIndicator:@"Uploading to Google Drive"];
	    
	    [self.service executeQuery:query
	                  completionHandler:^(GTLServiceTicket *ticket,GTLDriveFile *insertedFile, NSError *error)
	     {
	
	         if (error == nil)
	         {
	             NSLog(@"File ID: %@", insertedFile.identifier);
	             NSLog(@"File saved!");
	         }
	         else
	         {
	             NSLog(@"An error occurred: %@", error);
	            NSLog(@"Sorry, an error occurred!");
	         }
	     }];
	}
	
	
	
Search a spefic folder:	
	
	   GTLServiceDrive *service = self.driveService;
	
	    GTLDriveFile *folderObj = [GTLDriveFile object];
	
	    folderObj.title = [NSString stringWithFormat:@"%@", title];
	
	    folderObj.mimeType = @"application/vnd.google-apps.folder";
	
	    GTLQueryDrive *query = [GTLQueryDrive queryForFilesInsertWithObject:folderObj
	                                                       uploadParameters:nil];
	    _editFileListTicket = [service executeQuery:query
	                              completionHandler:^(GTLServiceTicket *ticket,
	                                                  GTLDriveFile *folderItem,
	                                                  NSError *error) {
	
	                                 if (error == nil)
	                                 {
	
	                                     UIAlertView *alert=[[UIAlertView alloc] initWithTitle:nil message:@"Created" delegate:self cancelButtonTitle:@"OK" otherButtonTitles:nil, nil];
	                                     [alert show];
	
	
	                                    }
	                                 else
	                                 {
	
	                                     NSLog(@"error");
	
	                                  }
	                              }];
	                              

##IOS: How to upload a file to specific Google drive folder using Google drive sdk library
	                              
http://stackoverflow.com/questions/13439457/ios-how-to-upload-a-file-to-specific-google-drive-folder-using-google-drive-sdk


How to save photos into a folder on google drive in iOS

http://stackoverflow.com/questions/32984984/how-to-save-photos-into-a-folder-on-google-drive-in-ios