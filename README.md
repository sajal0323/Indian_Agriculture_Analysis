
# Indian Agriculture -Dashboard

### Dashboard Link :https://app.powerbi.com/groups/b6c87d0e-ad7f-4a36-b3d3-3fb94e458f70/dashboards/2bd11076-c4d5-4281-a58e-92c84c984b2e?ctid=0c2c5eb2-7477-4593-ac08-f1de3be027d2&pbi_source=linkShare

## Problem Statement

This dashboard helps to conducted an extensive analysis of agricultural data using Power BI, revealing valuable insights through visualizations and DAX functions. Our findings encompass key trends, patterns, and actionable recommendations for optimizing agricultural processes and decision-making.
   
Additionally, the analysis sheds light on the efficacy of Minimum Support Price (MSP) implementation, providing valuable insights for policymakers and stakeholders.


### Steps followed 

- Step 1 : Load data into Power BI Desktop, dataset is a csv file.
- Step 2 : Open power query editor & in view tab under Data preview section, check "column distribution", "column quality" & "column profile" options.
- Step 3 : Also since by default, profile will be opened only for 1000 rows so you need to select "column profiling based on entire dataset".
- Step 4 : It was observed that in none of the columns errors & empty values were present except column named "Production[in_tonnes]".
- Step 5 : These null values were not taken into account as only less than 1% values were null in this column and were replaced by zero.
- Step 6 : In the report view, under the view tab, theme was selected.

- Step 7 : In Indian Agricultutre Analysis report page,Visual filters (Slicers) were added for three fields named "State_Name", "Crop_Year" & "Crop" and two buttons, "Apply all Slicers" and "Clear all Slicers" were also added.

    In Crop MSP Prediction report page, Slicer "Crop" was added.
- Step 8 : In Indian Agricultutre Analysis report page, key insights were:

        a) Top 5 crops by Production was visualized using Stacked Bar Chart, in Y-axis "Crop" column was drag and drop and in X-axis "Production(in_tonnes)" column was drag and drop.
           Using visual level filter from the filters pane, Top N filtering was selected for consideration and in show items column, 5 was written, then filter was applied.
        b) Top 3 States by Production was visualized using Funnel Chart, in Category "State_Name" column was drag and drop and in values "Production(in_tonnes)" column was drag and drop.
           Similarly,in Top N filtering 3 was written.
        c) Top 3 Districts by Production was visualized using Pie Chart, in Legend "District_Name" column was drag and drop and in values "Production(in_tonnes)" column was drag and drop.
           Similarly,in Top N filtering 3 was written.
        d) Production by each season was visualized using donut chart, in Legend "Season" column was drag and drop and in values "Production(in_tonnes)" column was drag and drop.
           For this visualization,Advanced filtering was selected and to show items when the value does not contain "Whole Year" was written.
        e) Production Prediction for 1 year was visualized using Line Chart,in Y-axis "Crop" column was drag and drop and in X-axis "Crop_Year" column was drag and drop.
           In further Analysis Visual option in visualization pane,forecast option was made "On" and length was set to 1.
        f) Production by each Crop_Year was visualized using "Tree Map",in Category "Crop_Year" column was drag and drop and in values "Production(in_tonnes)" column was drag and drop.
    Snap of first report page,
    ![image](https://github.com/sajal0323/Indian_Agriculture_Analysis/assets/120362510/82052bda-354b-4921-acde-c8e0d105efc0)
-   Step 9 : In Crop MSP Prediction report page, key insights were:
 
          a) Production of Crop vs Area(in_hectares) for each year was visualized using Line and Stacked Column Chart
             In column Y-axis "Production(in_tonnes)" column was drag and drop,in X-axis "Crop_Year" column was drag and drop and in Line Y-axis "Area(in_hectares)" column was drag and drop.
          b) How many times a particular Crop gets MSP was visualized using Stacked column Chart.
             In X-axis "Crop_Year" column was drag and drop and in Y-axis "Production(in_tonnes)" column was drag and drop.
             Conditional formatting was also done for columns under format your visuals pane by selecting MSP measure.
    Snap of second report page,
    ![image](https://github.com/sajal0323/Indian_Agriculture_Analysis/assets/120362510/541a0a43-3fda-4beb-ab08-7c26e2734677)

- Step 10 : Text box were also inserted in both report pages to name "Indian Agricultutre Analysis" the 1st report and "Crop MSP Prediction" the 2nd page.
- Step 11 : Several New measure were also created to find Average Production, Crops_count, Crop_Year count, District count, Farmer_getting_MSP, MSP, Total Production, State count,Season count.
            
            Following DAX functions were written respectively:
                Avg. Production = AVERAGE(crops_data[Production (in tonnes)])
                crop count = DISTINCTCOUNT(crops_data[Crop])
                Crops year count = DISTINCTCOUNT(crops_data[Crop_Year])
                District Count = DISTINCTCOUNT(crops_data[District_Name])
                Farmer_getting_MSP = IF(SUM(crops_data[Production (in tonnes)])<=AVERAGE(crops_data[Production (in tonnes)]),"YES","NO")
                MSP = SWITCH(TRUE(),SUM(crops_data[Production (in tonnes)])<=AVERAGE(crops_data[Production (in tonnes)]),"Green","Red")
                Total Production = SUM(crops_data[Production (in tonnes)])
                State Count = DISTINCTCOUNT(crops_data[State_Name])
                Season Count = DISTINCTCOUNT(crops_data[Season])
      
- Step 12 : Seperate card visuals were added for each new measure.
            
  Snap of card visuals,
![image](https://github.com/sajal0323/Indian_Agriculture_Analysis/assets/120362510/9f02fe69-365d-4b8b-a01c-83fe3dc50223)

 
 - Step 13 : The report was then published to Power BI Service.
 
 # Report Snapshot (Power BI DESKTOP)
 # First page
![image](https://github.com/sajal0323/Indian_Agriculture_Analysis/assets/120362510/6a2b81d5-53d4-4ffd-8461-94c70fbd4586)

# Second page
![image](https://github.com/sajal0323/Indian_Agriculture_Analysis/assets/120362510/83408617-2fab-45f9-8eee-e8553bbf165b)

# Indian_Agriculture_Analysis-Dashboard.md.txt
Displaying # Indian_Agriculture_Analysis-Dashboard.md.txt.

