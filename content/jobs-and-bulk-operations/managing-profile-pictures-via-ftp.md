---
section: Jobs & Bulk Operations
nav_order: 3
title: Managing Profile Pictures via FTP
topics:
---
## Relevant Ex Libris Documentation
- [Managing Researcher Profiles](https://knowledge.exlibrisgroup.com/Esploro/Product_Documentation/Esploro_Online_Help_(English)/250_Working_with_Esploro_Portal_and_Profiles/430_Managing_Profiles) - Quick note on image recommendations

## How to Add and Sync Profile Pictures  

Seth Thompson 1/7/2025

Along with Esploro, you will need access to VS Code and WinSCP  

- Find and save the researcher images (e.g. U of I faculty page photo)  
- Save the image in last_first.jpg format
  
All the images must be turned into links hosted on the U of I server 
- I sent the images to Devin Becker to complete this step, as I do not have the required permissions to do so

The links should be returned in a spreadsheet like so:  
![image](https://github.com/user-attachments/assets/3095fb6c-64aa-4b66-9a4d-2b0ed0f486eb)


**Accessing Synchronization:**  
1.	Open Esploro.   
2.	Click ‘Configuration’ in bottom left corner under the gear icon.  
3.	Click ‘General’ located in blue ribbon  
4.	In the expanded menu, under ‘External Systems,’ click ‘Integration Profiles’  
5.	Find and click ‘Esploro Researchers’ on the Integration Profile list  
6.	Click on the ‘Actions’ tab
  
![image](https://github.com/user-attachments/assets/ec7f0afd-d74c-49b1-9c7e-a5f6f3d40354)

Within the ‘Import’ section, click the ‘Create Sample File’ button.  
Type the name of a researcher from your list of links.  
- Affiliated faculty and staff should auto-populate the drop-down menu as you type
   
Select their name and click 'Create.' This will send and XML file named UserDetails to your downloads folder  
  
Continue creating XML UserDetails files for each researcher on your list. Do not worry about renaming each file.  
  
Using VS Code, open every UserDetails file.  

Open the first UserDetails tab. You should find the researcher name in the first few tags.  

- Scroll until you find the &lt;researcher&gt; tag  
- Inside &lt;researcher&gt;, look for &lt;photo_url&gt;
- If &lt;photo_url&gt; is present, you can simply paste in the new JPG link. Ensure the tag is in &lt;photo_url&gt;your_link&lt;/photo_url&gt; format
- If &lt;photo_url&gt; is **NOT** present:  
  - **AFTER** &lt;researcher_title&gt; and **BEFORE** &lt;profile_identifier_url&gt; paste in the following: &lt;photo_url&gt;your_link&lt;/photo_url&gt;
 
![image](https://github.com/user-attachments/assets/a0037c03-c4da-4eb0-98aa-e45af25d8903)  


You may notice some researcher files have the tag &lt;profile_image_url&gt;. This tag is created when a researcher personally uploads a profile picture to their page.  
**DO NOT** paste your link into this tag.  
Like before, paste the link inside &lt;photo_url&gt; (The tag should be **AFTER** &lt;profile_image_url&gt; and **BEFORE** &lt;profile_identifier_url&gt;).  
In this case, your link will be a backup for the image that they personally uploaded.  

Repeat the link pasting process for every UserDetails file.   
  
Double check every file to ensure the name in the researcher file matches the name on the link you pasted in.

Click File -> Save All
  - This will overwrite all the UserDetails files in your Downloads folder so that they all have their new links pasted in.  
  - There is no need to individually rename every UserDetails file.  
  
Select every UserDetails file, right click, and compress to ZIP.

Log in to WinSCP.  
1.	In the left-hand pane, navigate the directory to your downloads folder.  
2.	In the right-hand pane, click into the production folder twice. Production -> Production ->  
3.	Ensure that the second production file has nothing in it.  
4.	Drag the ZIP you created from your downloads folder to the production folder.  
  
![image](https://github.com/user-attachments/assets/d4ec914a-e494-48b0-bd79-748698b9c8d4)  
  
Go back to the Esploro Integration Profiles page that you were creating sample files from.  
Scroll down to Synchronize  
- •	Match the fields to the image below. Ensure that ‘Selected Researcher Fields’ in selected and that only Photo URLs in selected from the drop-down list.

![image](https://github.com/user-attachments/assets/4e6846bd-0b10-4d63-8ac2-38b282cde39e)  

Click Run. This will run a job.

## Job Results Summary and Troubleshooting 
  
![image](https://github.com/user-attachments/assets/6ad4b61b-ba8f-43b4-a757-2da2fef19ce7)  
  
You will receive a job summary email similar to the one pictured above.  

Error Handling:  
  
The errors typically come from formatting errors or invalid entries the user made to their profile.  
If a USER gets rejected, the system did not recognize them as an existing user in esploro.  
- The user must exist in Esploro for us to pull their file in the first place, so what this usually means is that their profile has an inactive identifier attached to it. In this case, the user had two Barcode identifiers, one of them being defunct.
  
If a RESEARCHER gets rejected, there is likely a formatting issue, invalid data, profile issue, XML typo, etc. The three rejected researchers in this batch added education affiliations to their profile but did not populate the required 
fields, causing Esploro to throw an error when encountering their accounts  
  
To see the cause of the rejection:  
1.	Go to Esploro home page  
2.	Click on Admin  
3.	In the expanded menu click Monitor Jobs  
4.	Click the History tab  
5.	Your Job will have the title “Users SYNCHRONIZE using Esploro Researchers”, the number of records you processed, your userID, etc.  
6.	Click the button with three dots on the right side of your job’s row  
7.	Click ‘Events’  
8.	Scroll through the list of events and find the User that failed / the reason why it failed  
9.	You can now check their Esploro researcher page or their XML file for the source of the rejection.


To synchronize rejected users:   
- Correct the invalid data
- Repeat the sample file pulling, link pasting, WinSCP process for the users that were originally rejected.  
  - You do not need to resync 60 users if only 3 threw errors. Just redo those 3.  
  - Yes, you must repeat this entire process for any users that got rejected, **AFTER** correcting the error that caused the rejection  
  - Even after correcting errors, do not resue the UserDetails file that got rejected. That file will still have the errors in it. Pull a new file.


