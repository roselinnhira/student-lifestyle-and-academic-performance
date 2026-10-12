# Student Lifestyle and Academic Performance Analysis

## Project Overview
This project explores how daily student habits—such as study hours, sleep duration, screen time, and stress levels—impact academic performance (**CGPA**) and class attendance (**Attendance Percentage**). Using a dataset of 1,000 students from Kaggle, I built an end-to-end analytical pipeline in **R** combining exploratory data analysis, multivariate modeling, unsupervised learning, and classification.

---

## Tech Stack & R Packages
* **Language:** R
* **Data Manipulation:** `dplyr`, `tidyverse`
* **Visualization:** `ggplot2`, `corrplot`, `factoextra`
* **Machine Learning / Modeling:** `stats` (Linear/Logistic Regression), `kmeans`, `class` (KNN)

---

## Methodology & Key Findings

### 1. Correlation Analysis & PCA
* **Study Hours (0.51)** and **Sleep Hours (0.62)** showed the strongest positive linear relationship with CGPA.
* **Stress Level (-0.17)** showed a negative correlation, confirming high stress pulls academic performance down.
* **Principal Component Analysis (PCA)** grouped performance drivers (Study, Sleep, Internal Marks) opposite to Stress, highlighting distinct balance vs. burnout axes across student profiles.

### 2. CGPA Prediction (Multiple Linear Regression)
* **Model Performance:** Adjusted $R^2 = 0.72$ (explaining ~72% of variance in CGPA).
* **Key Factors:** 
  * +0.60 CGPA increase per additional hour of study daily ($p < 0.001$).
  * +0.19 CGPA increase per additional hour of sleep daily ($p < 0.001$).
  * -0.29 CGPA decrease per unit increase in stress level ($p < 0.001$).

### 3. Student Segmentation (K-Means Clustering)
Using the Elbow Method ($k=3$), students were grouped into three clear behavioral tribes:
1. **The Academic Weapons:** High study hours (~4.8 hrs), high sleep (~7.6 hrs), low stress $\rightarrow$ **Highest CGPA (8.28)**.
2. **The Burnouts:** High study hours (~4.7 hrs), low sleep (~5.5 hrs), high stress $\rightarrow$ **Lower CGPA (6.89)**.
3. **The Chillers:** Low study hours (~2.5 hrs), moderate sleep (~6.5 hrs), low stress $\rightarrow$ **Lowest CGPA (6.78)**.

### 4. Attendance Classification (Logistic Regression vs. KNN)
* **Logistic Regression:** Achieved **83.8% accuracy** predicting high vs. low attendance ($\ge 80\%$). Study hours proved to be the primary driver of attendance ($p < 0.001$).
* **K-Nearest Neighbors ($k=3$):** Achieved **77.5% accuracy**, demonstrating that a linear decision boundary provides superior classification for this behavioral pattern.

---

##  How to Run

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/YOUR_USERNAME/student-lifestyle-and-academic-performance.git](https://github.com/YOUR_USERNAME/student-lifestyle-and-academic-performance.git)
   cd student-lifestyle-and-academic-performance
   ```

2. **Install required packages in R:**
   ```R
   install.packages(c("dplyr", "corrplot", "factoextra", "tidyverse", "class"))
   ```

3. **Run the script:**
   Open `scripts/lifestyle_analysis.R` in RStudio and execute the pipeline.
