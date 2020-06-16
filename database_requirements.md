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


Energy system optimization modeling requires detailed, accurate data to produce results that are meaningful to policy negotiations. In addition, to enable interested parties to run Temoa-compatible models on their own, the data must be publicly available. The following section describes how the Virginia dataset used in this research was constructed.
Temoa input datasets consist of user-defined technologies, which are linked through a set of user-defined commodities in a network diagram. Each technology is defined by a set of technical and economic parameters, such as capital cost, operations and maintenance costs, emission rates, conversion efficiency, and lifetimes. Individual technologies in the VA dataset do not refer to individual generators, but rather total installed capacity associated with a technology and its vintage. For example, state-wide electricity generation at advanced combined cycle natural gas plants is represented by ‘ENGAACC’, which converts the input commodity (natural gas) to the output commodity (pre- transmission and distribution electricity).
A simplified network diagram for the Virginia dataset is shown in Figure. In this conceptual image, all power plants that use the same type of fuel are grouped into a single category, as they will be throughout this report. The final commodity, ‘ELCDMD’, represents the user-specified total end-use demand in Virginia. Energy technologies consume energy commodities such as natural gas or solar, and produce either ELC (if from traditional fuels) or ELCRNWB (if from those technologies classified as renewable by the Virginia legislature). The renewable electricity commodity is used to track total renewable generation to meet a RPS. Just as in the actual electricity market, these commodities must then flow through transmission and/or distribution technologies beforethey are converted to demand. The following section details the construction of the Virginia dataset.

Data

Electricity Demand (sales data)
eia_elec_sales_va_all_m (millionkilowatthours)

Technologies and Commodities
There are two categories of energy generation technologies used in the construction of the input dataset for North Carolina: residual (or existing) technologies, and future technologies.
Capacity of residual tecnologies in Viginia (2018)
capacity_factors_annual 
