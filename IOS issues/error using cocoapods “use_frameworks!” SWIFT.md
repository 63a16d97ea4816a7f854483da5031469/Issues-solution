#error using cocoapods “use_frameworks!” SWIFT

Using Swift written library:

I updated my podfile adding "use_frameworks!"

My podfile is now:

	# Uncomment this line to define a global platform for your project
	# platform :ios, '8.0'
	use_frameworks!
	
	source 'https://github.com/CocoaPods/Specs.git'
	
	target 'isam' do
	pod 'RESideMenu', '~> 4.0.7'
	pod 'AFNetworking', '~> 2.5'
	pod 'Parse', '~> 1.6'
	pod 'STZPopupView', '~> 1.0'
	end
	
	target 'isamTests' do
	
	end

