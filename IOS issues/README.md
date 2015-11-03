# IOS issues

###iOS 9 Xcode 7 - Application appears with black bars on top and bottom

http://stackoverflow.com/questions/32641240/ios-9-xcode-7-application-appears-with-black-bars-on-top-and-bottom

**My App does not use a launch image. Setting the "Launch Screen File" to my "main.storyboard" file fixed the issue for me.**

This setting can be found under "Target->General->App Icons and Launch Images"

Use the following link for more information: http://oleb.net/blog/2014/08/replacing-launch-images-with-storyboards/


###The resource could not be loaded because the App Transport Security policy requires the use of a secure connection

>* Errors get from the xcode:  

>> An error occured : Error Domain=NSURLErrorDomain Code=-1022 "The resource could not be loaded because the App Transport Security policy requires the use of a secure connection." 

>>Error Domain=NSURLErrorDomain Code=-1200 "An SSL error has occurred and a secure connection to the server cannot be made.  
>CFNetwork SSLHandshake failed (-9824)


From Apple's document:  
https://developer.apple.com/library/prerelease/ios/technotes/App-Transport-Security-Technote/

All connections using the NSURLConnection, CFURL, or NSURLSession APIs use App Transport Security default behavior in apps built for iOS 9.0 or later, and OS X v10.11 or later. Connections that do not follow the requirements will fail. For more information on various the connection methods, see NSURLConnection Class Reference, CFURL Reference, or NSURLSession Class Reference.

	 <key>NSAppTransportSecurity</key>  
	  <dict>  
 	   <key>NSAllowsArbitraryLoads</key>  
 	   <true/>  
 	  </dict>  


#String cannot be localized --bug in app:


- (UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath
{
    HeaderTableViewCell *cell = (HeaderTableViewCell*)[tableView dequeueReusableCellWithIdentifier:CELL_ID_TITLE forIndexPath:indexPath];
    cell.accessoryType = UITableViewCellAccessoryNone;
    
    cell.headerLabel.text = [LocaleHelper getLocalizedStringWithKey:[titleList objectAtIndex:indexPath.row]];

    return cell;
}

#Word display: linewarp


For delivery date and time line wrap:

        self.deliveryTime = [[UILabel alloc] initWithFrame:CGRectMake(20, 31, 260, 50)];

        self.deliveryTime.numberOfLines = 0;

* First, you need to set the numberOfLines=0.
* Second, you need to make sure the height of the UILabel is enough for display two or three(more than one line) as you want.(notice: the height will be affected by the font you set for the string.)


>The below sentence is not supported in below IOS 6, but this one can control whether to display "...." when there contains extra words cannot be displayed.

	   self.deliveryTime.lineBreakMode = NSLineBreakByCharWrapping;  // this will hide the "......", even there are extra words cannot be shown.


## NSAttributedString:
http://blog.csdn.net/zhangao0086/article/details/7616385

	//把this的字体颜色变为红色  
	[attriString addAttribute:(NSString *)kCTForegroundColorAttributeName  
	                    value:(id)[UIColor redColor].CGColor   
	                    range:NSMakeRange(0, 4)];  
	//把is变为黄色  
	[attriString addAttribute:(NSString *)kCTForegroundColorAttributeName  
	                    value:(id)[UIColor yellowColor].CGColor   
	                    range:NSMakeRange(5, 2)];  
	//改变this的字体，value必须是一个CTFontRef  
	[attriString addAttribute:(NSString *)kCTFontAttributeName  
	                    value:(id)CTFontCreateWithName((CFStringRef)[UIFont boldSystemFontOfSize:14].fontName,  
	                                                   14,   
	                                                   NULL)  
	                    range:NSMakeRange(0, 4)];  
	//给this加上下划线，value可以在指定的枚举中选择  
	[attriString addAttribute:(NSString *)kCTUnderlineStyleAttributeName  
	                    value:(id)[NSNumber numberWithInt:kCTUnderlineStyleDouble]  
	                    range:NSMakeRange(0, 4)];  
	return attriString;  