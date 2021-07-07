# Land use, land use change, and forestry

Notes and comments are indicated with **[bold, bracketed text]**
Other text and equations are pulled out of simulation files from Energy Innovations. Some edits made for clarity. Data input files are publicly available (https://us.energypolicy.solutions/docs/download.html) and also copied here for accessibility and version control. 

Energy Innovations: https://github.com/Energy-Innovation/eps-minnesota

Documentation: https://us.energypolicy.solutions/docs/lulucf.html


![image](https://user-images.githubusercontent.com/8172631/123455113-f5334f00-d5a6-11eb-9995-0a0cc6e336f6.png)


## BAU

**[BAU scenario takes average of high and low rates of sequestration scenarios from the US inventory for 2015, 2020, 2025, and 2030 (Report to UNFCC, Table 3, below) and uses the TREND function to return a linear trend using the least squares method to extend the projected sequestration to 2050.]**

https://unfccc.int/files/national_reports/biennial_reports_and_iar/submitted_biennial_reports/application/pdf/2016_second_biennial_report_of_the_united_states_.pdf (page 34, Table 3)

  ![image](https://user-images.githubusercontent.com/8172631/123321446-9dd6a580-d4f8-11eb-930c-e38e907ae229.png)


## From Potential Land area

### Acres Available Afforestation and Reforestation	

Low Estimate = 100 million acres

High Estimate = 450 million acres
		
Gorte (https://www.fas.org/sgp/crs/misc/R40562.pdf) estimates the fraction of the 1.8 billion acres of undeveloped land that could sustain a forest.  (It does not matter if it is reforestation or afforestation- we are looking at the total land area that is not now forest but could become forest.)  We take the average of Gorte's low-end and high-end estimates.		
		
Acres Available	MN = 24,751,690 acres	
		
The state has a total land area of roughly 50,961,000 acres, so this represents converting 48.6% of the state's land into forest (on top of existing forest lands).		
		
Acres Available Annually for Conversion		

This depends on the speed with which it would be possible to conduct tree planting operations on the available acres.  In practice, this may depend as much on financial and legal hurdles as on technical challenges, such as workforce or tree availability.  Lacking good data on this topic, and given the very large potential land area that could sustain a forest, it is best to assume a long time horizon, to avoid making the afforestation/reforestion policy lever unrealistically strong. Accordingly, we will assume that if all of the suitable lands could be converted to forest, it would require 1 year for each 0.1% of the lower 48 states' contiguous land area.		
		
0.1% = fraction of lower 48 states' land area forested per year	

486 = years needed to afforest/reforest all available acreage	
		
**50,961 = acres able to be afforested or reforested per year**	


### Set asides
Annual Acreage Cut in US						
thousand acres | Clearcut | Partial Cut		
--|--|--
All Owners | 3774 | 6081				
						
We assume that a "Partial Cut" results in 50% deforestation on a given acre, so we weight partial cut half as heavily as clearcut when determining the number of acres cut per year.						
						
Acres Cut per Year (MN) |  |  | |
--|--|--|--
6814500	| acres cut in US| 144568.1075 | Acres cut in state	
818,816,000 | total forest acres in the US | 17371000 | Forest acres in state				
0.008322383 | fraction of acres cut / year (national)	|  | 	

Acres cut in MN = forest acres in state * national fraction

How many of these acres are available annually for set-asides?		

This depends on the speed with which timber harvesting could be scaled down, given the need to find replacement materials for forest products.

It also is likely not desirable to completely cease timber harvesting, as wood is a renewable resource and may be better than fabricating certain replacement materials. Lacking good data on this, we will assume that timber harvesting could be reduced from its present scale by 2% of its current level per year. The model run period (2016-2050) is 35 years long, so if the policy were to be implemented in full strength throughout the entire model run, there would be a total 70% reduction in timber harvesting per year by the end.						

2% = potential reduction in timber harvesting achievable per year		

**2891 = acres potentially available for forest set-asides per year**	


### Improved forest management

No data for acres of forest land currently using best management practices (US Forest Service, National report on Sustainable Forests. 2010). 

Acreage of Forest Eligible for Improved Management Practices	
 
Total State Forest Acreage = 17,371.00 acres **[This seems like a mistake in units?]**
 
0 = Fraction of forest acreage already using best management practices

17,431 = acres eligible for improved management practices **[unit error persists?]**


Fraction Achievable Each Year	

Unlike afforestation/reforestation and set-asides, improved forest management has to be maintained every year to keep getting carbon benefits.  Accordingly, each year, any acreage affected by the Improved Forest Management policy is considered to be "newly" affected acreage by that policy this year, for purposes of this variable.	
	
We assume that within the model run timeframe, half of the forests not yet under best management practices could be brought under such practices.  Remainder may be too remote, have legal/ownership complications, or other issues.	
	
50% = fraction of eligible forest that could be brought under best management practices during model run
	
**8,686 = acres potentially affected by improved forest management per year** **[unit error persists?]**


### Avoided deforestation
When logging occurs but does not change the land type from forest to non-forest, this does not count as deforestation for purposes of this model.

Logging in the United States generally occurs on land that remains forest afterward, and as such, reduction of this timber harvesting is governed by the "Forest Set-Asides" policy lever, not the "Avoid Deforestation" policy lever.

Accordingly, we assume zero potential for CO2 abatement from avoiding deforestation in the United States.


## CO2 sequestered per acre

### Afforestation / Reforestation	

Forest Carbon Sequestration per Acre per Year	

We use an area-weighted average of the annualized "No Harvest" carbon sequestration rates from our county-level dataset.	
	
2.729 metric tons CO2 / acre / yr

	
### Forest Set-Asides	
Total Aboveground Carbon in U.S. Forests = 14312 million metric tons C
	
Total U.S. Forest Acreage = 751	million acres
	
Live Aboveground Carbon per Forest Acre	= 19.06	metric tons C/acre =  19,057,257 g C/acre =  69,876,609 g CO2/acre
	
Felling Cycle Length = 40 years
	
Avoided CO2 release per Year =  1,746,915 g CO2 / acre / yr

### Improved management

County data: Present value of carbon uptake over an 85 year timeline at a discount rate of 5%. Converted to annual value.

2.6 tons CO2/acre/yr (average of high and low estimate)
