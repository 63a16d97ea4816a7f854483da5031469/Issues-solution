#NSTimeInterval  and NSDate

Current Date to NSTimeInterval:

    NSTimeInterval eventTimeStamp = [[NSDate date] timeIntervalSince1970];
 
NSTimeInterval to NSDate:

	NSDate *lastUpdate = [[NSDate alloc] initWithTimeIntervalSince1970:1408709486];

    NSDateFormatter *dateFormat = [[NSDateFormatter alloc] init];
    [dateFormat setDateFormat:@"dd-MMM-YYYY HH:mm:ss"];
    [dateFormat setTimeZone:[NSTimeZone defaultTimeZone]];
    NSString *datestr = [dateFormat stringFromDate:lastUpdate];

 

NSLog(@"date time: %@", datestr);
