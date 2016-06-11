#Loop trough NSDictionary in key order displayed with NSLog


	NSArray *keys = [myDictionary allKeys];
	NSArray *sortedKeys = [keys sortedArrayUsingSelector:@selector(compare:)];
	
	for (id key in sortedKeys) {
	    id value = [myDictionary objectForKey:key];
	
	    NSLog(@"%@ = %@", key, value);
	}



       [newArr sortUsingComparator:^NSComparisonResult(id obj1, id obj2){
              
                        PlanList *tmp1=obj1;
                        PlanList *tmp2=obj2;
                        NSDateFormatter *dateFormat = [[NSDateFormatter alloc] init];
                        [dateFormat setDateFormat:@"dd-MMM-yyyy HH:mm:ss"];
                        NSDate *tmp1Date = [dateFormat dateFromString:tmp1.addDateTime];
                        NSDate *tmp2Date = [dateFormat dateFromString:tmp2.addDateTime];
          
                        return (![tmp1Date compare:tmp2Date]);
                    }];
                    
                    
newArr is the reference Array to loop NSDictionary.