# 🌍 Global Obesity & Malnutrition Analysis

This project explores global trends in adult **obesity (BMI ≥ 30)** and **malnutrition (BMI < 18.5)** for adults and obesity **BMI-PLUS2C** and malnutrition **MINUS 2C** for child/adolescents using WHO datasets. The analysis includes feature engineering, regional and temporal comparisons, level classifications, and visualizations across gender, age, and geography.

---

## 📂 Dataset Overview

- **Source**:
  
      For Obesity:
            1.	https://ghoapi.azureedge.net/api/NCD_BMI_30C – Obesity among adults (BMI ≥ 30)
  
            2.	https://ghoapi.azureedge.net/api/NCD_BMI_PLUS2C – Obesity/Overweight among children 

      For Malnutrition:
            3.	https://ghoapi.azureedge.net/api/NCD_BMI_18C – Underweight in adults (BMI < 18.5)
  
            4.	https://ghoapi.azureedge.net/api/NCD_BMI_MINUS2C – Thinness in children
  
- **Fearture Engineering**: Feature Engineering is done and have concatenated the 4 datasets into 2 datasets df_obesity,df_malnutrition
- **Rows**: 27,720 in each
- **Granularity**: Country × Year × Gender × Age group

Two separate datasets were analyzed:
1. **df_obesity**: Obesity prevalence (crude estimates)
2. **df_malnutrition**: Underweight prevalence (crude estimates)


---

## 📊 Feature Engineered Columns

### 🔵 `df_obesity` Columns

| Column Name     | Type       | Description                                                                 |
|-----------------|------------|-----------------------------------------------------------------------------|
| `Year`          | Continuous | Year of data collection                                                     |
| `Gender`        | Categorical| Gender group (`Male`, `Female`, `Both`)                                     |
| `Mean_Estimate` | Continuous | Crude % estimate of population                                              |
| `LowerBound`    | Continuous | Lower bound of confidence interval                                          |
| `UpperBound`    | Continuous | Upper bound of confidence interval                                          |
| `Region`        | Categorical| WHO-defined world region                                                    |
| `Country`       | Categorical| Country name                                                                |
| `Age_Group`     | Categorical| adult,child                                                                 |
| `obesity_level` | Categorical| (`Low`, `Moderate`, `High`) based on `Mean_Estimate`                        |
| `CI_Width`      | Continuous | Width of confidence interval (`UpperBound - LowerBound`)                    |

---

### 🟢 `df_malnutrition` Columns

| Column Name         | Type       | Description                                                                 |
|---------------------|------------|-----------------------------------------------------------------------------|
| `Year`              | Continuous | Year of data collection                                                     |
| `Gender`            | Categorical| Gender group (`Male`, `Female`, `Both`)                                     |
| `Mean_Estimate`     | Continuous | Crude % estimate of population                                              |
| `LowerBound`        | Continuous | Lower bound of confidence interval                                          |
| `UpperBound`        | Continuous | Upper bound of confidence interval                                          |
| `Region`            | Categorical| WHO-defined world region                                                    |
| `Country`           | Categorical| Country name                                                                |
| `Age_Group`         | Categorical| adult,child                                                                 |
| `malnutrition_level`| Categorical| Derived label (`Low`, `Moderate`, `High`) based on `Mean_Estimate`          |
| `CI_Width`          | Continuous | Width of confidence interval (`UpperBound - LowerBound`)                    |

---

## 🛠️ Tools & Technologies Used

| Tool         | Purpose                                    |
|--------------|--------------------------------------------|
| **Python**   | Data cleaning, feature engineering         |
| **MySQL**    | Structured querying and storage            |
| **Plotly**   | Interactive data visualization (maps, bars)|
| **Power BI** | Dashboard and executive-level reporting    |
| **pandas**   | DataFrame manipulation                     |
| **Seaborn**  | Statistical plots (optional)               |

---

## 🚀 Potential Use Cases

- **Country-level health analysis** over time (e.g., India from 2000–2022)
- **Gender disparities** in obesity and malnutrition
- **Obesity vs Malnutrition paradox** in developing nations
- **Public policy planning** using regional BMI statistics
- **Dashboards for WHO / public health agencies**
- **ML classification**: Predict BMI category level from year, region, gender

---

## 🔮 Future Directions

- 📈 **Model BMI category** using ML models like Decision Trees or XGBoost  
- 🧩 **Combine obesity and malnutrition datasets** into a unified panel  
- 🗺️ **Interactive choropleth maps** using Plotly or Folium  
- 📊 **Add per capita income or urbanization features** from external sources  
- 🤖 **Deploy Streamlit dashboard** for real-time data exploration  
- 📝 **Build a SQL warehouse** for large-scale country-year comparisons  

---



