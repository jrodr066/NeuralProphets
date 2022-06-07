## NeuralProphets

#Research Question: 
Recent works have shown that NeuralProphets is powerful when it comes to improving forecasting accuracy because of its ability to take in additional information alternative forecasting models can not. Although NeuralProphet is a powerful algorithm, additional forecasting techniques such as Predict Last Value, Exponential Smoothing, and SARIMA also exist. In this study, we aim to compare the accuracy of NeuralProphets alongside other existing forecasting techniques. Furthermore, we want to forecast the behavior of energy consumption and energy prices in Australia by using data collected in 2015 to 2019.

#Background: 
Precise electricity demand forecast is a crucial part of ensuring electric grid stability. Since the electric grid has limited capacity to store energy, inaccurate electricity demand forecast could lead to, at best, a waste of unused energy, and, at worst, grid failure that leads to significant economic and potential human loss. It is a task that has only become increasingly important in recent years. The extreme weather caused by climate change increases electricity demand fluctuations and puts more stress on the grid. The cold-air outbreak of 2021, for example, devastated Texas’ electric grid and left the entire state without light or heat for weeks (Millin). The introduction of weather-dependent renewable energy sources such as wind and solar also requires the grid operators to know more about the demand ahead of time. Precise short-term forecasts can allow operators to reduce their reliance on polluting standby coal power plants. Precise long-term forecasts can help system operators (and investors) to build more variable power sources such as wind and solar (Rolnick). For all the reasons mentioned above, any improvement an ML algorithm can create in accuracy or speed can create a significant societal impact.

#Project:
In this project, given daily data points of electricity demand and price from January 1st, 2015 to October 6, 2020, for Victoria, Australia, we want to examine and forecast energy demand and energy prices. We will conduct a time series forecast using Meta’s latest deep-learning-based method: NeuralProphets. We will also perform hyperparameter tuning on the model and benchmark it against other forecasting strategies such as Predict Last Value, Exponential Smoothing, and SARIMA 

#Data:
The data we will use consists of daily electricity price and demand data between 1 January 2015 and 6 October 2020 (2016 days total) for Australia's second most populated state, Victoria. A brief description of the data is as follows:

	date : datetime, the date of the recording
	demand : float, a total daily electricity demand in MWh
	RRP : float, a recommended retail price in AUD$ / MWh
	demand_pos_RRP : float, a total daily demand at positive RRP in MWh
	RRP_positive : float, an averaged positive RRP, weighted by the corresponding intraday demand in     AUD$ / MWh
	demand_neg_RRP : float, an total daily demand at negative RRP in MWh
	RRP_negative : float, an average negative RRP, weighted by the corresponding intraday demand in AUD$ / MWh
	frac_at_neg_RRP : float, a fraction of the day when the demand was traded at negative RRP
	min_temperature : float, minimum temperature during the day in Celsius
	max_temperature : float, maximum temperature during the day in Celsius
	solar_exposure : float, total daily sunlight energy in MJ/m^2
	rainfall : float, daily rainfall in mm
	school_day : boolean, if students were at school on that day
	holiday : boolean, if the day was a state or national holiday

An important contextual factor to consider during the time period is the Covid-19 pandemic that started near the end of 2019. In 2020, Australia was among the first to close international borders, followed by a closure of interstate borders. Victoria introduced some of the strictest pandemic-related restrictions on business activity that resulted in a significant portion of its population working from home. We expect to see the impact of lock-down reflected in the data, hence we take out the data for 2020 to ensure an accurate measure of model performance.

#References:
Millin, Oliver T., Jason C. Furtado, and Jeffrey B. Basara. "Characteristics, Evolution, and Formation of Cold Air Outbreaks in the Great Plains of the United States." Journal of Climate (2022): 1-37.

Rolnick, David, et al. "Tackling climate change with machine learning." ACM Computing Surveys (CSUR) 55.2 (2022): 1-96.
