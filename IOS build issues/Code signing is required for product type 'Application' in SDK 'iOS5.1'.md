##Code signing is required for product type 'Application' in SDK 'iOS8.4'

http://stackoverflow.com/questions/9899920/code-signing-is-required-for-product-type-application-in-sdk-ios5-1

One possible solution which works for me:

Search "code sign" in Build settings
Change everything in code signing identity to "iOS developer", which are "Don't code sign" originally.
