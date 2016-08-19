#How do I find the last occurrence of a substring in an NSString?

http://stackoverflow.com/questions/2440137/how-do-i-find-the-last-occurrence-of-a-substring-in-an-nsstring

Use rangeOfString:options:, including NSBackwardsSearch in the options.

	[@"abc def ghi abc def ghi" rangeOfString:@"abc" options:NSBackwardsSearch];
