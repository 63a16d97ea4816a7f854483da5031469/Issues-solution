#How to compare two NSDates: Which is more recent?

http://stackoverflow.com/questions/5965044/how-to-compare-two-nsdates-which-is-more-recent

Let's assume two dates:

	NSDate *date1;
	NSDate *date2;
	
	Then the following comparison will tell which is earlier/later/same:
	
	if ([date1 compare:date2] == NSOrderedDescending) {
	    NSLog(@"date1 is later than date2");
	} else if ([date1 compare:date2] == NSOrderedAscending) {
	    NSLog(@"date1 is earlier than date2");
	} else {
	    NSLog(@"dates are the same");
	}