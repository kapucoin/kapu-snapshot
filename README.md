# kapu-snapshot
A bash script to automate backups for KAPU blockchain
v0.3

##Requisites
    - This script works with postgres and kapu_db, configured with kapu user
    - You need to have sudo privileges

##Installation
Execute the following commands
```
cd ~/
git clone https://github.com/kapucoin/kapu-snapshot.git
cd kapu-snapshot
sudo updatedb
bash kapu-snapshot.sh help
```
##Available commands

  - create
- restore
- log
- schedule
	- hourly
	- daily
	- weekly
	- monthly
    
###create
Command _create_ is for create new snapshot, example of usage:<br>
`bash kapu-snapshot.sh create`<br>
Automaticly will create a snapshot file in new folder called snapshot/.<br>
Don't require to stop you node app.js instance.<br>
Example of output:<br>
```
   + Creating snapshot                                
  -------------------------------------------------- 
  OK snapshot created successfully at block  91005 ( 154 MB).
```
Also will create a line in the log, there you can see your snapshot at what block height was created.<br>

###restore
Command _restore_ is for restore the last snapshot found it in snapshot/ folder.<br>
Example of usage:<br>
`bash kapu-snapshot.sh restore`<br>
<br>
Automaticly will pick the last snapshot file in snapshot/ folder to restore the ark.<br>
If you want to restore a specific file please (for this version) delete or move the other files in snapshot/ folder.<br>
You can use the _log_ command to better pick up your restore file.<br>
<br>

Schedule

Schedule snapshot creation periodically, with the available parameters:
```
- hourly
- daily
- weekly
- monthly
Example: bash kapu-snapshot.sh schedule daily 
```




###log
Display all the snapshots created. <br>
Example of usage:<br>
`bash kapu-snapshot.sh log`<br>
<br>
Example of output:<br>
```
   + Snapshot Log                                                                  
  --------------------------------------------------                               
  09-03-2017 - 20:59:06 -- Snapshot created successfully at block  91005 ( 154 MB)  
  09-03-2017 - 21:36:07 -- Snapshot created successfully at block  91019 ( 154 MB)  
  --------------------------------------------------END                            
```
-------------------------------------------------------------

