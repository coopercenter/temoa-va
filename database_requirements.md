Energy Systems Modeling using TEMOA 

Plan of Action  

May 26, 2020 

Overview 

The US state of Virginia has passed a new bill pledging to transition to 100% clean energy by 2050. Under the terms of the bill, utilities Dominion Energy and American Electric Power will retire all-electric units that release carbon emissions while acquiring or constructing renewable energy generation systems. The overall goal of our project would be to model the current and future state of the electricity market of Virginia, using Temoa (Tools for Energy Model Optimization and Analysis) 

Milestone 

Virginia Database Requirements 

(green – data available, red – have to make assumption) 

| Item                                                     | Method                                                       | Source (name as in azure database)     |
|----------------------------------------------------------|--------------------------------------------------------------|----------------------------------------|
| Fraction of yearly demand by season (Spring, Summer..)   | Calculation based on monthly electricity retail sales data   | “retail_sales_of_electricity_monthly”  |
| Fraction of yearly demand by hours of day                | Make assumption based on smaller scale data I can find       |                                        |
| Percent loss during transportation and distribution      | EIA Estimate                                                 |                                        |
| Electricity generation for each power plant in Virginia  | Extract from EIA 860 database                                | eia860_plant_y2018                     |
| Fuel price                                               | Database                                                     | fuel                                   |
