#Provisioning Profiles have a UUID

Command line to get the Profile_UUID:
	grep -aA1 UUID Tony_In_House_Profile.mobileprovision 

<key>UUID</key>
		<string>cab9befa-b4f4-45bb-9e40-f3995e927e49</string>


Provisioning Profiles have a UUID that can be seen using the Terminal command:

security cms -D -i (path_to_your_provisioning_profile)
See the UUID section of the command output like:

<key>UUID</key>
    <string>A008C022-7B82-4E40-8B37-172763E1E3CC</string>

Xcode inserts the provisioning profile used to sign the application within the .app bundle. To find it, rename your .ipa to .zip, uncompress it with Finder, find the .app file in /Payload. "Show Package Contents" on the .app file and find the provisioning profile with the name embedded.mobileprovision.

Dump its entitlements using the above command and compare that with the UUID found within your profiles in your Xcode Organizer > Devices tab > Provisioning Profile section under "Library". You can use "Show in Finder" on those to reveal their location on disk.