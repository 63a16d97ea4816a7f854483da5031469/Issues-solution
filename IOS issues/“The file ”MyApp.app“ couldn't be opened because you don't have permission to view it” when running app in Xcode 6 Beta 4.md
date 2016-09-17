#“The file ”MyApp.app“ couldn't be opened because you don't have permission to view it” when running app in Xcode 6 Beta 4

#####Solution:

In Xcode do the following

Window --> Organiser --> Projects --> The app with the issue --> delete button in Derived Data.

I then cleaned the project and voila

works