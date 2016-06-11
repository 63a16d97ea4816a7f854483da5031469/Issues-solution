#When you are looping a MutableArray, then delete its record inside.

In Java, Iterating through a Collection when removing in loop, it will cause: <font color="red"><b>ConcurrentModificationException </b></font>

Exception in thread "main" java.util.ConcurrentModificationException  

Java is collection, objective-c one is NSMutableArray.  A reminder for this kind of issue.

NSMutableArray 
ArrayList

<b>The behavior is different!!</b>


In Objective-c, we can delete its records when you are looping the Array.

> We should do something like this:

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
            
            

> We should avoid this kind of behavior:

<b>[Wrong code]</b>:

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