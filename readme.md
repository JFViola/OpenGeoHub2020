## Introduction

In many middle and low-income countries, air pollution monitor networks are deficient or nonexisting, but in these countries people are the most vulnerable to air pollution, with young children suffer the most. The idea is to borrow information from countries where relatively dense ground monitors are available, and integrate information from satellite measurements and geospatial predictors, to give an estimation of global air quality. The challenge lies in modelling the geospatially heterogenious relationships between predictors and pollutants, as well as integrating remote sensing measurements and predictors from different resolutions and sources. Machine learning methods, when making full use of spatial information, clearly is an auspicious shot. 

In this course, I will introduce the whole global air pollution modelling process, with a focus on introducing how different machine learning (regularized regression, ensemble trees, deep learning) can be used in spatial NO2 predictio. The deep learning is introduced in Python and others in R. I will also briefly go through the convenient features of these two languages, many developments try to combine them in one environment, which will take time to see if it is the most efficient way. I am an R user for almost 10 years and in these 3 years gradually moving some of my works to Python (I actually like it better, and I got the feeling that even the statistical community of Python is catching up).   

Deep learning is a very fast evolving and facinating fields, many strategies, architectures, concepts have been developed. You may learn in the workshop that it is a powerful representation learning tool that is a game changer in computer vision, which means also in many areas of remote sensing, particulaly in instance segmentation, localization, image maching, showing its great power in the era of big data. What about deep learning in air pollution mapping, up to now it has been a regression problem, and the number of observations (ground meausrements) are low? Is it not so useful? Too early to say, the Holly Grail in machine learning is actually unsupervised learning. I see the buergeoning data and algorithms as an unprecedented opportunity! In this course, you will discuss with me the future of machine learning, data integration in air pollution mapping (or prediction problems in general).

After this course, you will 1) become an efficient modeller (using a variety of machine learning algorithms); 2) understand/implement/use the newest algorithms in machine learning, 3) (hopefully) also be intrersted in related prediction problems.

## Methods to be learned are: 
- **Ridge**
- **Lasso**
- **Elastic Net**
- **random forest**
- **gradient boosting machine**
- **xgboost**
- **Deep Neural Networks** 
  - point-based
  - convolutional neural networks: Self-defined; recently developed 

## Scripts:

- Data Visualization 
  - **plot_RS.Rmd**: visualize the 3 remote sensing products.
  - **openaq.Rmd** : querying open openaq data using R API 

- Data exploration and tool file
  - **Geohub.Rmd**: data analysis script that includes a variety of tools for data exploration and modeling. You can explore the data and analyse modeling results, for example looking at the scatterplots, spatial correlations, partial dependence plot, importance plot. You can also see how the machine learning functions are parameterized and used for modelling, besides the deep neural networks, which is implemented in Python. 

- Cross validation, mapping, further analysis

  - **Glo_hyp_tun.Rmb**: hyperparmeter tunning for the xgboost, random forest, and gradient boosting machine, using grid search and R caret package.
  - **Glo_vali_map_compare** : the models are validated using bootstrapping (eval set to false, if you want to try it to yourself it takes about 10 minutes), the variable importance are averaged over the bootstrapped rounds. The models are used to make predictions (map) in a small region. The prediction results are further compared with mobile sensor measurements (air monitor stations on board a carrier-bike).

- Small experiements
  - **differences between ML and statistics**
  - **ensemble**: ensemble multiple machine learning models, which often could give the best results
  
- Predictor calculation
  - **predictors**: In this study, we used buffered variables -- variables aggregated over buffers of various sizes. The roads and industry variables are calcualted from OpenStreetMap. Scripts to downloading OpenStreetMap data, pre-processing, and calculate buffers are included in this folder. Please refer to the README file in the foler for more details. You can also visit our GitHub page to reproduce all the predictor variables, or calculate your own predictors. I believe this will greatly faciliate relevant research, especially studies starting from scratch. 
 
- Other folders:
  - **slides**: the slides for the plenary and workshop in the afternoon
  - **output**: some output saved from running the Geohub.Rmd
  - **predict_tiles**: functions and dataset for making predictions (mapping) in a (10km by 10km) example region.
  - **Satelite**: the remote sensing products
 
