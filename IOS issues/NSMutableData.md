##NSMutableDate

##How to append the NSData

If you need to concatenate multiple NSData objects into one then something like this will work:

NSData *data1 = ... // the 1st NSData object
NSData *data2 = ... // the 2nd NSData object
NSData *data3 = ... // the 3rd NSData object
NSMutableData *completeData = [data1 mutableCopy];
[completeData appendData:data2];
[completeData appendData:data3];


http://stackoverflow.com/questions/17284761/how-to-concatenate-multiple-nsdata