#[NSBundle mainBundle] pathForResource

    NSURL *URL=[NSURL fileURLWithPath:[[NSBundle mainBundle] pathForResource:@"index" ofType:@"html"] isDirectory:NO];
    
If you would like to use above way to get the file, you need to add your file into the Build Phases-->Copy Bundle Resources.

Otherwise, it will be always nil.