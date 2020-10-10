# machine-learning-challenge

Background:  Over a period of nine years in deep space, the NASA Kepler space telescope has been out on a planet-hunting mission to discover hidden planets outside of our soloar system.

Objective:  Create machine learning models capable of classifying candidate exoplanets from the Kepler Exoplanet data.


Analysis:

1. The first step was to preprocess the data and get it ready for analysis.  

    * Unnecessary variables were removed from the data set.  This included "identifer" variables (such as kepid and kepoi_name) and variables without predictive value (such as the positive and negative uncertainties for each measurement).  
    * Rows with missing values were removed.
    * The SelectKBest method was performed on the remaining independent variables to determine if any were insignificant and could be removed before modeling.  Four variables were identified as insignificant and were removed:  koi_slogg, ra, dec, and koi_kepmag.
    
2.  Before modeling, the data was split into training and testing data sets and the indepdent (numeric) variables were scaled.

3.  Three different classification models were used to classify the data:  KNN (K Nearest Neighbor), SVM, and Random Forest.  For each of these three classification models, after the initial model was fit, Grid Search was used to tune the parameters and find the best fitting model.


Conclusion:

The Random Forest classification model was the most predictive of the three.  An initial model was fit using n=200 estimators.  Grid Search was performed using five different n-estimators (200, 400, 600, 800, and 1,000) and two different max features (auto and sqrt).  The best fitting model was n=800 estimators with max_features = sqrt.  This model had an accuracy of 90% compared to best KNN model (accuracy of 84%) and best SVM model (accuracy of 81%).

