#NSDictionary objectForKey Vaule should be converted before using.

Wrong code:

	 NSString *newUserId=[response objectForKey:@"id"];
	                 if(newUserId!=nil&&![newUserId isEqualToString:@""]){
	                 
	                 }
 
	[response objectForKey:@"id"]


	2016-08-22 16:20:06.606 xxxxx[15988:579080] create new userId: 39203
	2016-08-22 16:20:06.606 xxxxx[15988:579080] -[__NSCFNumber isEqualToString:]: unrecognized selector sent to instance 0xb000000000099233
	2016-08-22 16:20:06.614 xxxxx[15988:579080] *** Terminating app due to uncaught exception 'NSInvalidArgumentException', reason: '-[__NSCFNumber isEqualToString:]: unrecognized selector sent to instance 0xb000000000099233'
	*** First throw call stack:
	
	
Use below code ==right:  

	 NSString *newUserId=[NSString stringWithFormat:@"%@",[response objectForKey:@"id"]];
                 if(newUserId!=nil&&![newUserId isEqualToString:@""]){
                 
                 }