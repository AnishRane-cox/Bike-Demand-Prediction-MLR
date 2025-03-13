# Bike Demand Prediction Using Multiple Linear Regression  

This repository contains a **Multiple Linear Regression** model to predict bike demand for **BoomBikes**, a bike-sharing provider in the US. The model analyzes the impact of various factors, such as **weather conditions, seasonality, and user behavior**, on daily bike rentals. The insights help BoomBikes optimize its business strategy post-COVID-19.  

---

##  Features  

✅ **Exploratory Data Analysis (EDA)** – Identifies key factors affecting bike demand.  
✅ **Feature Engineering** – Encodes categorical variables and scales numerical features for improved model performance.  
✅ **Multicollinearity Analysis** – Uses **VIF (Variance Inflation Factor)** to remove highly correlated predictors.  
✅ **Model Training & Evaluation** – Implements **Multiple Linear Regression**, analyzes residuals, and validates predictions.  
✅ **Performance Metrics** – Evaluates model accuracy using R², RMSE, and predicted vs. actual demand plots.  

---

##  Dataset  

The dataset (`day.csv`) contains daily records of bike rentals, categorized by:  

- **Temporal Features**: Season, month, weekday, holiday, and working day.  
- **Weather Conditions**: Temperature, humidity, wind speed, and weather situation.  
- **User Count**: Casual, registered, and total bike rentals (target variable: `cnt`).  

---

## Project Workflow  

1️⃣ **Data Preprocessing**: Handling missing values, feature encoding, and scaling.  
2️⃣ **Exploratory Data Analysis (EDA)**: Understanding demand trends and key influencing factors.  
3️⃣ **Model Building**: Training a Multiple Linear Regression model with significant predictors.  
4️⃣ **Evaluation**: Assessing model accuracy and visualizing residual distributions.  

---

## Key Insights  

📌 **Temperature and Season** significantly impact bike demand.  
📌 **Weather conditions** like humidity and wind speed have moderate effects.  
📌 **Holidays and weekdays** show a minor correlation with demand.  

These insights help **BoomBikes** optimize fleet distribution, pricing, and marketing strategies.  

---

##  Installation & Usage  

```bash
# Clone the repository
git clone [<repository_url>](https://github.com/AnishRane-cox/Shared-Bike/tree/main)

# Install required dependencies
pip install -r requirements.txt

# Run the analysis
python bike_demand_prediction.py
```

---

## License  

This project references the dataset from:  
**Fanaee-T, Hadi & Gama, Joao (2013). Event Labeling Combining Ensemble Detectors and Background Knowledge.**  

For citation details, see the [License Section](#license).  

---

## Contact  

For queries, feel free to reach out!  

Email: hadi.fanaee@fe.up.pt 


## Dataset characteristics

day.csv have the following fields:
	
	- instant: record index
	- dteday : date
	- season : season (1:spring, 2:summer, 3:fall, 4:winter)
	- yr : year (0: 2018, 1:2019)
	- mnth : month ( 1 to 12)
	- holiday : weather day is a holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
	- weekday : day of the week
	- workingday : if day is neither weekend nor holiday is 1, otherwise is 0.
	+ weathersit : 
		- 1: Clear, Few clouds, Partly cloudy, Partly cloudy
		- 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
		- 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
		- 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
	- temp : temperature in Celsius
	- atemp: feeling temperature in Celsius
	- hum: humidity
	- windspeed: wind speed
	- casual: count of casual users
	- registered: count of registered users
	- cnt: count of total rental bikes including both casual and registered
	
## License

Use of this dataset in publications must be cited to the following publication:

[1] Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", Progress in Artificial Intelligence (2013): pp. 1-15, Springer Berlin Heidelberg, doi:10.1007/s13748-013-0040-3.

@article{
	year={2013},
	issn={2192-6352},
	journal={Progress in Artificial Intelligence},
	doi={10.1007/s13748-013-0040-3},
	title={Event labeling combining ensemble detectors and background knowledge},
	url={http://dx.doi.org/10.1007/s13748-013-0040-3},
	publisher={Springer Berlin Heidelberg},
	keywords={Event labeling; Event detection; Ensemble learning; Background knowledge},
	author={Fanaee-T, Hadi and Gama, Joao},
	pages={1-15}
}

## Contact
	
For further information about this dataset please contact Hadi Fanaee-T (hadi.fanaee@fe.up.pt)

