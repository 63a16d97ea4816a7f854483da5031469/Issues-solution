#How to set date format to 24 hour in Objective-c?

	NSDateFormatter* dateFormatter = [[NSDateFormatter alloc] init];
	NSLocale *locale = [[NSLocale alloc] initWithLocaleIdentifier:@"en_GB"];
	[dateFormatter setLocale:locale];
	

            NSDateFormatter *dateFormat = [[NSDateFormatter alloc] init];
            [dateFormat setDateFormat:@"dd-MMM-YYYY HH:mm:ss"];
            [dateFormat setTimeZone:[NSTimeZone defaultTimeZone]];
            NSString *datestr = [dateFormat stringFromDate:firstDate];

	
	
UIDatePicker inside the UITableView:
	
    ALEDatePickerCell *cell = [self.tableView dequeueReusableCellWithIdentifier:DateCellIdentifier];
    
    cell.datePicker.datePickerMode = UIDatePickerModeDateAndTime;
    cell.datePicker.locale=[[NSLocale alloc] initWithLocaleIdentifier:@"en_GB"];