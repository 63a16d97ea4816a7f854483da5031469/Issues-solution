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