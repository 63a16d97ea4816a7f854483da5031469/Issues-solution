#Google Drive - To avoid this error on v3

To avoid this error on v3

"The resource body includes fields which are not directly writable."
when calling update, you need to create an empty File with the new changes and pass that to the update function.

I wrote this and other notes as a v3 Migration Guide here.