---
section_id: Jobs & Bulk Operations
nav_order: 4
title: De-duping Researchers
topics:
---
## Relevant Ex Libris Documentation
- [How to Bulk Merge Duplicate Researchers](https://knowledge.exlibrisgroup.com/Esploro/Training/Esploro_How-To_Videos/Bulk_Actions/How_to_Bulk_Merge_Duplicate_Researchers)

## How to De-Dupe Researchers

Seth Thompson 1/7/2025  

As assets come in through deposits and smart harvests, it is possible for duplicate researchers to be created.   
This can happen in a couple ways. For example, somebody making a manual deposit could fail to check that their authors are already in the system and instead enter an affiliated researcher as non-affiliated.   
Whatever the reason may be, a list of duplicate affiliated authors will slowly build up in the non-affiliated researcher list.  

## Individual De-Duplication

![image](https://github.com/user-attachments/assets/efe9efa0-8329-40d6-9928-fc58679e63cb)  

Searching for Christopher Williams returned 3 researchers – one affiliated and two non-affiliated.  
- Click the three horizontal dots on one of the non-affiliated researchers and go to ‘View Assets.’
  - Use this asset list to determine if the non-affiliated researcher is a duplicate of an affiliated researcher (the U of I Christopher Williams), or simply a different researcher with the same name.
- If you determine that the non-affilated member is a copy of an affiliated member, go back to the original search page where the duplicates were listed.
- Click the three horizontal dots again and go to ‘Move all assets and grants.’  
- Search for and select the corresponding affiliated researcher, check ‘delete current researcher,’ and click Move.

You have now moved all assets to the affiliated U of I researcher and deleted the duplicate profile.  

## Bulk De-Duplication

Perform a bulk merge as routine maintenance or if you suspect a large number of duplicates have built up.  

- For routine maintenance or if you suspect a large number of duplicates have built up.  
- Click researchers in side tab -> ‘Potential Duplicate Researchers Report / Bulk Merge Duplicate Researchers’  
- Check ‘Export Report’  
- Check ‘Check affiliated researchers’  
- For mode, I recommend checking ‘New Researchers.’ This will only look at researchers that have been added since you last ran the report.
  >Explanation – Say you have affiliated researcher John(1). You run a duplicate report at the start of 2024, and it returns two non-affiliated researchers of the same name. You find that John(2) is a duplicate, while John(3) is a separate researcher that needs to be kept. You merge John 2 and keep John 3.
  >
  >If at the start of 2025 you select ‘All researchers’ as your mode, the report will once again return John 3 as a potential duplicate, even though you determined in the past that he is a separate researcher. As such, you should save this mode for instances where you are suspicious of old duplicate researchers not being properly screened out.
  >
  >If you select ‘New Researchers’ as your mode, Esploro will only check researchers that have been added since the last report, so John 3 will be left out and potential duplicates will only be found if there is a John(4/5/6 etc).

Click Submit. This will run a job that generates a report.

When the job finishes running, you need to download the report.
- Admin -> monitor jobs -> history tab
- The job will be named “Duplicate Researcher Report – mm/dd/yyyy”
- Click the three horizontal dots, go to ‘Report’
- Click link to download report
- Open the CSV you just downloaded.
  - There will be groups of researchers separated by a single blank row. In each name group, the affiliated researcher will be listed first, followed by non-affiliated potential duplicates.
  - Go back to Esploro and check the assets of each potential duplicate to see if they need to be merged or kept.


![image](https://github.com/user-attachments/assets/d6c83205-ce48-458c-94f9-3e5a34f4138a)

In the CSV, the only column you will make changes to is ‘Merge Status.’   
For each name grouping where you found a duplicate, simply type ‘k’ under merge status, in the same row as the affiliated researcher.  
Type ‘m’ in the same column, in every row that contains a duplicate.
>The ‘k’ means keep, and the ‘m’ means merge. (Later when you submit this CSV, the names marked ‘m’ will have all their assets transferred to the name marked ‘k’, then the ‘m’ names will be deleted.)

Any names where the Merge Status column is left blank will simply be unchanged.  
After marking all your keeps and merges, save the CSV.  
- In Esploro, click researchers -> ‘Potential Duplicate Researchers Report / Bulk Merge Duplicate Researchers’  
- Check ‘Bulk Merge’  
- Upload the CSV you just edited  
- Click submit. This will run a job.
  
You can look in Admin -> monitor jobs -> history to see if all the merges completed successfully. The specified duplicates should be gone, with all assets transferred to affiliated researchers.  

