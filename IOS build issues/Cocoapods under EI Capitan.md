#Cocoapods issue under OS X 10.11.1 (EI Capitan)

	sudo gem install cocoapods

Then encountered this error below:  
ERROR:  While executing gem ... (Errno::EPERM)
    Operation not permitted - /usr/bin/xcodeproj
    
Solution:  
> http://stackoverflow.com/questions/30812777/cannot-install-cocoa-pods-after-uninstalling-results-in-error/30851030#30851030

As it has been pointed out below, this is a cleaner way of doing it, instead of getting around the Security features of OS X.

sudo gem install -n /usr/local/bin cocoapods

Im assuming you're running OS X 10.11.

This is happening because Apple has enabled rootless on the new install.

If you type sudo nvram boot-args="rootless=0"; sudo reboot in terminal.app Your computer will reboot with it disabled.

Once that is done, type

sudo gem install cocoapods -V

the -V is for verbose and will spit out any errors if they happen.



Also tried this one: updated the ruby.

Using home-brew or custom $GEM_HOME can help resolving the issue. I did clean installation of ruby with brew: 
brew install ruby
Now the gem stuff seem to happen relative to my /usr/local/bin*, which is exactly what I needed.

Then everything is fine.


