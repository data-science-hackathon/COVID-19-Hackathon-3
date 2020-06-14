# COVID-19-Hackathon

COVID-19 Hackathon
Liem Luong
Submission for Interactive Visualization

Introduction:
COVID-19 is a global pandemic and its impacts can be seen around the world. There are a lot of visualization on the internet and majority of them are focusing on tracking the confirmed cases and confirmed deaths across the location dimension (world level, country level, city level, and county level). Rather than repeating the same visualization on the internet, I decided to look at the COVID-19 from a different perspective based on the stringency index data from the OxCGRT Covid Policy Tracker. This will help the viewers to see the impact from the containment and closure policy between the countries around the world.

Source:
https://www.bsg.ox.ac.uk/research/research-projects/coronavirus-government-response-tracker
https://github.com/OxCGRT/covid-policy-tracker

Data Exploration:
Upon exploring the data, there are some transformation to clean up an enhance the quality of the data:
1. The data provides the detail of indexes status for every country on the daily timestamp. However, not all countries will have the latest status dues to the reporting structure / timing delay of each countries around the world. Therefore, null values are presented in the dataset. The solution was applied to take the last known status of each null values as the latest status. This way, it will ensure the data is clean and the logic working for the visualization later.

2. Enrich the dataset with more field. By matching each countries to the approriate region (based on the UN Geogrphic Region
   https://unstats.un.org/unsd/methodology/m49/), we can later view filter and view the data on the regional level.
    
3. Country names can be ambiguous for the tools to recognize and varies from many sources of how it is spelling the name in short or abbreviation. By adding the latitude and longitude fields into the dataset model, this will ensure the unique country in the dataset for the visualization down the road effectively.

4. Encoding and color are very important to the visualization. 
- The originial data source provide the statuses based on numeric index values (0, 1, 2, 3, 4). This will be not intuitive meaning for the regular viewer. By merging the index description for all C1 to C8 index into the data model, we can decode and show the real status that will be helpful for the viewers to read the content.
- The status of the indexes (0, 1, 2, 3, etc.) show the progression from good, neutral, bad, worst, etc. From the human cognitive brain, we are adapted to the stop light color (GREEN = good, YELLOW = neutral, RED = worst), this stop light color theme was applied throughout the visualization for all C1 - C8 indexes. 

Implementation:
1. Data transformation (logic merging, formating, joining table, etc.) was done in Excel Power Query tool. The visualization was done in Tableau and save on the Tableau Public website. 

2. The visualization for each visual are created with the minimalist theme in mind (This mean, not tangle lot of visuals into a small space). Rather, each visual is presented with its best layout so that the viewers wont get distraction and can focus on the message of the visualization delivers. This minimal theme enhance the simplicity and easy navigation around the content.

3. The play button on the right hand side is available to see the time series animation over time from Jan 1st 2020 till the latest data available today. 

4. The country and region filter buttons are available to help users to drill down the data and focus on the specific countries / regions as needed.

Take away:
- This visualization achieves the objective by providing a different views of the COVID-19 impact around the world based on the containment and closure policy.

- This visualization provides viewer a venue to compare the trend, performance, and status overtime for each countries and regions for every all policy indicators C1 to C8. 

Reference:
- All the files and data for the project are in this githut repository

- The Tableau visualization is also available online interactive and downloadable at https://public.tableau.com/profile/liem.luong#!/

- Online interactive visualization (scroll down and click on links from the METADATA section to view the visualization)
  https://public.tableau.com/profile/liem.luong#!/vizhome/COVID-19ContainmentandClosurePoliciesTimeSeries/Introduction

