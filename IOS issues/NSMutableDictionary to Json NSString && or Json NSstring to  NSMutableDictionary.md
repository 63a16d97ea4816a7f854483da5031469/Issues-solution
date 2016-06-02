# NSMutableDictionary to Json NSString && or Json NSstring to  NSMutableDictionary

##NSMutableDictionary to Json NSString:

	  NSMutableArray *logArr=[NSMutableArray new];
	    [logArr addObject:@"the first layer"];
	    [logArr addObject:@"the second layer"];
	    
	    NSMutableDictionary *jsonDict=[NSMutableDictionary new];
	    [jsonDict setObject:logArr forKey:@"logs"];
	    
	    NSData *jsonData = [NSJSONSerialization dataWithJSONObject:jsonDict options:0 error:nil];
	    
	    // Checking the format
	    NSString *jsonString =  [[NSString alloc] initWithData:jsonData encoding:NSUTF8StringEncoding];
	    
	    NSLog(@"the json:%@",jsonString);

##Json NSstring to  NSMutableDictionary
    
    NSString * jsonString=@"{"logs":["the first layer","the second layer"]}";
    
    NSStringEncoding  encoding=NSUTF8StringEncoding;
    NSData * deJsonData = [jsonString dataUsingEncoding:encoding];
    NSError * error=nil;
    NSDictionary * parsedData = [NSJSONSerialization JSONObjectWithData:deJsonData options:kNilOptions error:&error];
    NSLog(@"the perseData:%@",parsedData);
    
    