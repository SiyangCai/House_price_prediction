# House Price Prediction

This dataset contains house sale prices for King County in US, which includes Seattle. It includes [houses sold between May 2014 and May 2015](https://www.kaggle.com/datasets/harlfoxem/housesalesprediction?select=kc_house_data.csv).

## Goal
Our Goal is to build Machine Learning models to predict house prices using this dataset. 

## Data 
This dataset includes following informations:
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

## Data Analysis/Cleaning
First of all, let us take a look on the qualitative view of the average house prices.
<div class='tableauPlaceholder' id='viz1670502041597' style='position: relative'><noscript><a href='#'><img alt='Dashboard 2 ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ho&#47;Houseprice1&#47;Dashboard2&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='Houseprice1&#47;Dashboard2' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ho&#47;Houseprice1&#47;Dashboard2&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-GB' /><param name='filter' value='publish=yes' /></object></div>               

<script type='text/javascript'>                    var divElement = document.getElementById('viz1670502041597');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='1120px';vizElement.style.height='2187px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='1120px';vizElement.style.height='2187px';} else { vizElement.style.width='100%';vizElement.style.height='1227px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>


We should also review the average house prices given on the quantitative aspects.
<div class='tableauPlaceholder' id='viz1670502153616' style='position: relative'><noscript><a href='#'><img alt='Dashboard 1 ' src='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ho&#47;Houseprice2_16705021433090&#47;Dashboard1&#47;1_rss.png' style='border: none' /></a></noscript><object class='tableauViz'  style='display:none;'><param name='host_url' value='https%3A%2F%2Fpublic.tableau.com%2F' /> <param name='embed_code_version' value='3' /> <param name='site_root' value='' /><param name='name' value='Houseprice2_16705021433090&#47;Dashboard1' /><param name='tabs' value='no' /><param name='toolbar' value='yes' /><param name='static_image' value='https:&#47;&#47;public.tableau.com&#47;static&#47;images&#47;Ho&#47;Houseprice2_16705021433090&#47;Dashboard1&#47;1.png' /> <param name='animate_transition' value='yes' /><param name='display_static_image' value='yes' /><param name='display_spinner' value='yes' /><param name='display_overlay' value='yes' /><param name='display_count' value='yes' /><param name='language' value='en-GB' /><param name='filter' value='publish=yes' /></object></div>                

<script type='text/javascript'>                    var divElement = document.getElementById('viz1670502153616');                    var vizElement = divElement.getElementsByTagName('object')[0];                    if ( divElement.offsetWidth > 800 ) { vizElement.style.width='1120px';vizElement.style.height='887px';} else if ( divElement.offsetWidth > 500 ) { vizElement.style.width='1120px';vizElement.style.height='887px';} else { vizElement.style.width='100%';vizElement.style.height='727px';}                     var scriptElement = document.createElement('script');                    scriptElement.src = 'https://public.tableau.com/javascripts/api/viz_v1.js';                    vizElement.parentNode.insertBefore(scriptElement, vizElement);                </script>
## Feature Engineering

## ML Model Building

## Results
