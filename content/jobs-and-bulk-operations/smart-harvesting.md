---
section: Jobs & Bulk Operations
nav_order: 6
title: SmartHarvesting
topics:
---

## Refining Smart Harvesting

Last Updated: 2/7/2024, Jeremy Kenyon

- By default Smart Harvesting will be run without a date range, so the system will try to find anything and everything that person has in the CDI.  
- This results in a “fire hose” – way too many items to sift through.

To refine the harvesting by date/time:

First, update researchers’ Last Smart Harvesting Date:

1. Admin \> Run a Job \> Select “Update Set of Researchers”. Click Next.  
   2. Then, choose a set (see this [video on Creating Sets](https://knowledge.exlibrisgroup.com/Esploro/Product_Documentation/Esploro_Online_Help_\(English\)/Working_with_the_Esploro_Research_Hub/027_Searching_in_the_Esploro_Research_Hub), if Needed; Sets are in second half of video). Click Next.  
   3. At the bottom, select “Last Smart Harvesting Date” and select the oldest date you want to have your harvest run on. Click Next.  
      * Updating this will override other dates, so you can effectively re-run smart harvests by changing the date field if desired.  
   4. Confirm your choices. Click Submit.  
      * Is the set you selected the one you want?  
      * Have you only checked the boxes you want?  
          
        

   Second, run the smart harvest:  
1. Repository \> Smart Harvesting/Manage Profiles \> CDI  
2. Click on CDI to begin.  
3. At the bottom, under RUN, select the set against which you want to run your harvest, then click “Run Now”.

   This will run the Smart Harvest against the CDI, using the date listed on the researcher profile as a parameter.