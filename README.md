# House Price Prediction

This dataset contains house sale prices for King County in US, which includes Seattle. It includes [houses sold between May 2014 and May 2015](https://www.kaggle.com/datasets/harlfoxem/housesalesprediction?select=kc_house_data.csv).

## Goal
Our Goal is to build Machine Learning models to predict house prices using this dataset. 

## Data 
This dataset (21623 rows) includes following informations:
* `id`. Unique for each sold.
* `date`. 
* `price`.
* `bedrooms`. Number of bedrooms.
* `bathrooms`. Number of bathrooms, where 0.5 acoounts for a room with toilet but no shower, 0.25 accounts for a room with either toilet, sink, shower or bathtub.
* `sqft_living`. Squre footage of the apartments interior living space.
* `sqft_lot`. Square footage of the land space.
* `floors`. Number of floors
* `waterfront`. Whether the apartment overlooks waterfront. 
* `view`. How good the view is (marked 0 ~ 4)
* `condition`. Conditon of the apartment. (marked 1 ~ 5)
* `grade`. Marked 1 ~ 13, where 1 ~3 falls short of building construction and design, 4 ~ 7 represents average level and 11 ~ 13 means high quality. 
* `sqft_above`. Squre footage of the apartments interior living space that is above ground level.
* `sqft_basement`. Squre footage of the apartments interior living space that is below ground level.
* `yr_built`. Year built initially.
* `yr_renovated`. Latest renovation year.
* `zipcode`. 
* `lat`. Lattitude.
* `long`. Longitude.
* `sqft_living15`. Squre footage of the apartments interior living space for the nearest 15 neighbors.
* `sqft_lot15`. Square footage of the land space for the nearest 15 neighbors.

## Data Analysis/Visualizations
First of all, let us take a look on the qualitative view of the average house prices. This includes the grade scores, conditions, views and whether that house overlooks waterfront. From the following visualizations, it basically summarizes the fact that the higher those scores, the higher the house prices, which makes sense in the reality.
<div class='tableauPlaceholder' id='viz1670502041597' style='position: relative'><noscript><a href='#'><img alt='Dashboard 2 ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ho&#47;Houseprice1&#47;Dashboard2&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='Houseprice1&#47;Dashboard2' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ho&#47;Houseprice1&#47;Dashboard2&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-GB' /><param name='filter' value='publish=yes' /></object></div>               

<script type='text/javascript'>                    var divElement = document.getElementById('viz1670502041597');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='1120px';vizElement.style.height='2187px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='1120px';vizElement.style.height='2187px';} else { vizElement.style.width='100%';vizElement.style.height='1227px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>

We should also review the average house prices given on the quantitative aspects. This includes the number of bedrooms, floors and living squarefoot in the house. It is interesting to see that houses with 0.5 floors usually have higher average prices compared to those with complete floors. This is probably becasue those houses with 0.5 floors typically has more living spaces.

Here I also noticed that there are houses with extreme numbers of bedrooms but low average prices. This will require further clean in the dataset.
<div class='tableauPlaceholder' id='viz1670502153616' style='position: relative'><noscript><a href='#'><img alt='Dashboard 1 ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ho&#47;Houseprice2_16705021433090&#47;Dashboard1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='Houseprice2_16705021433090&#47;Dashboard1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ho&#47;Houseprice2_16705021433090&#47;Dashboard1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-GB' /><param name='filter' value='publish=yes' /></object></div>                

<script type='text/javascript'>                    var divElement = document.getElementById('viz1670502153616');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='1120px';vizElement.style.height='887px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='1120px';vizElement.style.height='887px';} else { vizElement.style.width='100%';vizElement.style.height='727px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>

## Data Cleaning/Feature Engineering
First of all, the ID and date of purchases will not be included in the model as both of them might be irrelavent to the topic. Then from the last section, I have already noticed some weird numbers in bedrooms and bathrooms. So a quick search in the data frame can tell us about some interesting information about houses that:
  * there are 3 houses have at least 1 bedroom (all of them actually have only one bedroom) but no bathrooms.
  * there are 6 houses have no bedrooms but at least 1 bathrooms.
  * there are 7 houses have no bedroooms or bathrooms.
  * there are 1 house have 11 bedrooms (built in 1918) and 1 house have 33 bedrooms (built in 1947), which their prices, living squarefoot, do not match with the reality now in 2022, given the assumption that those information are correct.

As a results, I simply removed all 18 rows in the dataset as outliers. Furthermore, I create three new features that could be crucial to imporve our model in predicting the price of a house:
 * replace `yr_renovated` by a binary feature `renovated` to represent whether this house is renovated after built.
 * calculate `avg_price_per_sqft`, which represent the price per living squarefoot.
 * calculate `sqft_living_percent`, which represent the percentage (in decimal) of the living squarefoot in the total actual land space.

## ML Model Building
These are the models I will be using to search for the best fit.
* Linear regression is a good start in price-prediction problem.
* Lasso regression can be an improvement.
* Random Forest.
* XGBoost.
* Also grid search will be an option to find the best combinations of hyperparameter if necessary. 

A cross validation with 5 folds will be performed to avoid random effect in splitting the data. The cross validataion will be perform on the pipeline of sickit-learn preprocessing and ML models.

## Results
The results of these models can be review by many metrics. Here we use $R^2$ as this is a regression problem. Cross validation scoring with negative mean absolute/squared error are also checked and are consistent with the following conclusion:
* Linear regression: seems bad, there will be one fold with extremely high error (`R2` extremely close to 0), which bring down the mean of 5 cross validation scores.
* Lasso regression: stable, $R^2 = 0.9097$ after searching with best parameters.
* Random forest: $R^2 = 0.9944$ with pruing to avoid overfitting.
* XGBoost:  $R^2 = 0.9952$.

In summary, random forest and XGBoost are the two best models with high scoring in predictions of house prices using this dataset. Lasso regression is also stable and well-performed.
