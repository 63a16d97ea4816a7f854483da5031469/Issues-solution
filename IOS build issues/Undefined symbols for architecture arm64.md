##Undefined symbols for architecture arm64
http://stackoverflow.com/questions/19213782/undefined-symbols-for-architecture-arm64

###solution
If your Architectures & Valid Architectures are all right, you may check whether you have add $(inherited) to Other Linker Flags as below. enter image description here
<img src="screenshots/arm64.jpg">