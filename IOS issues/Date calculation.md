##Date calculation

####The first day of month:

	NSDate *today = [NSDate date];
	NSCalendar *gregorian = [[NSCalendar alloc] initWithCalendarIdentifier:NSGregorianCalendar];
	
	NSDateComponents *components = [gregorian components:(NSEraCalendarUnit | NSYearCalendarUnit | NSMonthCalendarUnit) fromDate:today];
	components.day = 1;
	
	NSDate *dayOneInCurrentMonth = [gregorian dateFromComponents:components];

####The last day of month:
	-(NSDate*)lastDayOfMonth
	{
	    NSInteger dayCount = [self numberOfDaysInMonthCount];
	
	    NSDateComponents *comp = [[self calendar] components:
	                              NSCalendarUnitYear |
	                              NSCalendarUnitMonth |
	                              NSCalendarUnitDay fromDate:self];
	
	    [comp setDay:dayCount];
	
	    return [[self calendar] dateFromComponents:comp];
	}

####The Number of days in month:

	-(NSInteger)numberOfDaysInMonthCount
	{
	    NSRange dayRange = [[self calendar] rangeOfUnit:NSCalendarUnitDay
	                                             inUnit:NSCalendarUnitMonth
	                                            forDate:self];
	
	    return dayRange.length;
	}
