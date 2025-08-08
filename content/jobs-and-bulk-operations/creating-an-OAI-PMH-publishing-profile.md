---
section_id: Jobs & Bulk Operations
nav_order: 7
title: Creating an OAI-PMH publishing profile
topics:
---
## Creating an OAI-PMH publishing profile

### Relevant Esploro Documentation:  
  
Step 2:  
[Setting Up OAI Integration - Ex Libris Knowledge Center](https://knowledge.exlibrisgroup.com/Alma/Product_Documentation/010Alma_Online_Help_(English)/090Integrations_with_External_Systems/030Resource_Management/060Setting_Up_OAI_Integration)  
Step 3:  
[Esploro Publishing to OAI and Exporting to FTP - Ex Libris Knowledge Center](https://knowledge.exlibrisgroup.com/Esploro/Product_Documentation/Esploro_Online_Help_(English)/Esploro_Publishing/Esploro_Publishing_to_OAI_and_Exporting_to_FTP)  
Step 4:  
[Examples of OAI Syntax - Ex Libris Developer Network](https://developers.exlibrisgroup.com/blog/examples-of-oai-syntax/)  

---

This process can be done in 4 main steps:  
1.	Create a set  
2.	Configure the OAI Definition  
3.	Create a publication profile
4.	Test Access  

### Step 1: Create a set  
You will need to make a set to be published.  
Admin>Manage Sets  
You can select a set that already exists, or make one from scratch.  

### Step 2: Configure the OAI Definition  
Configuration>General>External Systems> Integration Profiles  
  
- Select OAI_DEFINITION (Note: You can only have one OAI profile for the whole institution, so you only need to edit the existing one.)  
  - The default check box has no functionality for this profile.  
  - Edit the description to include the compatibility / functionality you are adding. (In my case, Esploro OAI-PMH harvesting)  
  - Go to the Actions tab  
  - Click 'Metadata Prefixes'  
  - Enable your desired metadata format. (For Verso purposes, ensure Esploro is enabled)  
  - Save  
  - Click 'Allowed Ips'  
  - If 0.0.0.0-255.255.255.255 is enabled, all IPs will have access. If you need to restrict an IP, you will need to add lines that have the full range of IPs above and below the one that you blocked.  
  - Save  
- On the actions tab, save / copy the Repository Base URL. You will need it later.

### Step 3: Create a Publishing Profile  
Leave configuration and go to Esploro home.  
  
Repository>Publishing>Manage Publishing Profiles  
  
- Click Add Profile –> Research General Profile  
  - Create a name for the publication: FORMAT_NAME_OAI -> ESPLORO_EXTENSION_OAI  
  - Optionally add a descsription.
  - Status: Active
  - Edit Scheduling -> weekly
  - Set name: select the set that you made in step 1  
  - Ouput format: select your desired format, for Verso this should be esploro  
  - Publishing protocol: OAI
  - Set Spec and Set Name can be any string you want.
    - Set Spec: This is the string you will need to enter in the URL later to access the set.
    - Set Name: This is the name that will appear in the OAI window.
    - Examples: SetSpecExtensionPublications SetNameExtensionPublications  
  - Save the publication profile.  
- Return to Repository>Publishing>Manage Publishing Profiles  
- Click your new profile.
- Click ‘Run’. This will start a publication job. Wait for the job to finish (will take some time, refresh the monitor jobs page to track progress. Admin>Monitor Jobs).

### Step 4: Test Access  
Ensure that you have the URL from step 2  
Ensure that you have run the publication job on your publication profile as seen in step 3  
Paste the saved URL into a new browser window and follow the step 4 documentation (above) to properly format your URL  
Remember to use the URL you saved earlier. Ensure that you are editing the snippets from the documentation.  
- Example: replace **&metadataPrefix=marc21** with **&metadataPrefix=esploro**
  
I recommend using the following URLS (edit accordingly):  
**https://alliance-uidaho.alma.exlibrisgroup.com/view/oai/01ALLIANCE_UID/request?verb=ListSets**  
to see if your set is appearing, followed by  
**alliance-uidaho.alma.exlibrisgroup.com/view/oai/01ALLIANCE_UID/request?verb=ListRecords&metadataPrefix=esploro&set=YOURSETNAMEHERE**  
to view the metadata of your set. 
