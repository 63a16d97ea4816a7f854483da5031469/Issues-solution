#Comparing objects in Obj-C


if(![myArray containsObject:anObject]) {
    [myArray addObject:anObject];
}

== will compare the pointer, you need to override

	- (BOOL)isEqual:(id)anObject	