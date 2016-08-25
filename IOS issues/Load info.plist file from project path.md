#Load info.plist file from project path

    typeof(self) weakSelf = self;
    
    dispatch_after(dispatch_time(DISPATCH_TIME_NOW, (int64_t)(0.5 * NSEC_PER_SEC)), dispatch_get_main_queue(), ^{
        
        NSString *path = [[NSBundle mainBundle] pathForResource:@"abc.plist" ofType:nil];
        
        NSDictionary *Dict = [NSDictionary dictionaryWithContentsOfFile:path];
        
        weakSelf.list = [Model mj_objectArrayWithKeyValuesArray: Dict[@"data"][@"list"]];
        
        [weakSelf.tableView reloadData];
   
    });