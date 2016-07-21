#Too many arguments to function call, expected 0, have 3

Xcode > Build Settings > Enable Strict Checking of objc_msgSend Calls = Yes

it is the cocoapods' bug:
downgrade to below version:

sudo gem install cocoapods -v 0.35.0


####<font color=red>This is the right solution:</font>

You can also disable this with a post install hook:

post_install do |installer|
    installer.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['ENABLE_STRICT_OBJC_MSGSEND'] = 'NO'
        end
    end
end