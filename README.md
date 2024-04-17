![Screenshot of Road Accident Dashboard-1](<img width="590" alt="image" src="https://github.com/jyokable5/RoadAccidentDashboard_PowerBI/assets/106279459/400e84f8-5920-473e-a1e1-91036ef78665">)

![Screenshot of Road Accident Dashboard-2](<img width="590" alt="image" src="https://github.com/jyokable5/RoadAccidentDashboard_PowerBI/assets/106279459/723d045e-454a-4695-bb0e-5e706965383a">)

The dataset can be accessed from this link: Road Accident Data (UK) -> https://drive.google.com/drive/folders/1G3BFBOcSn-i-8aJ6c_MgGWJzhYWM_Okb?usp=sharing

# Dashboard Requirements 
1. Primary KPI's - Total Casualties and Total Accident values for Current Year and YoY Growth
2. Primary KPI's - Total Casualties by Accident Severity for Current Year and YoY Growth
3. Secondary KPI's - Total Casualties with respect to Vehicle Type for Current Year
4. Monthly Trend showing comparison of Casualties for Current Year and Previous Year
5. Casualties by Road Type for Current Year
6. Current Year Casualties by Area/Location & Day/Night
7. Total Casualties and Total Accident by Location


# DAX Formulas Used in Measures
1. Total Casualties For Current Year and Year on Year Growth

(a) Current Year To Date Casualties -- CY Casualties Measure

       CY Casualties = TOTALYTD(SUM(Data[Number_of_Casualties]), 'Calendar'[Date])
(b) Previous Year Casualties -- PY Casualties Measure

       PY Casualties = CALCULATE(SUM(Data[Number_of_Casualties]), SAMEPERIODLASTYEAR('Calendar'[Date]))
(c) Year on Year Growth of Casualties - YoY Casualties Measure

       YoY Casualties = ([CY Casualties] - [PY Casualties])/[PY Casualties]
2. Total Accidents for Current Year and Year on Year Growth

(a) Current Year Accidents Count -- CY Accidents Count Measure

    CY Accidents Count = TOTALYTD(COUNT(Data[Accident_Index]), 'Calendar'[Date])
(b) Previous Year Accidents Count -- PY Accidents Count Measure

    PY Accidents Count = CALCULATE(COUNT(Data[Accident_Index]), SAMEPERIODLASTYEAR('Calendar'[Date]))
(c) Year on Year Growth of Accidents - YoY Accidents Measure

    YoY Accidents = ([CY Accidents Count]-[PY Accidents Count])/[PY Accidents Count]


* I have used this Youtube tutorial for this project https://www.youtube.com/watch?v=Hn9f13uoLAQ
  
