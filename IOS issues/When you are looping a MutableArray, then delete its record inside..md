#When you are looping a MutableArray, then delete its record inside.

In Java, Iterating through a Collection when removing in loop, it will cause: <font color="red"><b>ConcurrentModificationException </b></font>

Exception in thread "main" java.util.ConcurrentModificationException  

Java is collection, objective-c one is NSMutableArray.  A reminder for this kind of issue.

NSMutableArray 
ArrayList

<b>The behavior is the same!!</b>


In Objective-c, we can not delete its records when we are looping the Array.

> We should not do something like this:

            for(int i=0;i<_data.lists.count;i++){
                ListObj* tmp=[_data.lists objectAtIndex:i];
  
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

            for(ListObj *tmp in _data.lists){
                NSLog(@"data list:%@ markStr:%@",tmp.listTitle,tmp.markStr);
                //change the '1' items to '0' items.
                if([tmp.markStr isEqualToString:@"1"]){
                    tmp.markStr=@"0";
                }
                
                //remove the financial records.
                if([tmp.timeLength rangeOfString:@"$"].location!=NSNotFound){
                    [_data.lists removeObject:tmp];
                }
            }







Collection <__NSArrayM: 0x126d63f00> was mutated while being enumerated.'



<b>[Right code]:</b>

          {
            [[NSUserDefaults standardUserDefaults] setValue:dateStr forKey:@"date_Str"];
            NSLog(@"not the same day!");
       

            
            for(int i=0;i<_data.lists.count;i++){
                ListObj* oldtmp=[_data.lists objectAtIndex:i];
 
                NSLog(@"data list:%@ markStr:%@",oldtmp.listTitle,oldtmp.markStr);
                //change the '1' items to '0' items.
                if([oldtmp.markStr isEqualToString:@"1"]){
                    oldtmp.markStr=@"0";
                }
      
            }
            
            NSMutableArray *newTmpArr=[NSMutableArray arrayWithArray:[_data.lists copy]];
            
            for(ListObj *tmpSec in _data.lists){
                //remove the financial records.
                if([tmpSec.timeLength rangeOfString:@"$"].location!=NSNotFound){
                    if([newTmpArr containsObject:tmpSec]){
                        [newTmpArr removeObject:tmpSec];
                    }
                }
                
            }
            
            _data.lists=newTmpArr;
        }
            
            
   