Setting Xcode Build Settings Terminal

http://stackoverflow.com/questions/32743012/setting-xcode-build-settings-terminal

All Xcode settings is actually store in <project-name>.xcodeproj/project.pbxproj . It looks like

buildSettings = {
    CODE_SIGN_ENTITLEMENTS = "";
    CODE_SIGN_IDENTITY = "iPhone Developer";
    "CODE_SIGN_IDENTITY[sdk=iphoneos*]" = "iPhone Developer";

    ...

    PRODUCT_NAME = "$(TARGET_NAME)";
    PROVISIONING_PROFILE = "";
    SKIP_INSTALL = YES;
};
Code Signing Identity is controlled by CODE_SIGN_IDENTITY key and Provisioning Profile is controlled by PROVISIONING_PROFILE key.

The project.pbxproj is a text file that can be edited by traditional text processing tools in CLI, such as sed with

sed -ie 's/CODE_SIGN_IDENTITY = "iPhone Developer"/CODE_SIGN_IDENTITY = ""/g' <project-name>.xcodeproj/project.pbxproj
sed -ie 's/PROVISIONING_PROFILE = ""/PROVISIONING_PROFILE = "1c28c979-6bef-4917-aa34-92aecd91315c";/g' <project-name>.xcodeproj/project.pbxproj
You can get the list of available Signing Identities with

security find-identity -v -p codesigning
For PROVISIONING_PROFILE, it's a UUID of provisioning file, it can be fetched with

grep -aA1 UUID /path/to/mobileprovision