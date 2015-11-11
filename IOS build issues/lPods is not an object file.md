##Cocoapods - can't locate file for: -lPods / -lPods is not an object file (not allowed in a library)

**http://stackoverflow.com/questions/23090734/cocoapods-cant-locate-file-for-lpods-lpods-is-not-an-object-file-not-al**

Cocoapods - can't locate file for: -lPods / -lPods is not an object file (not allowed in a library)


(https://github.com/CocoaPods/CocoaPods/releases/tag/0.38.0.beta.1), the object passed to the Podfile post-install hook has changed.

you probably just want to change project to pods_project.


Modified from:
post_install do |installer_representation|
    installer_representation.project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['ONLY_ACTIVE_ARCH'] = 'NO'
        end
    end
end

<font size=5>To:</font>

post_install do |installer_representation|
    installer_representation.pods_project.targets.each do |target|
        target.build_configurations.each do |config|
            config.build_settings['ONLY_ACTIVE_ARCH'] = 'NO'
        end
    end
end