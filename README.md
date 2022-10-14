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

<h4 align="center">Application Dataframe</h4>
<p align="center">
    <img src= "https://github.com/Bropell/Neural_Network_Charity_Analysis/blob/main/Resources/application_df.png"/>
</p><br>