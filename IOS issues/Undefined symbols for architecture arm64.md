# Undefined symbols for architecture arm64

http://stackoverflow.com/questions/19213782/undefined-symbols-for-architecture-arm64

##solution:	 	
Simple Solution Go to Target ->Linking -> other linker Flag and add $(inherited) in other linker flag in both Debug and Release. – Mihir Oza Feb 3 at 11:10