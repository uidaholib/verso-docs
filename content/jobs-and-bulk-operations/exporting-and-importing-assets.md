---
section: Jobs & Bulk Operations
nav_order: 2
title: Exporting and Importing Assets
topics:
---
## Relevant Ex Libris Documentation
- [Working with Research Assets](https://knowledge.exlibrisgroup.com/Esploro/Product_Documentation/Esploro_Online_Help_(English)/Working_with_the_Esploro_Research_Hub/010_Working_with_Research_Assets#Esploro_Import_File_Formats) READ THIS

## Bulk Asset Export and Import  

Seth Thompson 1/7/2025

### Exporting  
  
The assets you want to export must be in a set  
  
Click Admin -> Run a job  
  
Select the ‘Research assets CSV export’ job. Click next  
  
Select the asset set you want to export
  
If you want to export all metadata, check Full Export.
  
You can also check selective export, then use the list below to select the specific metadata categories that you want.
  
Click next, then submit. This will run a job. Once finished, go to Admin -> monitor jobs -> history. Find your export job, click into it, and you should find a download link for your CSV.
  
### Importing  
  
Importing is a varied and tedious enough process that you should view the full Ex Libris documentation (above) to make sure you do it properly. Imports are made by uploading a CSV that is built with a very specific set of rules. You will need a script to build your CSV. I will use this page to highlight the most important points and nuances I have found from doing it several times:  

![image](https://github.com/user-attachments/assets/9062ca22-7077-49d7-8a0d-57da1d7af079)  

Basic Setup:
1. The A column must be blank in cell A1, and contains the metadata type indicators at the beginning of each row (will explain later). Every other column will contain a metadata category header in the first row.  
2. B1 contains the ‘group_id’. The group ID is not metadata and does not alter your assets in any way. All rows associated with the same asset will contain the same group_id value. If you have 1 creator row and 3 file rows for one asset, they must all have the same value in their group_id column (see above photo for example). Two different assets cannot have the same group_id. You can use whatever convention you want to assign group_ids, I typically just used integers starting from 0.  
3. You must build the A and B columns with those rules in mind and in that order. All other column headers can be arranged in any order.

The photo above shows all the metadata ‘types’ at the start of each row: ASSET, CREATOR, FILE, LINK, etc.  
  
Column headers are typically in this format: TYPE_CATEGORY  
  - FILE_FILEURL, ASSET_LANG, CREATOR_FAMNAME, ASSET_ABSTRACT, etc.
  
The cell you place each data point into must be an intersection of matching types from the row and column headers.  
  
![image](https://github.com/user-attachments/assets/05554640-9bfd-47a2-b431-da47f09a62b3)  
  
Each asset will only have one ASSET row  
  
For each creator, file, or link, create a new row of that type.   
  
If your asset has three authors, two links, and a file, your rows will look like so:  
  ASSET  
  CREATOR  
  CREATOR  
  CREATOR  
  LINK  
  LINK  
  FILE  

![image](https://github.com/user-attachments/assets/d6f1e7d0-a7a9-4f56-a17e-9d253c36b306)  
  
Above is a section of an import frame I made for Extension. Use this to visualize how each rule applies to the construction of the frame:  
1.  A column – Blank in A1. Contains metadata type headers at start of each row.  
2.  B column – Contains group_id’s. Same group id applied to all rows of a single asset  
3.  A column (row headers) and B column (group_id) come first and in that order  
4.  All column headers begin with a ‘type’ indicator that matches one of the row headers  
5.  All data points placed at an intersection of matching types: Author name placed at intersection of CREATOR row and CREATOR_ column.   
6.  One ASSET row per asset  
7.  New CREATOR / FILE row for each author / file within a single asset.
8.  Not every asset is going to use each column. You can see the asset of group ID 3 did not have author metadata, so that asset simply did not have any CREATOR rows.
  
Other Tips:  

All dates must be entered in YYYYMMDD format. No hyphens or slashes.
  
If you have multiple tags / keywords for one asset, enter them in this format: tag1@@tag2@@tag3…   
- e.g. biology, habitat restoration, fish -> biology@@habitat restoration@@fish
   
Any data point that contains block text (abstract, file description, etc.) cannot contain leading or trailing whitespace or newlines / line breaks. Esploro will not be able to compile the CSV otherwise.  
- If you must have the new lines in your abstract, you can use html text modifiers to keep the formatting. i.e. &lt;p&gt;&lt;/p&gt;
   
To ensure that your upload compiles properly, eliminate leading and trailing whitespaces from all datapoints.
  
You will need to include an ASSET_AFFILIATION code for each asset. This can be found in Esploro at Research Management -> Manage Organizational Units.  
- Find your department from the collapsible list. Look for where it says “code” and append the code to this string: 01ALLIANCE_UID___xxxxxxxxx
  - For example, an asset affiliated with the library would be 01ALLIANCE_UID___n6370


Once you have your CSV data frame built, head to Esploro and go to Repository -> Manage Import Profiles.
  
Click the three dots on the Profile titled ‘import as draft’ and select ‘Run’.
  
Hit ‘Select File’ and upload the CSV you built. Run the import job. 
  
If the file does not compile, check your data for leading/trailing whitespaces and line breaks.
  
All the assets should now be under ‘Research Deposits’ on your Esploro home page, listed as drafts. Approve them as you would any other asset deposit. 





