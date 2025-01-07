---
section_id: Researcher Profiles
nav_order: 3
title: Connecting Profiles to ORCiD
topics:
---
## Relevant Ex Libris Documentation
- [CSV Researcher Loader Cloud App](https://knowledge.exlibrisgroup.com/Esploro/Product_Documentation/Esploro_Online_Help_(English)/Ongoing_Maintenance_and_Administration/Configuring_Cloud_Apps/CSV_Researcher_Loader_Cloud_App)

## Connecting Profiles to ORCID
Seth Thompson 1/7/2025
You can add ORCIDs to researcher profiles in a bulk update or individually.

### To add and individual ORCID:
Click the researchers tab in the side bar. Click on Manage Researchers.  
Search for your researcher in the top search bar.  
After searching, you can navigate to the Affiliated tab to narrow the results further.  
Click on the researchers name. Once you are on their Details page, go to the Identifiers tab.  
Click ‘Add Identifier’  
Check ‘Add as an external’  
Select ORCID from the drop-down menu  
Enter the ORCID ID in the ‘Value’ field  
Click Add and Close  
Hit save at the top of the researcher page.  

![image](https://github.com/user-attachments/assets/f4f3478b-b6b4-449c-9b5e-94399b53927a)



### Bulk Update
You will need to obtain a CSV that contains researcher primary IDs, the constant 'ORCID,' and the ORCIDs themselves  
To bulk add ORCIDs, you will need to run an App.  
The App center can be found by clicking the square icon on the top right of the home page.  

![image](https://github.com/user-attachments/assets/8f7d1a1d-9e1a-4a7e-bb1f-f5a906a7eaad)

After clicking the cloud app center icon, look in the Activated Apps tab.  
Click on the CSV Researcher Loader app.  
Click the 3 horizontal dots just to the right of the words ‘CSV Researcher Loader’  
Click the gear Icon  
Click the ‘Select a profile’ drop-down menu and select ORCID.  
If ORCID is not an option, you can create your own profile by clicking the blue plus symbol.  
Make sure the ‘profile type’ is set to Update  
In the field mapping section, we will set up our headers to match to our CV of researchers and their ORCIDs.  
We only need 3 headers. If you need to add more headers, use the black plus symbol at the bottom of the field mapping section.  
Our first header should be ‘Primary_ID’ with a field name of General – Primary ID  
Header 2 should be ‘Record_Type’ with a field name of Identifiers – ID Type  
Header 3 should be ‘ORCID_ID’ with a field name of Identifiers – Value  
The middle default column can be left blank.  
The field map will now match a CV that contains a column of primary IDs, a column containing the constant type ‘ORCID,’ and a column with the ORCIDs themselves.   
Note that the headers in the Esploro app and the headers in your CSV must be identical  

![image](https://github.com/user-attachments/assets/bbc761af-2c35-43c4-aff2-e185e7d64fdf)

In the app window, click the ‘< Home’ button.  
Ensure that the ORCID profile is still selected in the drop-down menu. Drag your CSV file into the designated field.  
Click Load Researchers and confirm that you want the job to run.  
ORCIDs should now be visible in researcher pages.  





