#substring from start and substring from end of NSString

   NSRange range2 = [tempUrl rangeOfString:@".com"];

   finalURL=[tempUrl substringWithRange:NSMakeRange(0, range2.location+4)];

   NSLog(@"your URL is %@",finalURL); //prints www.yahoomail.com


NSString *lastFourChar = [yourNewString substringFromIndex:[yourNewString length] - 4];
