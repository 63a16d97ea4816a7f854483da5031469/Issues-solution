#When you are looping a MutableArray, then delete its record inside.

In Java, this will cause exception.

In Objective-c, we should avoid this kind of behavior:

            for(int i=0;i<_data.lists.count;i++){
                PlanList* tmp=[_data.lists objectAtIndex:i];
  
                //change the '1' items to '0' items.
                if([tmp.markStr isEqualToString:@"1"]){
                    tmp.markStr=@"0";
                }
                
                if([tmp.timeLength rangeOfString:@"$"].location!=NSNotFound){
                    [_data.lists removeObjectAtIndex:i];
                }
            }
            
            
> We should do something like this:

            NSMutableArray *newTmpArr=[NSMutableArray arrayWithArray:[_data.lists copy]];
            
            for(int i=0;i<_data.lists.count;i++){
                PlanList* tmp=[_data.lists objectAtIndex:i];
                NSLog(@"data list:%@ markStr:%@",tmp.listTitle,tmp.markStr);
                //change the '1' items to '0' items.
                if([tmp.markStr isEqualToString:@"1"]){
                    tmp.markStr=@"0";
                }
                
                if([tmp.timeLength rangeOfString:@"$"].location!=NSNotFound){
                    [newTmpArr removeObjectAtIndex:i];
                }
            }
            _data.lists=newTmpArr;