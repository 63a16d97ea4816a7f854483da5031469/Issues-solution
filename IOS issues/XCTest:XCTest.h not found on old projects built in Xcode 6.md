#XCTest/XCTest.h not found on old projects built in Xcode 6

In order to fix this for any CocoaPod dependencies you need to add the following to FRAMEWORK_SEARCH_PATHS in any Pod target that requires XCTest (e.g. Kiwi, Specta, FBSnapshotTestCase, etc).

$(PLATFORM_DIR)/Developer/Library/Frameworks


This solved the issue mentioned above but other issue appeared:

	dyld: Library not loaded: @rpath/XCTest.framework/XCTest
	  Referenced from: /Users/Tony/Library/Developer/CoreSimulator/Devices/F0397859-8F2C-41F7-8618-EF915099A56C/data/Containers/Bundle/Application/F1C6B01A-A11B-46A6-BD3B-0B058F64749E/DropboxTry.app/DropboxTry
	  Reason: image not found


http://stackoverflow.com/questions/24275470/xctest-xctest-h-not-found-on-old-projects-built-in-xcode-6


http://stackoverflow.com/questions/26104975/dyld-library-not-loaded-rpath-libswiftcore-dylib-image-not-found