#List down all the png files in google drive


## You need to login first and then call below method:

	-(void)listDownAllFilesInDrive{

	 NSLog(@"list down all the files");
	    GTLQueryDrive *query = [GTLQueryDrive queryForFilesList];
	    query.q = @"mimeType = 'image/png'";
	    
	//    UIAlertView *alert = [QEUtilities showLoadingMessageWithTitle:@"Loading files"
	//                                                         delegate:self];
	    [self.service executeQuery:query completionHandler:^(GTLServiceTicket *ticket,
	                                                              GTLDriveFileList *files,
	                                                              NSError *error) {
	//        [alert dismissWithClickedButtonIndex:0 animated:YES];
	        if (error == nil) {
	            if (self.driveFiles == nil) {
	                self.driveFiles = [[NSMutableArray alloc] init];
	            }
	            [self.driveFiles removeAllObjects];
	            [self.driveFiles addObjectsFromArray:files.files];
	            
	            NSLog(@"the files:%@",self.driveFiles);
	            
	        } else {
	            NSLog(@"An error occurred: %@", error);
	
	        }
	    }];
}


## If you would like to get the list of more than one different kinds of files:

    query.q = @"mimeType = 'image/png'  or mimeType = 'text/plain'";
    
    
http://stackoverflow.com/questions/18075937/how-to-list-multiple-mime-types-files-from-google-drive

