#cocoapods installation stuck on “Updating local specs repositories”

http://stackoverflow.com/questions/34522708/cocoapods-installation-stuck-on-updating-local-specs-repositories


There's an known error with http://blog.cocoapods.org/Repairing-Our-Broken-Specs-Repository/

You can try to fix it by doing:

pod repo remove master
pod setup
pod install