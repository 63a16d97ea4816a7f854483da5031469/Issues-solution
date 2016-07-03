#Get the list of google drive files

https://developers.google.com/drive/v2/reference/files/list#examples



	#import "GTLDrive.h"
	// ...
	
	+ (void)retrieveAllFilesWithService:(GTLServiceDrive *)service
	                    completionBlock:(void (^)(NSArray *, NSError *))completionBlock {
	  // The service can be set to automatically fetch all pages of the result. More information
	  // can be found on <a href="https://code.google.com/p/google-api-objectivec-client/wiki/Introduction#Result_Pages">https://code.google.com/p/google-api-objectivec-client/wiki/Introduction#Result_Pages</a>.
	  service.shouldFetchNextPages = YES;
	
	  GTLQueryDrive *query = [GTLQueryDrive queryForFilesList];
	  // queryTicket can be used to track the status of the request.
	  GTLServiceTicket *queryTicket =
	    [service executeQuery:query
	        completionHandler:^(GTLServiceTicket *ticket, GTLDriveFileList *files,
	                            NSError *error) {
	          if (error == nil) {
	            completionBlock(files.items, nil);
	          } else {
	            NSLog(@"An error occurred: %@", error);
	            completionBlock(nil, error);
	          }
	        }];
	}
	
	




##Querying for Files

####https://developers.google.com/drive/ios/devguide/queries#retrieving_multiple_pages_of_results

You can use Drive's query language to search a user's Drive account for files whose metadata or content match your search criteria. You can issue a query for a specific folder or on the entire filesystem.

Building queries

Query expressions are strings. The following example finds all files with the title "HelloWorld.txt".

NSString *search = @"name = 'HelloWorld.txt'";
You can combine multiple clauses together using and and or operators.

To execute a query, set the q property with listing files:

	GTLServiceDrive *drive = ...;
	GTLQueryDrive *query = [GTLQueryDrive queryForFilesList];
	query.q = search;
	[drive executeQuery:query completionHandler:^(GTLServiceTicket *ticket,
	                                              GTLDriveFileList *fileList,
	                                              NSError *error) {
	  if (error == nil) {
	    NSLog(@"Have results");
	    // Iterate over fileList.files array
	  } else {
	    NSLog(@"An error occurred: %@", error);
	  }
	}];
Retrieving the result of a query

The result of a query is a GTLDriveFileList object. The files property contains a list of GTLDriveFile instances for each of the matching entries. You can then use these instances to perform additional operations, such as reading the contents.

Retrieving multiple pages of results

Sometimes a query may return a large number of results, which are returned one page at a time. When a result object includes a nextPageToken string, you can execute the query again; supply the returned token as the pageToken property of the new query, fetching the next set of results. You can repeat this until you reach the last page, which will not inlude a nextPageToken string.

if (fileList.nextPageToken) {
  query.pageToken = fileList.nextPageToken;
  GTLServiceTicket *nextTicket = [drive executeQuery:query ...];
}


##Success:

	-(void)listDownAllFilesInDrive: (GTLQueryDrive*) queryDriveObject{
	    NSLog(@"list down all the images files");
	
	    queryDriveObject.q = @"mimeType = 'image/png'  or mimeType = 'image/jpeg' or mimeType = 'image/gif'";
	//    query.q = [NSString stringWithFormat:@"'%@' IN parents", @"root"];
	
	//     self.service.shouldFetchNextPages = YES;
	    GTLServiceTicket *queryTicket =[self.service executeQuery:queryDriveObject completionHandler:^(GTLServiceTicket *ticket,
	                                                              GTLDriveFileList *files,
	                                                              NSError *error) {
	//        [alert dismissWithClickedButtonIndex:0 animated:YES];
	        
	        if (error == nil) {
	            if (self.driveFiles == nil) {
	                self.driveFiles = [[NSMutableArray alloc] init];
	            }
	            
	            [self.driveFiles addObjectsFromArray:files.files];
	            
	            if (files.nextPageToken) {
	                NSLog(@"call another time----===");
	                queryDriveObject.pageToken = files.nextPageToken;
	//                GTLServiceTicket *nextTicket = [drive executeQuery:query ...];
	                [self listDownAllFilesInDrive:queryDriveObject];
	            }else{
	                 NSLog(@"get the whole list and do following thing:----===");
	            NSLog(@"the files:%@",self.driveFiles);
	            
	            
	            }
	        } else {
	            NSLog(@"An error occurred: %@", error);
	
	        }
	    }];