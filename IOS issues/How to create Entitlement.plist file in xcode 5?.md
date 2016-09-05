#How to create Entitlement.plist file in xcode 5?

http://stackoverflow.com/questions/19674514/how-to-create-entitlement-plist-file-in-xcode-5

You can manually create an Entitlements.plist file using the template below.

Save it as YourTargetName.entitlements

In your Target > Build Settings, set the key "Code Signing Entitlements" (CODE_SIGN_ENTITLEMENTS) to the file's path.

	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
	<plist version="1.0">
	<dict>
	    <key>application-identifier</key>
	    <string>$(AppIdentifierPrefix)$(CFBundleIdentifier)</string>
	    <key>beta-reports-active</key>
	    <true/>
	</dict>
	</plist>