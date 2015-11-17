##Android build checklist:

-->Before the build, I need to create the release and sent out to the whole team.

==>check whether the release note is sent out to users already. 

If yes, then do the following steps:

Go to https://jira.xxx.com/browse/MDSRE-xx

create sub-task according to previous :

upload the release note by using the "Select files" button.

Issue Links:
connect to all the related fixed JIRA ticket. (only JIRA)  To this created sub-task.

Android build checklist:

--Using Android Studio:

1. Go to sub-folder of specific market, to modify the Version number and build number in "AndroidManifest.xml" under "xxx_marketName_stg".   
2. Build-->"Generate Signed APK"--->Choose the specifc market--> click next.
3. "Key Store": release-key.keystore
4. Fill in the field called "key store password".
5. Choose the "mykey".
6. Fill in the field called "Key password".
7. Choose the "APK Destination Folder"
8. For "Build Type", using the "release".
9. Click "Finish". 
10. Do the testing and write the testing excel file.
11. Inform project manager of the testing result.
12. Wait for project manager's command to publish the release by using Android Play Console.
13. After releasing the apps, I need to check the links sent out to make sure it is right(version is right and can be download).
14. Report the release result.


