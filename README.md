# GLOBAL-EARTHQUAKE-ANALYSIS
A machine learning–ready dataset of 782 major global earthquakes (2001–2022), containing seismic features and tsunami indicators for earthquake analysis and tsunami risk prediction.

## 📊 Dataset Description

- Records: 782 global earthquakes

- Time Period: 2001 – 2022

- Target Variable: tsunami
  - 1 → Tsunami occurred
  -  0 → No tsunami

 | Feature   | Description                    |
| --------- | ------------------------------ |
| magnitude | Earthquake magnitude           |
| cdi       | Community Determined Intensity |
| mmi       | Modified Mercalli Intensity    |
| sig       | Significance score             |
| nst       | Number of seismic stations     |
| dmin      | Minimum distance to station    |
| gap       | Azimuthal gap                  |
| depth     | Earthquake depth (km)          |
| latitude  | Latitude                       |
| longitude | Longitude                      |
| Year      | Event year                     |
| Month     | Event month                    |

**✔ No missing values**
**✔ No duplicate records**

# 🌊 **Tsunami Distribution**
- Non-Tsunami Events: 478 (61.1%)
- Tsunami Events: 304 (38.9%)
<img width="552" height="470" alt="image" src="https://github.com/user-attachments/assets/0cd202a4-07d7-42f7-8547-4cabed37c40b" />


# 📉 **Major Earthquake Analysis (Magnitude ≥ 8.0)**
- Total major events: 28
- Tsunami-causing major events: 10

## Visualizations

- 📈 Magnitude vs Index plot with threshold line at M ≥ 8
- 🌍 World map showing:
  - All major earthquakes (M ≥ 8)
  - Major earthquakes that caused tsunamis
<img width="1163" height="621" alt="image" src="https://github.com/user-attachments/assets/32326feb-cef8-4329-ac40-5dd6227ff7fa" />

- 🌊 Global tsunami occurrence map
<img width="1163" height="611" alt="image" src="https://github.com/user-attachments/assets/66b740dd-f17f-4d1c-bcd3-945717397ea6" />


## 📊 Exploratory Data Analysis (EDA)
1️⃣ **Distribution Analysis**
- Gap Distribution: Right-skewed histogram
- Magnitude & Depth Trends: Line and box plots
<img width="582" height="435" alt="image" src="https://github.com/user-attachments/assets/d97e0453-8766-4af5-80bf-bd1151f29547" />

2️⃣ **Correlation Analysis**
- 🔥 Heatmap showing correlations between seismic features
- Helps identify strong predictors for tsunami occurrence

<img width="1155" height="434" alt="image" src="https://github.com/user-attachments/assets/b9d2ac09-6ed0-4077-a4df-12ba88263c9b" />


3️⃣ **Outlier Detection**
- 📦 Boxplots for all numerical features
<img width="1227" height="489" alt="image" src="https://github.com/user-attachments/assets/7878255d-5215-47d3-8c4a-4850ce103d22" />

- IQR-based detection for:
  - ```sig```
  - ```depth```
  <img width="580" height="416" alt="image" src="https://github.com/user-attachments/assets/b20fc4f4-dd85-46b2-8222-ad12e6223e0e" />

  <img width="571" height="416" alt="image" src="https://github.com/user-attachments/assets/e628e4d3-f9f8-4630-b672-65cff1ff3788" />


- Outliers removed to create a clean dataset for modeling

## 🧹 Data Preprocessing
- Outlier removal using IQR method
- Final dataset used for modeling: cleaned and normalized
- Features (```X```) and target (```y```) separated
- Train-Test Split: 80% / 20%

## 🤖 Machine Learning Models
🔹 **K-Nearest Neighbors (KNN)**

- Hyperparameter tuning:
  - k = 1 to 30
  - Best k chosen using 5-fold cross-validated F1-Macro score
  <img width="576" height="432" alt="image" src="https://github.com/user-attachments/assets/d7b9beeb-44a5-48f7-82ab-4d00ba6acdb5" />


- Optimal k: 13

**Performance**
- Train Accuracy: ~89.8%
- Test Accuracy: ~89.6%
- Strong balance between precision and recall

## 📈 Actual vs Predicted plot clearly shows prediction alignment.
<img width="846" height="393" alt="image" src="https://github.com/user-attachments/assets/9d911ea3-e918-43ae-9b08-6d019dd8e825" />

🔹 **Random Forest Classifier**
- Estimators: 500
- Max Depth: 3

**Performance**
- Train Accuracy: ~88.2%
- Test Accuracy: ~89.6%
- High recall for tsunami detection

## 📊 Prediction comparison plots included.
<img width="846" height="393" alt="image" src="https://github.com/user-attachments/assets/826040ab-f3a8-4149-a7c0-81e4778dfeb0" />

# 🔁 Cross-Validation
- 10-Fold Cross Validation (KNN)
- Average Accuracy: ~88.7%
- Confirms model stability and robustness


## 📌 Key Insights
- High-magnitude earthquakes alone do not always cause tsunamis
- Geographic location and depth play a critical role
- Machine learning models can reliably classify tsunami risk
- KNN and Random Forest performed comparably well

## 🛠 Tech Stack
- Python
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-Learn
- GeoPandas

## 👨‍💻 Author

**Roshan Kumar**
*B.Sc. Computer Science & Data Analytics
Indian Institute of Technology Patna*
📧 Email: rk1861303@gmail.com
