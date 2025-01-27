# Secure Backup and Attack Recovery

<h2> Scenario 1 </h2>
In this hands-on lab, I will assume the role of a junior system administrator at Rezifp Pharma Inc., a leading pharmaceutical company specializing in oncology, immunology, and vaccine research. In response to recent malware attacks that have threatened the integrity of critical data, the company has decided to implement a more robust backup strategy. My task is to create daily full backups of the core files associated with the E-Prescription Treatment database, a crucial system for multiple departments across the organization.<br />

To safeguard this essential data, I will:<br />

-  Adhere to the department’s established naming conventions to create a consistent name for the backup archive.<br />
-  Perform a full daily backup of the files and directories located in ~/Documents/epscript, ensuring all critical data is securely archived.<br />
-  Document detailed file attributes, including permissions, ownership, size, and timestamps, for each file included in the archive.<br />
-  Verify the integrity of the archive after it’s created to ensure that no errors have occurred during the backup process.<br />
-  Generate a log file containing the output of the tar command, which will be reviewed by the SysOps team to assess file structure, permissions, and any potential errors.<br />

<h2> Scenario 2 </h2>
Following a recent malware attack, the E-Prescription Treatment database was restored using a backup. However, the recovery effort encountered a setback when it was discovered that the wrong backup had been used, leaving critical patient files missing. This error has forced the system offline once again, creating an urgent need to locate and restore the missing files.<br />

After consulting with a pharmacy technician, I have received a list of affected patients whose files must be recovered. My mission is to:<br />

-  Inspect the archive contents to determine if the missing patient files are included.<br />
-  Create a dedicated directory to safely restore the identified patient files for further review.<br />
-  Extract only the specific patient files to the new directory, ensuring they are available for verification by the pharmacy technician.<br />

<h2> Scenario 3 </h2>
The company has recently implemented a new and robust backup policy to enhance data resilience. My mission is to validate the effectiveness of the backup and restoration process through two critical tests: restoring lost patient files and performing an incremental backup after simulating changes to the system.<br />

To achieve this, I will:<br />

-  Test the restoration process:<br />

  -  Start by listing and verifying the current files in the testenvir directory to establish a baseline.<br />
  -  Create a level 0 (full) backup of the entire testenvir directory, ensuring all existing files are captured.<br />
  -  Simulate a cyberattack by deleting the patient directory, which contains critical files, from the parent folder.<br />
  -  Confirm the patient directory is missing to simulate the impact of the attack.<br />
  -  Restore the missing directory from the full backup and verify that all files are successfully recovered.<br />
-  Test incremental backups:<br />

  -  Introduce changes by creating three new files within the restored patient directory.<br />
  -  Perform an incremental backup to capture only the new changes made to the directory.<br />
  -  Verify that the newly added files are included in the incremental backup, confirming the backup system is functioning as intended.<br />


<h2> Step 1: Creating the Backup Archive </h2>
<b>Purpose: </b> To ensure the critical data of the E-Prescription Treatment database is securely archived and readily available for restoration in case of data loss or malware attacks. <br />
<b>My Action: </b> Following the standard naming convention of Rezifp Pharma Inc., I will create a daily backup of the files located in the ~/Documents/epscript directory. Using the <b>tar cvvWf</b> command, I will compress and archive these files into a single tarball for secure storage. I will then use the <b>ls</b> command to confirm that the backup has been created. <br />
<p align="center">
<img src="https://i.imgur.com/vI0TydR.png" height="80%" width="80%" alt="Creating backup"/>

<h2> Step 2: Previewing the Backup File </h2>
<b>Purpose: </b> To confirm the contents of the backup archive and ensure all critical files and directories have been included before proceeding with verification and storage. <br />
<b>My Action: </b> After creating the backup, I will use the <b>less</b> command to preview the files and directories contained within the archive. This step ensures the backup accurately captures the intended data. <br />
<p align="center">
<img src="https://i.imgur.com/jxUdxyg.png" height="80%" width="80%" alt="Previewing file"/>
<img src="https://i.imgur.com/vTIAmv9.png" height="80%" width="80%" alt="Previewing file"/>

<h2> Step 3: Listing Archives in the Backup Directory </h2>
<b>Purpose: </b> To identify and locate the appropriate backup archive that may contain the missing patient files. This step ensures I work with the correct archive during the restoration process. <br />
<b>My Action: </b>  I will use the <b>ls</b> command to display all available backup archives stored in the backup directory. <br />
<p align="center">
<img src="https://i.imgur.com/ZTLKqx0.png" height="80%" width="80%" alt="Listing archives"/>

<h2> Step 4: Restoring the Backup </h2>
<b>Purpose: </b> To recover the missing patient files from the identified backup archive, ensuring they are accessible for review and verification by the pharmacy technician. <br />
<b>My Action: </b> Once I’ve identified the correct backup archive containing the missing files, I will extract entire backup archive using the <b>tar -xvf</b> command and focus specifically on the patients files that are missing. <br />
<p align="center">
<img src="https://i.imgur.com/lGfSL37.png" height="80%" width="80%" alt="Restoring backup"/>
<img src="https://i.imgur.com/gARA2Y9.png" height="80%" width="80%" alt="Restoring backup"/>

<h2> Step 5: Listing Files from the Restored Directory </h2>
<b>Purpose: </b> To verify that the extracted files from the backup archive have been successfully restored to the designated directory and to confirm their availability for review. <br />
<b>My Action: </b> After restoring the files, I will use the <b>ls -l</b> command to list all files and directories within the restored directory. This will help ensure that the missing patient files are present and accounted for. <br />
<p align="center">
<img src="https://i.imgur.com/gmMsG5T.png" height="80%" width="80%" alt="Listing files from backup"/>

<h2> Step 6: Listing Folders to Be Backed Up in the testenvir Directory </h2>
<b>Purpose: </b> To establish a clear understanding of the existing directory structure and verify the files and folders that need to be included in the backup process. <br />
<b>My Action: </b> I will use the <b>ls -l</b> command to list all the files and subdirectories within the testenvir directory. This ensures that I capture the current state of the directory before performing the backup. <br />
<p align="center">
<img src="https://i.imgur.com/RzOVrRN.png" height="80%" width="80%" alt="List"/>


<h2> Step 7: Backing Up Directories with Incremental Backup </h2>
<b>Purpose: </b> To create a backup of the testenvir directory using an incremental approach, ensuring that only new or modified files are captured after the initial full backup. This approach optimizes storage and reduces redundancy. <br />
<b>My Action: </b> I will perform a level 0 (full) backup to capture the entire testenvir directory. This serves as the baseline for all subsequent incremental backups. <br />
<p align="center">
<img src="https://i.imgur.com/SqGTmWv.png" height="80%" width="80%" alt="Incremental Backup"/>
<img src="https://i.imgur.com/xPbn2rP.png" height="80%" width="80%" alt="Incremental Backup"/>
<img src="https://i.imgur.com/bxVgN82.png" height="80%" width="80%" alt="Incremental Backup"/>

<h2> Step 8: Verifying Backup Status </h2>
<b>Purpose: </b> To confirm that the backup process was successful and validate the integrity of both the full and incremental backups. This step ensures that all intended files have been accurately captured and can be restored when needed. <br />
<b>My Action: </b> Verify the contents of the full backup archive by using the <b>tar -tvf</b> command piped through <b>less</b> to preview the files. <br />
<p align="center">
<img src="https://i.imgur.com/ihBK17u.png" height="80%" width="80%" alt="Verifying status"/>
<img src="https://i.imgur.com/icCrSC4.png" height="80%" width="80%" alt="Verifying status"/>

<h2> Step 9: Simulating Cyberattack by Removing the Patient Directory from testenvir Directory
Purpose </h2>
<b>Purpose: </b> o simulate a data loss scenario, such as a cyberattack or accidental deletion, by removing the patient directory from the testenvir directory. This test validates the recovery process and ensures that the backup system can effectively restore lost data. <br />
<b>My Action: </b> I will confirm the presence of the patient directory in the testenvir directory using the <b>ls</b> command. After confirmation, I will delete the patient directory and all associated files using the <b>rm -r</b> to simulate the loss of data during an attack. Finally, I will verify that the patient directory is missing using the <b>ls</b> command. <br />
<p align="center">
<img src="https://i.imgur.com/F2rR5ih.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/cHM7X4z.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/SELnVeq.png" height="80%" width="80%" alt=""/>

<h2> Step 10: Restoring the Patient Directory from the Backup </h2>
<b>Purpose: </b> To recover the deleted patient directory from the most recent backup. This step ensures that lost data can be restored seamlessly in the event of a real-world cyberattack or accidental deletion. <br />
<b>My Action: </b> I will navigate to the testenvir parent directory to ensure the backup restoration occurs in the correct location. After that, I restore the patient directory from the full backup archive. Then finally, I verify that the patient directory has been restored <br />
<p align="center">
<img src="https://i.imgur.com/NLqmEwv.png" height="80%" width="80%" alt="Restoring backup directory"/>
<img src="https://i.imgur.com/0ZPGUV0.png" height="80%" width="80%" alt="Restoring backup directory"/>
<img src="https://i.imgur.com/bhVw9jG.png" height="80%" width="80%" alt="Restoring backup directory"/>

<h2> Step 11: Testing Incremental Backup by Creating New Files </h2>
<b>Purpose: </b> To simulate changes to the system by adding new files to the patient directory. This test ensures that the incremental backup process captures these changes without duplicating unchanged data. <br />
<b>My Action: </b> I create three new files using the <b>touch</b> command to simulate updates or additions to the directory. I list the contents of the patient directory to verify the new files have been created. <br />
<p align="center">
<img src="https://i.imgur.com/eBhvMTK.png" height="80%" width="80%" alt="Creating new files"/>

<h2> Step 12: Backing Up New Files with Incremental Backup </h2>
<b>Purpose: </b> To test the incremental backup process by capturing only the newly created files within the patient directory. This ensures the backup system is efficient and can record updates without duplicating unchanged data. <br />
<b>My Action: </b> I run the incremental backup targeting the changes in the testenvir/patient directory to backup the new files added. <br />
<p align="center">
<img src="https://i.imgur.com/NgKrKbY.png" height="80%" width="80%" alt="Backing up new files"/>
<img src="https://i.imgur.com/FXUkUrS.png" height="80%" width="80%" alt="Backing up new files"/>
  
<h2> Step :  </h2>
<b>Purpose: </b>  <br />
<b>My Action: </b>  <br />
<p align="center">

<h2> Step :  </h2>
<b>Purpose: </b>  <br />
<b>My Action: </b>  <br />
<p align="center">

<h2> Step :  </h2>
<b>Purpose: </b>  <br />
<b>My Action: </b>  <br />
<p align="center">
