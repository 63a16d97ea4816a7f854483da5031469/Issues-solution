#NSUserDefaults basic operations

##Get all the local cache configurations or settings:

	- (void) logAllUserDefaults
	{
	    NSArray *keys = [[[NSUserDefaults standardUserDefaults] dictionaryRepresentation] allKeys];
	    NSArray *values = [[[NSUserDefaults standardUserDefaults] dictionaryRepresentation] allValues];
	    for (int i = 0; i < keys.count; i++) {
	        NSLog(@"%@: %@", [keys objectAtIndex:i], [values objectAtIndex:i]);
	    }
	}
	
	
##Delete specific item:

	[[NSUserDefaults standardUserDefaults] removeObjectForKey:@"MyKey"];
	
Dont forget to synchronize if you want to save immediately

	[[NSUserDefaults standardUserDefaults] synchronize];
	
##Delete all the items saved before:

	NSDictionary *defaultsDictionary = [[NSUserDefaults standardUserDefaults] dictionaryRepresentation];
	for (NSString *key in [defaultsDictionary allKeys]) {
	                    [[NSUserDefaults standardUserDefaults] removeObjectForKey:key];
	}
###another method:
	- (void) clearDefaults {
	    [[NSUserDefaults standardUserDefaults] removePersistentDomainForName:[[NSBundle mainBundle] bundleIdentifier]];
	    [[NSUserDefaults standardUserDefaults] synchronize];
	}	

##Add one item:
	[[NSUserDefaults standardUserDefaults] setObject:dataElement forKey:@"Name"];		

##Insert more than one items:
	- (void) fillInSettings:(NSDictionary*)settingsDict {
	    NSString *key;
	    for(key in settingsDict){
	        NSLog(@"Key: %@, Value %@", key, [settingsDict objectForKey: key]);
	    	[[NSUserDefaults standardUserDefaults] setObject:[settingsDict objectForKey:key] forKey:key];
	    }
	    [[NSUserDefaults standardUserDefaults] synchronize];
	}