###How do I force Xcode to rebuild the Info.plist file in my project every time I build the project?

http://stackoverflow.com/questions/3730186/how-do-i-force-xcode-to-rebuild-the-info-plist-file-in-my-project-every-time-i-b

Select 'Edit Scheme', then select 'Build' from the control on the left.

Then, add a Pre-actions step, ensure the scheme in question is selected in the 'Provide build settings from' pulldown and then add this into the edit window below:

rm "${CONFIGURATION_BUILD_DIR}/${INFOPLIST_PATH}"
This will delete the cached version of Info.plist, causing XCode to rebuild it each time you hit build.

----------------------------------------------------
**force Xcode to rebuild the Info.plist file in my project every time I build the project**
Note: This is not the same as a run script build phase. A pre build action happens before Xcode checks the info plist, a run script build phase seems to happen after Xcode has already checked the info plist (which is why it only works every other time).

Go to Edit Scheme > Build > Pre-actions
Click the "+" button and choose "New Run Script Action"
Choose your target in the "Provide build settings from" dropdown
Add touch "${SRCROOT}/${INFOPLIST_FILE}" in the script box

----------------------------------------------------
**Copying plist to document directory**
IOS restricts writing to bundled files. If you want a writable plist, you need to copy it to your app's Documents folder and write to it there.


	+ (NSString*) getPlistPath:(NSString*) filename{
	    //Search for standard documents using NSSearchPathForDirectoriesInDomains
	    //First Param = Searching the documents directory
	    //Second Param = Searching the Users directory and not the System
	    //Expand any tildes and identify home directories.
	    NSArray *paths = NSSearchPathForDirectoriesInDomains(NSDocumentDirectory , NSUserDomainMask, YES);
	    NSString *documentsDir = [paths objectAtIndex:0];
	    return [documentsDir stringByAppendingPathComponent:filename];
	}
	+ (void) copyPlistFileToDocument{
	    NSFileManager *fileManager = [NSFileManager defaultManager];
	    NSError *error;
	    NSString *dbPath = [Utilities getPlistPath:@"AppStatus.plist"];
	    if( ![fileManager fileExistsAtPath:dbPath])
	    {
	        NSString *defaultDBPath = [[NSBundle mainBundle] pathForResource:@"AppStatus" ofType:@"plist"];
	            BOOL copyResult = [fileManager copyItemAtPath:defaultDBPath toPath:dbPath error:&error];
	            if(!copyResult)
	                    NSAssert1(0, @"Failed to create writable plist file with message '%@'.", [error localizedDescription]);
	    }
	
	}


How to copy a Plist file from your app bundle into the documents file on the first run of the application. This allows your to ship your app with pre populated data that the user can then edit and save. If you don't need them to edit and save the data it can simply reside in the app bundle all the time no need to copy it to your documents folder.



##Read values from plist
	+(id) getObjectsFromInfoPlistWithKey:(NSString*) key {
		return [[NSBundle mainBundle] objectForInfoDictionaryKey:key];
	}

    NSDictionary* urlTypes = [[Objects getObjectFromInfoPlistWithKey:@"CFBundleURLTypes"] objectAtIndex:0];  
    urlScheme = [[urlTypes objectForKey:@"CFBundleURLSchemes"] objectAtIndex:0];


	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
	<plist version="1.0">
	<key>CFBundleURLTypes</key>
	<array>
		<dict>
			<key>CFBundleURLName</key>
			<string>xxx.xx.xxx.xx</string>
			<key>CFBundleURLSchemes</key>
			<array>
				<string>xxxxx</string>
			</array>
		</dict>
	</array>
	</plist>

###IPhone: preserve user data against app update 

Any data saved in the user Documents folder will remain intact during and after an update.

Files Saved During Application Updates

When a user downloads an application update, iTunes installs the update in a new application directory. It then moves the user’s data files from the old installation over to the new application directory before deleting the old installation. Files in the following directories are guaranteed to be preserved during the update process:

< Application_Home > / Documents

< Application_Home > / Library

Although files in other user directories may also be moved over, you should not rely on them being present after an update.

