#AFnetworking get StatusCode

    [self POST:[NSString stringWithFormat:@"%@xxxxxx//authn/token",xxxx_HOST] parameters:params success:^(NSURLSessionDataTask *task, id responseObject) {
        NSDictionary *response = (NSDictionary *) responseObject;
        NSLog(@"HIDToken response: %@", response);
        
        NSInteger statusCode = 0;
        NSHTTPURLResponse *httpResponse = (NSHTTPURLResponse *)task.response;
        
        if ([httpResponse isKindOfClass:[NSHTTPURLResponse class]]) {
            statusCode = httpResponse.statusCode;
        }