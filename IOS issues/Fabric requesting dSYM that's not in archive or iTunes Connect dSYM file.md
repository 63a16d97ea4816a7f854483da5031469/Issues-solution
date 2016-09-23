#Fabric requesting dSYM that's not in archive or iTunes Connect dSYM file

http://stackoverflow.com/questions/35635874/fabric-requesting-dsym-thats-not-in-archive-or-itunes-connect-dsym-file


To help find where the dSYM is located, run this command in an open terminal:

mdfind "com_apple_xcode_dsym_uuids == <UUID>"
To find all dSYM try

mdfind "com_apple_xcode_dsym_uuids == *"
Also, if you upload a dSYM to Fabric, you should check that the UUID matches the one that is missing. Running this command in an open terminal will give you the UUID of the dSYM.

dwarfdump -u <PathToYourAppsDsym>




https://krausefx.com/blog/download-dsym-symbolication-files-from-itunes-connect-for-bitcode-ios-apps