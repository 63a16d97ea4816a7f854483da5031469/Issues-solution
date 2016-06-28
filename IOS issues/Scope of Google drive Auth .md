#Scope of Google drive Auth 

kGTLAuthScopeDriveFile    ==> you only read and write the data you created.

kGTLAuthScopeDriveMetadata   ==> you can see all the files and read and write this files.


	// Creates the auth controller for authorizing access to Drive API.
	- (GTMOAuth2ViewControllerTouch *)createAuthController {
	    GTMOAuth2ViewControllerTouch *authController;
	    // If modifying these scopes, delete your previously saved credentials by
	    // resetting the iOS simulator or uninstall the app.
	    NSArray *scopes = [NSArray arrayWithObjects:kGTLAuthScopeDriveMetadata, nil];
	    authController = [[GTMOAuth2ViewControllerTouch alloc]
	                      initWithScope:[scopes componentsJoinedByString:@" "]
	                      clientID:kClientID
	                      clientSecret:nil
	                      keychainItemName:kKeychainItemName
	                      delegate:self
	                      finishedSelector:@selector(viewController:finishedWithAuth:error:)];
	    return authController;
	}
