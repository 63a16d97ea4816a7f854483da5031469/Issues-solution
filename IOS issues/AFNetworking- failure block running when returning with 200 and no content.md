AFNetworking: failure block running when returning with 200 and no content

http://stackoverflow.com/questions/12044880/afnetworking-failure-block-running-when-returning-with-200-and-no-content

Instead of using AFNetworking's success and completion blocks you could use AFHTTPRequestOperation and deal with the response codes yourself. For example:

	// Setup HTTP client
	AFHTTPClient *client = [AFHTTPClient clientWithBaseURL:[NSURL URLWithString:@"http://website.com"]];
	
	// Create the request
	NSURLRequest *request = [client requestWithMethod:@"GET" path:@"authenticate" parameters:params];
	
	// Create an HTTP operation with your request
	AFHTTPRequestOperation *operation = [[AFHTTPRequestOperation alloc] initWithRequest:request];
	
	// Setup the completion block
	[operation setCompletionBlockWithSuccess:^(AFHTTPRequestOperation *operation, id responseObject) {
	    switch (operation.response.statusCode) {
	        case 200:
	            // Do stuff
	            break;
	        default:
	            break;
	    }
	} failure:^(AFHTTPRequestOperation *operation, NSError *error) {
	    switch (operation.response.statusCode) {
	        case 400:
	            // Do stuff
	            break;
	        default:
	            break;
	    }
	}];
	
	// Begin your request
	[operation start];