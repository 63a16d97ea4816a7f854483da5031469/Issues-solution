#Error during submission

The archive did not contain <DVTFilePath:0x7f9a1672aac0:'/Users/Adam/Library/
Developer/Xcode/Archives/2015-10-03/final_project 03.10.15 19.28.xcarchive/
BCSymbolMaps/989F2A46-2149-3CE5-AFD1-1614968AE31C.bcsymbolmap'> as expected.

##Solution:
It's likely you built your app with Enable Bitcode set to NO in build settings.

Then, in the app submission window, you had "include bitcode" checked, which is now at the bottom of the window. Uncheck that and it should submit. Enable bitcode in your build settings if you want to then submit with bitcode.