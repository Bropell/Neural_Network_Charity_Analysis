# Neural_Network_Charity_Analysis
## Project Overview
The purpose of this project is to use a deep learning neural network to create a binary classifier
that is capable of predicting whether investments will be successful. A CSV containing more than 
34,000 organizations that have received funding over the years was preprocessed and used in the 
deep learning model. Additionally, an attempt at optimizing the model was made to achieve a target 
predictive accuracy higher than 75% by adjusting different model parameters. 

## Results
### Data Preprocessing 
As with most datasets, there was some preprocessing that needed to be done in order for the data
to be suitable for a machine learning model and this dataset was no exception. Some of these 
preprocessing steps included dropping unnecessary columns and finding unique values for each
coulumn in order to determine if binning was necessary. There was some binning required for 
some of the smaller application values as well as the classifications because their unique 
values were significantly higher than the other parameters except ask_amt. Categorical values
were fit and transformed using the OneHotEncoder instance and then merged into the original 
DataFrame so original values could be dropped. The data was split into the feature and target
arrays as well as training and testing datasets. Finally, the StandardScaler instances were 
created, fit and scaled so the data was ready to be passed into the model. Supporting images 
are displayed below to answer some questions.<br>

<p align="center">
    <img src= "https://github.com/Bropell/Neural_Network_Charity_Analysis/blob/main/Resources/Targets%20and%20Features.png"/>
</p><br>

- What variable(s) are considered the target(s) for your model?<br>

The target variable of a dataset is the feature of a dataset about which you want to gain a deeper
understanding. In this case, the target is the "IS_SUCCESSFUL" column since that is the feature of
interest and the model will aim to gain an understanding of this based on the other features. 

- What variable(s) are considered to be the features for your model?<br>

A feature is an individual measurable property or characteristic of a phenomenon. In this case, the 
features are all the parameters remaining after unnecessary columns were dropped aside from the target
variable. An image of the features is shown below keeping in mind that the "IS_SUCCESSFUL" column is 
the target. Additionally, an image of the final merged DataFrame is also shown to demonstrate how the
catagorical features are being passed into the model.<br>

<p align="center">
    <img src= "https://github.com/Bropell/Neural_Network_Charity_Analysis/blob/main/Resources/Features.png"/>
</p><br>

<h4 align="center">Merged Application Dataframe</h4>
<p align="center">
    <img src= "https://github.com/Bropell/Neural_Network_Charity_Analysis/blob/main/Resources/application_df.png"/>
</p><br>

- What variable(s) are neither targets nor features, and should be removed from the input data?<br>

As mentioned earlier in the preprocessing section, there were some columns that needed to be dropped in order
for the model to function properly. Both the "EIN" and "NAME" columns in particular needed to be dropped because
they only contain identifiers for applications which will not benefit the machine learning model. An image of the
original DataFrame before those columns were dropped is shown below.<br>

<h4 align="center">Original Application Dataframe</h4>
<p align="center">
    <img src= "https://github.com/Bropell/Neural_Network_Charity_Analysis/blob/main/Resources/application_df_original.png"/>
</p><br>

### Compiling, Training and Evaluating the Model

<h4 align="center">Original Model</h4>
<p align="center">
    <img src= "https://github.com/Bropell/Neural_Network_Charity_Analysis/blob/main/Resources/Original%20Model.png"/>
</p><br>

- How many neurons, layers, and activation functions did you select for your neural network model, and why?<br>

As seen in the image above, there are two hidden layers and one outer layer in the original model. The first hidden
layer has 80 units, the second hidden layer has 30 units and the outer layer has one. Both hidden layers use the 
"Relu" activation function while the outer layer uses the "sigmoid" activation function. The Relu function was used
here because it is easier to train and often achieves better performance than other functions.<br>

- Were you able to achieve the target model performance?<br>

Unfortunately, during the optimization phase of this challenge a target model performance of greater than 75% was 
not able to be reached. Three attempts at optimization were made with the highest target model performance being
73.2%.<br>

- What steps did you take to try and increase model performance?<br>

<h4 align="center">Optimization 1 (Add Third Hidden Layer)</h4>
<p align="center">
    <img src= "https://github.com/Bropell/Neural_Network_Charity_Analysis/blob/main/Resources/Optimization1_three_hidden_layers.png"/>
</p><br>

The first attempt at optimizing the model to achieve a target performance greater than 75% was to add a third hidden 
layer. Hidden layers are required if the data must be separated non-linearly and in this case, the features must be
separated in this way. This modification was only slightly better than the original model with a target performance 
of 73.2% versus the original 73.0%.<br> 

<h4 align="center">Optimization 2 (Change Activation Functions)</h4>
<p align="center">
    <img src= "https://github.com/Bropell/Neural_Network_Charity_Analysis/blob/main/Resources/Optimization2_change_activation_functions.png"/>
</p><br>

The second attempt at optimizing the model was to change the activation functions for the hidden layers from "Relu" to
"sigmoid". The idea here was that sigmoid functions work better when there are fewer layers and tend to bias very large 
values to a value of 1 and very small values to 0. In this regard, the outcome was expected to change if any of these 
extreme values existed which was not the case. This modification produced a poorer performance than the original model with 
a target value of 73.1%.<br>

<h4 align="center">Optimization 3 (Added Perceptrons in Three Hidden Layers)</h4>
<p align="center">
    <img src= "https://github.com/Bropell/Neural_Network_Charity_Analysis/blob/main/Resources/Optimization3_add_perceptrons.png"/>
</p><br>

The last attempt at optimization was to return to using three hidden layers but to double the amount of perceptrons in 
each hidden layer. The idea here is that there are more units to shoulder the load and learning should be faster at the
beginning. Even though the target performance started the highest in this model, as more epochs passed there was little 
to be gained in terms of target performance. This modification produced the worst target performance with a value of 72.9%.

## Summary