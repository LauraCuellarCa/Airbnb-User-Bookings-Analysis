# Airbnb User Bookings Analysis

This project aims to predict user bookings using the Kaggle dataset "Airbnb New User Bookings". The problem posed in the competition was predicting where a user would make their first booking, which would enable Airbnb to provide more personalized content and community interactions. By utilizing various machine learning techniques, from exploratory data analysis (EDA) to feature engineering and model optimization, this project attempts to forecast user behavior and provide insights into booking trends.

## Table of Contents

- [Project Description](#project-description)
- [Dataset](#dataset)
- [Installation](#installation)
- [Usage](#usage)
- [Model Details](#model-details)
- [Evaluation Metrics](#evaluation-metrics)
- [License](#license)

## Project Description

The primary objective of this project is to predict whether a user will make their first booking and, if so, where they will do it. The dataset used is from the Kaggle "Airbnb New User Bookings" competition. The analysis involves a variety of techniques, including EDA, feature selection, model training, and optimization. Throughout this process, the model performance is evaluated using both traditional metrics and the unique competition metric provided by Airbnb.

Key steps include:
1. **Exploratory Data Analysis (EDA)** – Understanding user behavior and identifying popular travel destinations.
2. **Feature Engineering** – Converting categorical variables into numerical ones and reducing dimensionality using autoencoders.
3. **Model Selection** – Using Random Forest, XGB Classifier, and Stacking Classifier to predict user bookings.
4. **Model Evaluation** – Focusing on the Kaggle competition’s specific metric, rather than traditional metrics like accuracy and F1-score.

## Dataset

The dataset for this project is provided through Kaggle's "Airbnb New User Bookings" competition. The dataset contains various user attributes, such as gender, age, and country of origin, as well as information about whether or not a user made a booking and their first booking destination.

### How to Download the Dataset

To use this project, you’ll need to download the dataset from Kaggle. Follow the instructions below:

1. **Sign in to Kaggle**:
   If you don’t have an account, sign up [here](https://www.kaggle.com/).

2. **Generate Kaggle API Key**:
   - Go to your Kaggle account settings [here](https://www.kaggle.com/account).
   - Scroll down to the **API** section and click **Create New API Token**. This will download a `kaggle.json` file containing your API credentials.

3. **Set up the Kaggle API**:
   Place the `kaggle.json` file into the `~/.kaggle/` directory (or equivalent on your OS). This will authenticate your API requests.

4. **Download the Dataset**:
   Use the Kaggle API to download the dataset:
   ```bash
   !pip install kaggle
   !kaggle datasets download -d airbnb-recruiting-new-user-bookings
   ```

5. **Manual Download (Optional)**:
   If you prefer, you can manually download the dataset from [this Kaggle page](https://www.kaggle.com/competitions/airbnb-recruiting-new-user-bookings/data) and extract the data files into the appropriate directory on your system.

### Data Files

Once you’ve downloaded the dataset, place the extracted files in the `/kaggle/input` directory to proceed with the analysis.

## Installation

To get started with the project, clone the repository and install the required dependencies:

```bash
git clone https://github.com/your-username/airbnb-user-bookings-analysis.git
cd airbnb-user-bookings-analysis
pip install -r requirements.txt
```

## Usage

Once you have set up the repository and installed the dependencies, you can run the Jupyter notebook to start analyzing the data:

1. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

2. Open the `Airbnb_User_Bookings_Analysis.ipynb` notebook and begin exploring the dataset.

## Model Details

In this project, we utilized a combination of machine learning models to predict user bookings:

- **Random Forest**: Combines multiple decision trees to enhance performance and reduce overfitting.
- **XGB Classifier**: A gradient boosting classifier that is particularly useful for large datasets.
- **Stacking Classifier**: A logistic regression model that combines the predictions of both Random Forest and XGB Classifier to improve overall performance.

### Feature Engineering
- Categorical variables were converted to numerical values using one-hot encoding.
- Time-related columns were split into multiple integer columns.
- Missing values were handled by assigning a default value (-1) for certain columns, especially for users without a first booking date.
- Dimensionality reduction was performed using Autoencoders.

### Model Optimization
We used **ANOVA F-test** for feature selection to retain only the most relevant variables, reducing the feature count from 161 to 50. The model was optimized using hyperparameter tuning to improve prediction accuracy.

## Evaluation Metrics

Although we evaluated the model using traditional metrics like accuracy, precision, recall, and F1-score, the primary evaluation metric was the **Normalized Discounted Cumulative Gain (NDCG)**, a metric provided by Kaggle for this competition. Our final Kaggle score was approximately **0.86**, indicating a strong predictive model for user bookings.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

This README provides a comprehensive view of your project, including the methodology, dataset download instructions, and evaluation. Let me know if you’d like any more tweaks!
