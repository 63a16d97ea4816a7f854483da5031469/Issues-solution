#NSURLErrorDomain error code -999 in iOS


The error has been documented on the Mac Developer Library(iOS docs)

The concerned segment from the documentation will be:

URL Loading System Error Codes

These values are returned as the error code property of an NSError object with the domain “NSURLErrorDomain”.

enum
{
   NSURLErrorUnknown = -1,
   NSURLErrorCancelled = -999,
   NSURLErrorBadURL = -1000,
   NSURLErrorTimedOut = -1001,
As you can see; -999 is caused by ErrorCancelled. This means: 
**another request is made before the previous request is completed.**


