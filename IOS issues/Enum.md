#Enum



// define key state enum in .h file:

	enum {
	    KS_AUTHENTICATE,
	    KS_CHECK_USER_EXIST,
	    KS_CREATE_USER,
	    KS_CREATE_INVITATION,
	    
	    KS_UPDATE_ENDPOINT,
	    KS_LAST
	};
	
	
	@property(atomic) int ksState;
	
// define below code in the .m file:

	- (void) setState:(int)aState {
	    _ksState = aState;
	}
	
	- (void) processState {
	    switch(_ksState) {
	        case KS_AUTHENTICATE:
	            // call authenticate API here
	            break;
	            
	        case KS_CHECK_USER_EXIST:
	            // call search user by email API here
	            break;
	            
	        case KS_CREATE_USER:
	            // call create user API here
	            break;
	            
	        case KS_CREATE_INVITATION:
	            break;
	        default:
	            break;
	    }
	    
	}
	
	// Called by authenticate portal API when it succeeded
	- (void) ksAuthenticateDone {
	    [self setState:KS_CHECK_USER_EXIST];
	    [self processState];
	}
	
	// Called by search user by email portal API when it succeeded and totalResults = 0
	- (void) ksUserNotExist {
	    [self setState:KS_CREATE_USER];
	    [self processState];
	}
	
	// Called by search user by email portal API when it succeeded and totalResults > 0
	- (void) ksUserExist {
	    if (![self.mobileKeyController isEndpointSetup]) {
	        [self setState:KS_CREATE_INVITATION];
	        [self processState];
	    }
	    else {
	        // endpoint already setup
	    }
	}
	
	// Called by create invitation code API when it succeeded
	- (void)ksInvitationCreated:(NSString*)invitationCode {
	    
	}
