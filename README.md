# SFTP Download Manager
SFTP manager that download latest files from Zurich Server\
##
### Tasks handled 
- It handle all MW paths and files at Zurich server: MW528 (4kv2, 4kv1 and dci738), MW524 (4Kv1) and MW513(all NGs)
- Checks into three files (for each MW) if the latest build name is there
- If not there we are not up-to date. So we create the build folder locally
- For each folder in remote, we create the folder locally and download the files inside it. Always respecting the 
structure locally and the list of folders that shouldn't be downloaded (not a copy from remote to local)
- Finished we put the build name on respective MW file from step 2.  
- It run between 7pm and 7am inside QA server.
- It not recursive since we need to maintain the structure of folders locally (to not crash the app that flash set-top boxes)    


###External Libs 
Paramiko and tqdm (not essential)


###Future implementation
- It should have a specific file that handle with logs (today all files import it)
- It should fix and test the Open Stack manager. With this new process, we should handle SFTP and Open Stack.\
To do that we need check the emails and look for the links with the builds to download from there.\
Another way is look for the JIRA ticket and go through directly. 
