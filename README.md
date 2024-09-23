# Analysis on the best airplanes for purchase
## 1 Business Understanding
### 1.1 Overview 

**Tujenge Limited** is a global travel platform that provides luxurious transportation and accommodation services to its clients, which include business owners and travelers seeking both convenience and comfort. It was started in the year 2002 with Gideon Ochieng as the founder. The company initially focused on helping businesses coordinate group travel across different states and countries. It facilitates transportaion and accomodations for business owners and also personns who travel for ammusement. Since it started, Tujenge LTD has expanded with at least `5 branches` in every continent due to its amaizing offers and services it provides for its customers. The company has served approximately 2 million clients worldwide, thanks to its excellent service and attractive offers.

### 1.2 Problem statement

With the increase of customers, the company has had problems getting planes ready for the users in time while using third party airlines. hence the company has decided to purchase and operate it own airplaces for both commercial and private enterprice. With our own airplanes we will be able to ensure that our customers dont get any delays which we face when using other airline. The critical issue now is determining which aircraft models are the safest and lowest-risk options for the company's expansion into the aviation industry.

### 1.3 Objectives
1. To clean the dataset
2. To anayze the dataset and come up with aactionalble insight
3. To create an interactive dashboard

### 1.4 Stakeholders
- Tujenge LTD Management
- Tujenge LTD Investors

### 1.5 Success matrix
- Being able to determining which aircraft are the lowest risk for the company
- Being able to translate my findings into actionable insights that the head of the new aviation division can use to help decide which aircraft to purchase
- Creating an interactive dashboard
### 1.6 Assumptions
- The dataset accurately reflects aviation risk factors 
- The analysis assumes that aircraft models with lower accident frequency and severity are more suitable for purchase.
### 1.7 Limitations
- The dataset focuses on civil aviation accidents in the U.S. and international waters, which may not account for regional risks in areas where Tujenge operates.
- The data spans multiple decades, and technological advancements over time may impact the relevance of older incidents.


## 2. Data Understanding
The data is from the National Transportation Safety Board(NTSB) that includes aviation accident data from 1962 to 2023 about civil aviation accidents and selected incidents in the United States and international waters.

### 2.1 Data Overview
The data id from National Transportation Safety Board (NTSB) and it contains aviation incidents from 1962 to 2023.
The dataset has 90,348 records which are instances of every incident or accident it also has 31 columns which are fields related to aviation accidents and incidents.
This are the columns on the dataset:
      (['Event.Id', 'Investigation.Type', 'Accident.Number', 'Event.Date',
       'Location', 'Country', 'Latitude', 'Longitude', 'Airport.Code',
       'Airport.Name', 'Injury.Severity', 'Aircraft.damage',
       'Aircraft.Category', 'Registration.Number', 'Make', 'Model',
       'Amateur.Built', 'Number.of.Engines', 'Engine.Type', 'FAR.Description',
       'Schedule', 'Purpose.of.flight', 'Air.carrier', 'Total.Fatal.Injuries',
       'Total.Serious.Injuries', 'Total.Minor.Injuries', 'Total.Uninjured',
       'Weather.Condition', 'Broad.phase.of.flight', 'Report.Status',
       'Publication.Date'])

#### Column info
      Column                  Non-Null Count  Dtype  
---  ------                  --------------  -----  
 0   Event.Id                88889 non-null  object 
 1   Investigation.Type      90348 non-null  object 
 2   Accident.Number         88889 non-null  object 
 3   Event.Date              88889 non-null  object 
 4   Location                88837 non-null  object 
 5   Country                 88663 non-null  object 
 6   Latitude                34382 non-null  object 
 7   Longitude               34373 non-null  object 
 8   Airport.Code            50249 non-null  object 
 9   Airport.Name            52790 non-null  object 
 10  Injury.Severity         87889 non-null  object 
 11  Aircraft.damage         85695 non-null  object 
 12  Aircraft.Category       32287 non-null  object 
 13  Registration.Number     87572 non-null  object 
 14  Make                    88826 non-null  object 
 15  Model                   88797 non-null  object 
 16  Amateur.Built           88787 non-null  object 
 17  Number.of.Engines       82805 non-null  float64
 18  Engine.Type             81812 non-null  object 
 19  FAR.Description         32023 non-null  object 
 20  Schedule                12582 non-null  object 
 21  Purpose.of.flight       82697 non-null  object 
 22  Air.carrier             16648 non-null  object 
 23  Total.Fatal.Injuries    77488 non-null  float64
 24  Total.Serious.Injuries  76379 non-null  float64
 25  Total.Minor.Injuries    76956 non-null  float64
 26  Total.Uninjured         82977 non-null  float64
 27  Weather.Condition       84397 non-null  object 
 28  Broad.phase.of.flight   61724 non-null  object 
 29  Report.Status           82508 non-null  object 
 30  Publication.Date        73659 non-null  object 


### 2.3 Summary Statistics
This provides statistical summary for numerical columns
	   Number.of.Engines	 Total.Fatal.Injuries	Total.Serious.Injuries	Total.Minor.Injuries	Total.Uninjured
count	82805.000000	      77488.000000	         76379.000000	         76956.000000	      82977.000000
mean	1.146585	            0.647855	               0.279881	               0.357061	            5.325440
std	0.446510	            5.485960	               1.544084	               2.235625	            27.913634
min	0.000000	            0.000000	               0.000000	               0.000000	            0.000000
25%	1.000000	            0.000000	               0.000000	               0.000000	            0.000000
50%	1.000000	            0.000000	               0.000000	               0.000000	            1.000000
75%	1.000000	            0.000000	               0.000000	               0.000000	            2.000000
max	8.000000	            349.000000	            161.000000	            380.000000	         699.000000

### 2.4 Data Quality
The dataset has multiple missing values that will be delt with by ether imputation or dropping rows and columns.
This is the percentage of missing values in every column:
   Event.Id                   1459
   Investigation.Type            0
   Accident.Number            1459
   Event.Date                 1459
   Location                   1511
   Country                    1685
   Latitude                  55966
   Longitude                 55975
   Airport.Code              40099
   Airport.Name              37558
   Injury.Severity            2459
   Aircraft.damage            4653
   Aircraft.Category         58061
   Registration.Number        2776
   Make                       1522
   Model                      1551
   Amateur.Built              1561
   Number.of.Engines          7543
   Engine.Type                8536
   FAR.Description           58325
   Schedule                  77766
   Purpose.of.flight          7651
   Air.carrier               73700
   Total.Fatal.Injuries      12860
   Total.Serious.Injuries    13969
   Total.Minor.Injuries      13392
   Total.Uninjured            7371
   Weather.Condition          5951
   Broad.phase.of.flight     28624
   Report.Status              7840
   Publication.Date          16689