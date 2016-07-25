#NSDate for certain time set by yourself

 
	NSCalendar *calendar = [[NSCalendar alloc] initWithCalendarIdentifier:NSGregorianCalendar];
	NSDateComponents *components = [calendar components:( NSYearCalendarUnit | NSMonthCalendarUnit | NSWeekCalendarUnit | NSDayCalendarUnit | NSHourCalendarUnit ) fromDate:[NSDate date]];
	[components setHour:18];
	NSDate *todayAt6PM = [calendar dateFromComponents:components];