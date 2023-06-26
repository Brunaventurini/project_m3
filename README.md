# Machine Learning Competition: Diamond Price Prediction 🏆

Welcome to my repository for the Machine Learning Competition on diamond price prediction! In this competition, the goal is to build a model that accurately predicts the price of diamonds based on various features.

## Dataset Description 📊

The dataset used in this competition consists of information about diamonds, including their dimensions, transactional details, properties, cut, color, clarity, and city. The target variable is the price of the diamonds.

## Approach and Code 🚀

To solve this problem, I have implemented the following steps:

1. Data Retrieval:
   - The dataset is stored in a SQLite database file called `diamonds_train.db`.
   - I used the `sqlite3` library to connect to the database and fetch the required tables.

2. Data Preprocessing:
   - I merged the relevant tables based on the appropriate IDs to create a consolidated dataset.
   - I handled missing values by dropping the corresponding rows after converting non-numeric columns to numeric using `pd.to_numeric`.
   - Categorical variables (cut, color, clarity, city) were encoded using `OrdinalEncoder` from scikit-learn, and numerical features (carat, x, y, z, depth, table) were standardized using `StandardScaler`.

3. Model Building and Evaluation:
   - I split the preprocessed dataset into training and testing sets using `train_test_split` from scikit-learn.
   - I trained a `RandomForestRegressor` model to predict diamond prices.
   - Initially, the model achieved an RMSE of 583.50294.
   - To improve the performance, I performed feature selection using `SelectKBest` with the `f_regression` score function.
   - I then utilized `RandomizedSearchCV` to tune the hyperparameters of the `RandomForestRegressor` model.
   - The best model achieved an improved RMSE of 590.97399.

4. Further Improvement:
   - To further reduce the RMSE, I recommend trying additional feature engineering techniques, exploring different regression models, and fine-tuning hyperparameters.
   - Outlier handling, ensemble techniques, and careful data preprocessing can also contribute to better model performance.

