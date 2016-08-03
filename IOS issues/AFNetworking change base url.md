#AFNetworking change base url

If you're switching between base URL's it might just be easier to initialise a new manager each time rather than use a shared one. As much of the benefit of using a shared manager is the single static base URL.

	AFHTTPRequestOperationManager *manager = [AFHTTPRequestOperationManager manager];
	[manager GET:@"http://example.com/resources.json" parameters:nil success:^(AFHTTPRequestOperation *operation, id responseObject) {
	    NSLog(@"JSON: %@", responseObject);
	} failure:^(AFHTTPRequestOperation *operation, NSError *error) {
	    NSLog(@"Error: %@", error);
	}];