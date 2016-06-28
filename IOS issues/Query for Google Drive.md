#Query for Google Drive

query.q = @"mimeType='application/vnd.google-apps.folder' and trashed=false";


	GTLQueryDrive *query = [GTLQueryDrive queryForFilesList];
	query.q = @"mimeType='application/vnd.google-apps.folder' and trashed=false";
	
	[self.driveService executeQuery:query completionHandler:^(GTLServiceTicket *ticket,
	                                                          GTLDriveFileList *files,
	                                                          NSError *error) {
	
	    if (error == nil) {
	        NSLog(@"Array of folder: %@", files.items);
	    } else {
	        NSLog(@"An error occurred: %@", error);
	    }
	}];