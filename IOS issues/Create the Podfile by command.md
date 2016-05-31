#Create the Podfile by command

Run the following commands to create the Podfile, install the library, and open the resulting XCode project:

cat << EOF > Podfile &&
platform :ios, '7.0'
pod 'GoogleAPIClient/Drive', '~> 1.0.2'
pod 'GTMOAuth2', '~> 1.1.0'
EOF
pod install &&
open QuickstartApp.xcworkspace
