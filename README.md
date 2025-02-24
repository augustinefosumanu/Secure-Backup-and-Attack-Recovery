# Rezifp Pharma Malware Recovery and Backup Lab
(Ficticious Organization)

<h2> Lab </h2>
This lab focused on strengthening data resilience and securing backup processes at Rezifp Pharma Inc. in response to recent malware attacks. I implemented robust backup strategies, ensured data integrity, and tested system recovery against potential threats.<br />

<h2>Technical Skills</h2>
✅ Full & Incremental Backup Management<br />
✅ Data Restoration & Integrity Validation<br />
✅ Backup Security & Malware Resilience<br />
✅ Archive Inspection & Recovery<br />
✅ Disaster Recovery Planning<br />
✅ Cyberattack Simulation & System Testing<br />


<h2>  Creating the Backup Archive </h2>
Following the standard naming convention of Rezifp Pharma Inc., I created a daily backup of the files located in the ~/Documents/epscript directory. Using the tar cvvWf command, I compressed and archived these files into a single tarball for secure storage. Afterward, I used the ls command to confirm that the backup had been created successfully. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/vI0TydR.png" height="80%" width="90%" alt="Creating backup"/>

<h2>  Previewing the Backup File </h2>
After creating the backup, I used the less command to preview the files and directories contained within the archive. This step ensured that the backup accurately captured the intended data. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/jxUdxyg.png" height="80%" width="90%" alt="Previewing file"/>
  <br />
  <br />
<img src="https://i.imgur.com/vTIAmv9.png" height="80%" width="90%" alt="Previewing file"/>

<h2>  Listing Archives in the Backup Directory </h2>
I used the ls command to display all available backup archives stored in the backup directory. This helped me confirm the list of stored backups and ensure everything was organized correctly. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/ZTLKqx0.png" height="80%" width="90%" alt="Listing archives"/>

<h2>  Restoring the Backup </h2>
I identified the correct backup archive containing the missing files and then used the tar -xvf command to extract the entire backup archive. Afterward, I focused specifically on the patient files that were missing to restore them accurately.
 <br />
<br />
<p align="center">
<img src="https://i.imgur.com/lGfSL37.png" height="80%" width="90%" alt="Restoring backup"/>
  <br />
  <br />
<img src="https://i.imgur.com/gARA2Y9.png" height="80%" width="90%" alt="Restoring backup"/>

<h2>  Listing Files from the Restored Directory </h2>
After restoring the files, I used the ls -l command to list all files and directories within the restored directory. This allowed me to confirm that the missing patient files were successfully restored and accounted for. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/gmMsG5T.png" height="80%" width="90%" alt="Listing files from backup"/>

<h2>  Listing Folders to Be Backed Up in the testenvir Directory </h2>
I used the ls -l command to list all the files and subdirectories within the testenvir directory. This allowed me to capture the current state of the directory before performing the backup. <br />
  <br />
<p align="center">
<img src="https://i.imgur.com/RzOVrRN.png" height="80%" width="90%" alt="List"/>


<h2>  Backing Up Directories with Incremental Backup </h2>
I performed a level 0 (full) backup to capture the entire testenvir directory. This established the baseline for all subsequent incremental backups. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/SqGTmWv.png" height="80%" width="90%" alt="Incremental Backup"/>
  <br />
  <br />
<img src="https://i.imgur.com/xPbn2rP.png" height="80%" width="90%" alt="Incremental Backup"/>
  <br />
  <br />
<img src="https://i.imgur.com/bxVgN82.png" height="80%" width="90%" alt="Incremental Backup"/>

<h2>  Verifying Backup Status </h2>
I verified the contents of the full backup archive by using the tar -tvf command, piping the output through less to preview the files. This allowed me to confirm that the backup was correctly created and captured all necessary files. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/ihBK17u.png" height="80%" width="90%" alt="Verifying status"/>
  <br />
  <br />
<img src="https://i.imgur.com/icCrSC4.png" height="80%" width="90%" alt="Verifying status"/>

<h2>  Simulating Cyberattack by Removing the Patient Directory from testenvir Directory </h2>
I confirmed the presence of the patient directory in the testenvir directory using the ls command. After confirming its presence, I deleted the patient directory and all associated files using the rm -r command to simulate the loss of data during an attack. Finally, I verified that the patient directory was missing by running the ls command again. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/F2rR5ih.png" height="80%" width="90%" alt=""/>
  <br />
  <br />
<img src="https://i.imgur.com/cHM7X4z.png" height="80%" width="90%" alt=""/>
  <br />
  <br />
<img src="https://i.imgur.com/SELnVeq.png" height="80%" width="90%" alt=""/>

<h2>  Restoring the Patient Directory from the Backup </h2>
I navigated to the testenvir parent directory to ensure the backup restoration occurred in the correct location. After that, I restored the patient directory from the full backup archive using the appropriate command. Finally, I verified that the patient directory had been successfully restored by running the ls command. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/NLqmEwv.png" height="80%" width="90%" alt="Restoring backup directory"/>
  <br />
  <br />
<img src="https://i.imgur.com/0ZPGUV0.png" height="80%" width="90%" alt="Restoring backup directory"/>
  <br />
  <br />
<img src="https://i.imgur.com/bhVw9jG.png" height="80%" width="90%" alt="Restoring backup directory"/>

<h2>  Testing Incremental Backup by Creating New Files </h2>
I created three new files using the <b>touch</b> command to simulate updates or additions to the directory. Afterward, I listed the contents of the patient directory using <b>ls</b> to verify that the new files had been successfully created. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/eBhvMTK.png" height="80%" width="90%" alt="Creating new files"/>

<h2>  Backing Up New Files with Incremental Backup </h2>
I ran the incremental backup targeting the changes in the <b>testenvir/patient</b> directory to back up the new files that were added. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/NgKrKbY.png" height="80%" width="90%" alt="Backing up new files"/>
  <br />
  <br />
<img src="https://i.imgur.com/FXUkUrS.png" height="80%" width="90%" alt="Backing up new files"/>
