#iOS NSDateFormatter returns wrong date from string

                NSLog(@"the saved:%@",KeyExpirationDateStr);
                NSDateFormatter *dateFormat = [[NSDateFormatter alloc] init];
                [dateFormat setDateFormat:@"dd-MMM-yyyy HH:mm:ss"];

                NSDate *expirationDate = [dateFormat dateFromString:KeyExpirationDateStr];
                NSLog(@"Expiration Nsdate=%@",expirationDate);
                
                
The saved date is: 23-Jun-2016 14:50:04

I tried to convert it to NSDate from String.

But if I use:
<font color="red">        [dateFormat setDateFormat:@"dd-MMM-YYYY HH:mm:ss"];
</font>

The returned date will be: 2015-12-21..... 

##Solution
http://stackoverflow.com/questions/14838591/ios-nsdateformatter-returns-wrong-date-from-string
<font color="green">        
I think the issue is that you're using YYYY instead of yyyy. The uppercase variant is for "week of year" based calendars (see the UTS spec for more), which isn't actually the same as getting the literal calendar year in many (most?) situations. Using @"EEEE MMM d, yyyy" as the date formatter may fix this for you.
</font>
     
        
        