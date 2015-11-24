#IOS & Android build checklist

- Build binaries. Derive version and build numbers from existing versions, can also check crashlytics/google play/our server to be sure. Increment the version and build number for production apps even if we do not build it so that this number is reserved and we do not have to worry about conflicts.

- Test the builds in the real phone and using the template file as basecopy to create new file called testing file in the specific server folder to record all the issues you find. 

- Create new ticket in Bugzilla ticket system for each issue you find and update the testing file in the server.

- Commit and tag the release.

- Upload binaries to our server.

- Upload release note to our server.

- Upload release note to JIRA Ticket System.

- Create Bugzilla milestone, update release note's bugzilla tickets' Target Milestone field with new milestone.

- After getting approval from PM, upload binaries to crashlytics/google play, and send out email for google play by using the google group post.