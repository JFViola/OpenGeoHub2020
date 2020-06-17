## Introduction

In many middle and low-income countries, air pollution monitor networks are deficient or nonexisting, but in these countries people are the most vulnerable to air pollution, with young children suffer the most. The goal is to integrate information from ground station measurements, satellite measurements and geospatial predictors, to estimate global air quality, at a high resolution (< 100 m). Challenges are:
1. Modelling the geospatially heterogenious relationships between predictors and pollutants. 
2. Assimilating remote sensing measurements and predictors from different resolutions and sources 
3. Modelling the effects of transportation network structures (to air pollutant emission). 

Machine learning methods, when making full use of spatial information, clearly provide us an unprecedented opportunity with the burgeoning availability of data. Many atmospheric numerical modellers are impressed by the accuracy a statistical model could reach, however, global high-resolution air quality prediction is still at its infacy, the chanllenges are awaiting to be addressed.    

In this course, I will introduce the whole global air pollution modelling process, with a focus on introducing how different machine learning methods (e.g. ensemble trees, deep learning) and strategies (e.g. regularization, postprocessing) can be used in spatial NO2 prediction. The deep learning and variable predictor calculations (in particular OpenStreetMap querying and processing), are introduced in Python and others in R.  

Deep learning is a very fast evolving and facinating fields, many strategies, architectures, concepts have been developed. It is a powerful representation learning tool that is a game changer in computer vision, which means also in many areas of remote sensing, particulaly in instance segmentation, localization, image maching, showing its great power in the era of big data. Besides providing more accurate land element, what more can  deep learning algorithms bring in air pollution mapping, can it help with finding the road network-air pollution relationships?

**After this course, you will 1) learn a variety of machine learning algorithms; 2) become an efficient modeller (at least in air quality); 3) understand/implement/use the newest algorithms in machine learning and (hopefully) also be interested in challenges in global prediction problems**.

## Methods to be learned are: 
- **Model Regularization** (Ridge; Lasso; Elastic Net; XGBoost, Deep Neural Networks)
- **Random Forest**
- **Boosting** (e.g. gradient boosting machine and XGBoost)
- **Deep Neural Networks** 
  - point-based
  - convolutional neural networks: Self-defined and recently development 
- **Mixed-effect models** 

## Course Material:
### The  [R_scripts](/R_scripts/) folder 
contains 5 sub-folders that corresponds to the Introduction, statistical method, and modeling process sections of the lecture: 
 

- [Data_visualize](/R_scripts/Data_visualize/): visualizing Satellite imagery and the OpenAQ API.
  - **plot_RS.Rmd**: visualize the 3 remote sensing products.
  - **openaq.Rmd** : querying open openaq data using R API 
  - **rasters**: remote sensing products and a 1 degree by 1 degree tile of all the predictors for mapping and visual inspection

- [Introduction](/R_scripts/Introduction/)
  - **Geohub_2020.Rmd**: data analysis script that includes a variety of tools for data exploration and modeling. You can explore the data and analyse modeling results, for example looking at the scatterplots, spatial correlations, partial dependence plot, importance plot. You can also see how the machine learning functions are parameterized and used for modelling, besides the deep neural networks, which is implemented in Python. 

- [convolution_filter](/R_scripts/convolution_filter/)
  - **convolutional illustrated.Rmd**: Basic image analysis: the effect of different convolutional filters in image edge extraction, sharpening and blurring. 
 
- [modeling_process](/R_scripts/modeling_process/): the modelling process from hyperparameter optimization, cross validation, to mapping.

  - **Glo_hyp_tun.Rmd**: hyperparmeter tunning for the xgboost, random forest, and gradient boosting machine, using grid search and R caret package.
  - **Glo_crossvali.Rmd** : the models are validated using bootstrapping (eval set to false, if you want to try it to yourself it takes about 10 minutes), the variable importance are averaged over the bootstrapped rounds. 
  - **Glo_map.Rmd**: The models are used to make predictions (map) in a small region, using multiple methods for comparison.  
  - **dc.gri, dc.grd**: Geospatial predictors used for mapping.

- [other](/R_scripts/other/): Consists of small experiements to deepen the understandings of Machine learning.
  - **differences between ML and statistics**
  - **ensemble**: ensemble multiple machine learning models, which often could give the best results.

### The [Python](/Python/) folder

The predictor calculation- in particular OSM map querying and buffer calculation, and deep learning process are implemented in Python, forming the last part of the workshop. Python is used as some tools are currently only developed in Python, and most people in the deep learning community use python, contributing to (in my opinion) a faster pacing development. In this folder there is a note about how to start using conda environment for people new to python.   

This folder contains:

- [deep_learning](/Python/deep_learning/)
  two methods are implemented: point-based and convolutional based. Please go to the folder for more info. 
  
- [calc_predictors](/Python/calc_predictors/)
  In this study, we used buffered variables -- variables aggregated over buffers of various sizes. The roads and industry variables are calcualted from OpenStreetMap. Scripts to downloading OpenStreetMap data, pre-processing, and calculate buffers are included in this folder. Please refer to the README file in the foler for more details. You can also visit our GitHub page to reproduce all the predictor variables, or calculate your own predictors. I believe this will greatly faciliate relevant research, especially studies starting from scratch. 

- [Notes for installing Anaconda and editor (Jupyter or Spyder)](/Python/README.md) 

### Others

#### The [slides_notes](/slides_and_notes/) folder

the slides for the plenary and workshop in the afternoon. Software for querying and processing OpenStreetMap, and data description of the night earth light measurements.  

[Here is an example](https://lumeng0312.shinyapps.io/xgboost/?_ga=2.179522658.79817579.1592385947-986486774.1592216474) of the effects of hyperparameters on cross-validation results and prediction patterns of XGboost. 
   
