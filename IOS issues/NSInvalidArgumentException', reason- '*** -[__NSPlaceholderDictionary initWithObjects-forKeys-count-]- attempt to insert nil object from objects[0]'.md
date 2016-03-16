Error message:

NSInvalidArgumentException', reason: '*** -[__NSPlaceholderDictionary initWithObjects:forKeys:count:]: attempt to insert nil object from objects[0]'


Reason:

NSString==>userIDstr is nil:

   NSDictionary *params = @{   @"userId"   : userIdStr,
                                @"api_key"  : API_KEY};


If you try to add the nil into the NSDictionary then you will get the above error message.