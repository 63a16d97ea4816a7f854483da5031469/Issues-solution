#Convert NSDate to Unix timestamp

http://stackoverflow.com/questions/3023264/how-to-convert-nsdate-into-unix-timestamp-in-objective-c-iphone

	NSTimeInterval ti = [[NSDate date] timeIntervalSince1970];


##What unit of time does timeIntervalSinceDate return?

It returns the number of seconds, as an NSTimeInterval value.

From this documentation page:

>> <font color="red">NSTimeInterval</font> is always specified in seconds; it yields sub-millisecond precision over a range of 10,000 years.