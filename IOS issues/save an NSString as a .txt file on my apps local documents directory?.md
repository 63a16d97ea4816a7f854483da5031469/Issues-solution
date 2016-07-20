#save an NSString as a .txt file on my apps local documents directory?


####write to the file:

	NSArray *paths = NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES); 
	NSString *documentsDirectory = [paths objectAtIndex:0]; // Get documents directory
	
	NSError *error;
	BOOL succeed = [myString writeToFile:[documentsDirectory stringByAppendingPathComponent:@"myfile.txt"]
	      atomically:YES encoding:NSUTF8StringEncoding error:&error];
	if (!succeed){
	    // Handle error here
	}
	
		
		- (void)saveStringToDocuments:(NSString*) stringToSave {
	
	 NSString* documentsFolder = [NSHomeDirectory() stringByAppendingPathComponent:@"Documents"];
	 NSString* fileName = [NSString stringWithString:@"savedString.txt"];
	
	 NSString* path = [documentsFolder stringByAppendingPathComponent:fileName];
	
	 [[NSFileManager defaultManager] createFileAtPath:path contents:[stringToSave dataUsingEncoding:NSUTF8StringEncoding] attributes:nil];
	}
	
	
	
	
####Read the file:
 
	-(NSString *)readStringFromFile{
	    NSString *filePath = [NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES) objectAtIndex:0];
	    NSString *fileName = @"textFile.txt";
	    NSString *fileAtPath = [filePath stringByAppendingString:fileName];
	    return [[NSString alloc] initWithData:[NSData dataWithContentsOfFile:fileAtPath] encoding:NSUTF8StringEncoding];
	}	
	
	
	
####Remove the file:

	- (void)removeImage:(NSString *)filename
	{
	  NSFileManager *fileManager = [NSFileManager defaultManager];
	  NSString *documentsPath = [NSSearchPathForDirectoriesInDomains(NSDocumentDirectory, NSUserDomainMask, YES) objectAtIndex:0];
	
	  NSString *filePath = [documentsPath stringByAppendingPathComponent:filename];
	  NSError *error;
	  BOOL success = [fileManager removeItemAtPath:filePath error:&error];
	  if (success) {
	      UIAlertView *removedSuccessFullyAlert = [[UIAlertView alloc] initWithTitle:@"Congratulations:" message:@"Successfully removed" delegate:self cancelButtonTitle:@"Close" otherButtonTitles:nil];
	      [removedSuccessFullyAlert show];
	  }
	  else
	  {
	      NSLog(@"Could not delete file -:%@ ",[error localizedDescription]);
	  }
	}	