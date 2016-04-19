#How do I store and retrieve an NSMutableDictionary to and from NSUserDefaults?

http://stackoverflow.com/questions/10118586/how-do-i-store-and-retrieve-an-nsmutabledictionary-to-and-from-nsuserdefaults

 
You get a immutable dictionary back. You do not need to "capsulate" it in another dictionary. If you want to make it mutable write:

NSMutableDictionary* animals = [[defaults objectForKey:@"animals"] mutableCopy];


