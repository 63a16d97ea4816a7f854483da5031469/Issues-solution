#How to import Swift code to Objective-C

Here's what to do :

1.Create a new Project in ObjC  
2.Create a new .swift file 
 
 * A popup window will appear and ask "Would You like to configure an Objective-C bridging Header".
 
 * Choose Yes.

3.Click on your Xcode Project file  
4.Click on Build Settings  
5.Find the Search bar and search for Defines Module.  
6.Change the value to Yes.  
7.Search Product Module Name.  
8.Change the value to the name of your project.  
9.In App delegate, add the following : 
>\#import   "YourProjectName-swift.h"

Note: Whenever you want to use your Swift file you must add the following line :

#Import "YourProjectName-swift.h"

