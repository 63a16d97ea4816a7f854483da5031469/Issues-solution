#substringToIndex 

    
    NSString *testString = @"I love programming in objective-c";
    testString=[testString substringToIndex:[testString rangeOfString:@"objective-c"].location];
    NSLog(@"==>%@",testString);