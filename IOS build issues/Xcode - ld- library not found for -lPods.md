#issue:Xcode - ld: library not found for -lPods


##Solution:
After hours of research this solution worked for me:

(disclaimer: results may vary due to circumstances)

the Library not found -lPods-(someCocoapod) error was due to multiple entries in the :

Settings(Target) > Build Settings > Linking > 'Other Linker Flags'
A lot of other posts had me look there and I would see changes to the error when I messed around with the entries, but I kept getting some variation on the same error.

Too many hours lost ...

My Fix:
remove the -lPods-(someCocoaPod) lines in the 'Other Linker Flags' list BUT only if $(inherited) is at the top. At first I was unsure, but the reassuring sign was that I still saw references to my cocoapods when I left the edit mode(inherited). I tested in debug and release, both of which were giving me errors, and the problem was immediately resolved.



http://blog.csdn.net/ioswyl88219/article/details/21455573



Case: run the project one second later will get the same error mentioned above:

Solution: remove the libpod.a from the linked Frameworks and Libraries.
