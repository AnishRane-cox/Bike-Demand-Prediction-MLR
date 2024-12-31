# Bike Demand Prediction Using Multiple Linear Regression

This project aims to predict the demand for shared bikes for BoomBikes, a bike-sharing provider in the US. Due to significant revenue losses during the COVID-19 pandemic, BoomBikes wants to understand the variables that most influence demand in order to optimize business strategy for a post-lockdown recovery. This analysis uses a dataset that includes daily bike demand data alongside various factors like weather, season, and user behavior, which are essential for building a reliable model.

---

Table of Contents

- [Dataset Characteristics](#dataset-characteristics)
- [Project Workflow](#project-workflow)
- [Feature Engineering](#feature-engineering)
- [Model Building](#model-building)
- [Evaluation and Insights](#evaluation-and-insights)
- [License](#license)
- [Contact](#contact)

---

## Dataset Characteristics

The dataset (`day.csv`) contains daily records of bike-sharing demand along with various attributes influencing it:

| Field       | Description                                                                                               |
|-------------|-----------------------------------------------------------------------------------------------------------|
| `instant`   | Record index                                                                                              |
| `dteday`    | Date of the record                                                                                        |
| `season`    | Season (1: spring, 2: summer, 3: fall, 4: winter)                                                         |
| `yr`        | Year (0: 2018, 1: 2019)                                                                                   |
| `mnth`      | Month (1 to 12)                                                                                           |
| `holiday`   | Whether the day is a holiday (0: no, 1: yes)                                                              |
| `weekday`   | Day of the week                                                                                           |
| `workingday`| Whether the day is a working day (1: yes, 0: no)                                                          |
| `weathersit`| Weather situation (1: clear, 2: misty/cloudy, 3: light rain/snow, 4: heavy rain/snow)                     |
| `temp`      | Temperature (normalized)                                                                                  |
| `atemp`     | "Feels-like" temperature (normalized)                                                                     |
| `hum`       | Humidity (normalized)                                                                                     |
| `windspeed` | Wind speed (normalized)                                                                                   |
| `casual`    | Count of casual (non-registered) users                                                                    |
| `registered`| Count of registered users                                                                                 |
| `cnt`       | Total count of bike rentals (dependent variable)                                                          |

---

## Project Workflow

### Step 1: Data Preparation and Cleaning

1. **Loading and Basic Exploration**: Import libraries, load data, and conduct preliminary checks (e.g., `shape`, `describe`, `info`) to understand data structure.
2. **Feature Segmentation**: Segment columns into categorical, numerical, and datetime for easier handling.
3. **Removing Unnecessary Columns**: Drop the `dteday` column, as it’s redundant for modeling.
4. **Type Conversion**: Convert categorical variables to `category` type for better handling in model training.

### Step 2: Exploratory Data Analysis (EDA)

- **Numerical Variables**: Use scatter plots and pair plots to visualize relationships among numerical variables (e.g., `temp`, `atemp`, `hum`, `windspeed`, and `cnt`).
- **Categorical Variables**: Use box plots to understand the effect of categorical variables (e.g., `season`, `holiday`, `workingday`, `weathersit`) on bike demand.

### Step 3: Data Preprocessing and Feature Engineering

1. **Dummy Encoding**: Create dummy variables for categorical columns to prepare data for regression modeling.
2. **Scaling**: Normalize numerical variables using MinMaxScaler to scale them between 0 and 1, making model coefficients comparable.
3. **Train-Test Split**: Split the data into training (70%) and testing (30%) sets.

### Step 4: Model Building

1. **Linear Regression Model**:
   - Fit an initial model using all features.
   - Conduct recursive feature elimination based on p-values and VIF (Variance Inflation Factor) to remove multicollinear features, focusing on significant predictors.
2. **Variance Inflation Factor (VIF)**: Calculate VIF for each feature to identify multicollinearity. Drop features with high VIF iteratively until multicollinearity is minimized.

### Step 5: Model Evaluation

1. **Residual Analysis**: Plot the residuals to check if they are normally distributed, indicating a good model fit.
2. **Test Set Prediction**: Use the optimized model on the test set to predict bike demand.
3. **Performance Metrics**: Plot predicted vs. actual demand values to evaluate model accuracy.

---

## Evaluation and Insights

- **Key Features Impacting Demand**: Variables like temperature, season, and year show strong correlation with bike demand. Weekday, holiday, and weather conditions have a weaker correlation.
- **Recommendations**: Insights suggest that demand may be influenced more by climate and seasonal factors than specific days, which could inform promotion and fleet allocation strategies.

---

## License

If you use this dataset in any publication, please cite it as follows:

Fanaee-T, Hadi, and Gama, Joao, "Event labeling combining ensemble detectors and background knowledge", *Progress in Artificial Intelligence* (2013): 1-15. Springer Berlin Heidelberg. doi:10.1007/s13748-013-0040-3.

```bibtex
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
```

---

## Contact

For further details on the dataset, please contact:

**Hadi Fanaee-T**  
Email: hadi.fanaee@fe.up.pt
