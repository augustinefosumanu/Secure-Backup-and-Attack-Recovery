# Rezifp Pharma Backup Strategy & Security Testing Lab
(Ficticious Organization)

<h2> Lab </h2>
In this lab, I focused on enhancing data resilience and securing backup processes at Rezifp Pharma Inc. following recent malware attacks.<br />

-  <b>Full & Incremental Backup Implementation</b>: Created daily full backups of critical data and validated backup integrity. Performed incremental backups to capture system changes.<br />
-  <b>Data Restoration</b>: Recovered missing patient files by inspecting and extracting data from backup archives, ensuring accurate restoration.<br />
-  <b>Backup System Testing</b>: Simulated cyberattacks to verify backup restoration and validate system functionality.<br />
-  <b>Penetration Testing</b>: Used wildpwn.py to identify potential privilege escalation vulnerabilities in the backup system and proposed mitigation strategies.<br />


<h2> Step 1: Creating the Backup Archive </h2>
Following the standard naming convention of Rezifp Pharma Inc., I created a daily backup of the files located in the ~/Documents/epscript directory. Using the tar cvvWf command, I compressed and archived these files into a single tarball for secure storage. Afterward, I used the ls command to confirm that the backup had been created successfully. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/vI0TydR.png" height="80%" width="90%" alt="Creating backup"/>

<h2> Step 2: Previewing the Backup File </h2>
After creating the backup, I used the less command to preview the files and directories contained within the archive. This step ensured that the backup accurately captured the intended data. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/jxUdxyg.png" height="80%" width="90%" alt="Previewing file"/>
  <br />
  <br />
<img src="https://i.imgur.com/vTIAmv9.png" height="80%" width="90%" alt="Previewing file"/>

<h2> Step 3: Listing Archives in the Backup Directory </h2>
I used the ls command to display all available backup archives stored in the backup directory. This helped me confirm the list of stored backups and ensure everything was organized correctly. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/ZTLKqx0.png" height="80%" width="90%" alt="Listing archives"/>

<h2> Step 4: Restoring the Backup </h2>
I identified the correct backup archive containing the missing files and then used the tar -xvf command to extract the entire backup archive. Afterward, I focused specifically on the patient files that were missing to restore them accurately.
 <br />
<br />
<p align="center">
<img src="https://i.imgur.com/lGfSL37.png" height="80%" width="90%" alt="Restoring backup"/>
  <br />
  <br />
<img src="https://i.imgur.com/gARA2Y9.png" height="80%" width="90%" alt="Restoring backup"/>

<h2> Step 5: Listing Files from the Restored Directory </h2>
After restoring the files, I used the ls -l command to list all files and directories within the restored directory. This allowed me to confirm that the missing patient files were successfully restored and accounted for. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/gmMsG5T.png" height="80%" width="90%" alt="Listing files from backup"/>

<h2> Step 6: Listing Folders to Be Backed Up in the testenvir Directory </h2>
I used the ls -l command to list all the files and subdirectories within the testenvir directory. This allowed me to capture the current state of the directory before performing the backup. <br />
  <br />
<p align="center">
<img src="https://i.imgur.com/RzOVrRN.png" height="80%" width="90%" alt="List"/>


<h2> Step 7: Backing Up Directories with Incremental Backup </h2>
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

<h2> Step 8: Verifying Backup Status </h2>
I verified the contents of the full backup archive by using the tar -tvf command, piping the output through less to preview the files. This allowed me to confirm that the backup was correctly created and captured all necessary files. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/ihBK17u.png" height="80%" width="90%" alt="Verifying status"/>
  <br />
  <br />
<img src="https://i.imgur.com/icCrSC4.png" height="80%" width="90%" alt="Verifying status"/>

<h2> Step 9: Simulating Cyberattack by Removing the Patient Directory from testenvir Directory </h2>
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

<h2> Step 10: Restoring the Patient Directory from the Backup </h2>
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

<h2> Step 11: Testing Incremental Backup by Creating New Files </h2>
I created three new files using the <b>touch</b> command to simulate updates or additions to the directory. Afterward, I listed the contents of the patient directory using <b>ls</b> to verify that the new files had been successfully created. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/eBhvMTK.png" height="80%" width="90%" alt="Creating new files"/>

<h2> Step 12: Backing Up New Files with Incremental Backup </h2>
I ran the incremental backup targeting the changes in the <b>testenvir/patient</b> directory to back up the new files that were added. <br />
<br />
<p align="center">
<img src="https://i.imgur.com/NgKrKbY.png" height="80%" width="90%" alt="Backing up new files"/>
  <br />
  <br />
<img src="https://i.imgur.com/FXUkUrS.png" height="80%" width="90%" alt="Backing up new files"/>
  
<h2> Step 13:   </h2>
  <br />
<p align="center">

<h2> Step :  </h2>
<br />
<p align="center">

<h2> Step :  </h2>
<br />
<p align="center">

<img src="https://i.imgur.com/eJ87uFK.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/2Ci7lsF.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/CMdWCll.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/x9qEli5.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/HJF9Kbs.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/w4VM29Z.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/e9K4NCv.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/0I2Ypo4.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/j2NckGp.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/KsmXzLT.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/SO2t8YO.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/LxxQBa8.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/x71KrsQ.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/EatcSwi.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/xbmB9Ee.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/JInSAyE.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/.png" height="80%" width="90%" alt=""/>
<img src="https://i.imgur.com/.png" height="80%" width="90%" alt=""/>


