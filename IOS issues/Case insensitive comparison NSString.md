#Case insensitive comparison NSString

http://stackoverflow.com/questions/2582306/case-insensitive-comparison-nsstring

if ([[stringX uppercaseString] isEqualToString:[stringY uppercaseString]]) {
    // They're equal
}

- (NSComparisonResult)caseInsensitiveCompare:(NSString *)aString

if( [@"Some String" caseInsensitiveCompare:@"some string"] == NSOrderedSame ) {
  // strings are equal except for possibly case
}