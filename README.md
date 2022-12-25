# Home Sale Price Prediction Model & Shiny App
#### Primary objective: show model deployment in Shiny app

#### Home sale price predictive model and deployment in R shiny dashboard.

The training dataset from House Prices: Advanced Regression Techniques Kaggle competition was used for this project and is referred to as `home_price_prediction_app/house_prices_df.csv` in this repository.

For more information on the Kaggle competition, go here: https://www.kaggle.com/c/house-prices-advanced-regression-techniques

## Requirements

### Libraries
- shiny
-	shinyWidgets
-	scales
-	grid
-	gridExtra
-	tidyverse
-	skimr
-	janitor
-	tidymodels
-	vip
-	xgboost
-	openxlsx

### From the Repository

Run `home_price_prediction_app/app.R` to deploy model predictions within the shiny app, changing working directory to your desired local directory where you have saved repository files. All files needed to run the shiny app are in the `home_price_prediction_app` folder. Descriptions of those files within the folder, model script and shiny app script and data, are below:

**Final Model Script**
- `home_price_prediction_app/model_main.R`

In this script, the data is imported, preprocessed, and the model fitted using tidymodels package. The fitted model parameters and hyperparameters were finalized in this script after several model iterations. Model iterations were set up in `model_iteration.R`, and the performance of each model is shown here in `model_output_files/xgboostmodels_performances.csv`. The parameters of the best model were saved in `model_output_files/xgboostfinal_model_parameters.csv`. The final model is saved as an object, `model_output_files/final_model.rds`. 

The `model_out_files/model_output` shows final model output, showing the test and training dataframe with predictions along with overall rmse for the training and test datasets. A visualization of the test data error is in `model_output_files/error_plot.png`, showing error by decile. 

Predictors used in the model were pared down to top 10 most important variables. To see visual representation of top 10 most important variables' influence on the model, go here: `model_output_files/imp_var_plot.png`. Description of all data variables, including those inputted in the model before the model was finalized, are here: `data_description.txt`.

**Shiny App UI and Server**
- `home_price_prediction_app/app.R`

The app takes in user inputs, the model's predictors. The model is used to predict the home's sale price from these user inputs. 

**Data File**
`home_price_prediction_app/house_prices_df.csv`

The training dataset from House Prices: Advanced Regression Techniques Kaggle competition was used for this project. Description of all data variables, including those inputted in the model before model was finalized, are here: `data_description.txt`. 
