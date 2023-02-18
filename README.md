# WildBlueberry-Pollination-Simulation
Abstract


A number of research is underway in the agricultural sector to better predict crop yield using machine learning algorithms. Many machine learning algorithms require large amounts of data in order to give useful results. One of the major challenges in training and experimenting with machine learning algorithms is the availability of training data in sufficient quality and quantity remains a limiting factor. In the paper, “Wild blueberry yield prediction using a combination of computer simulation and machine learning algorithms” [1], we used dataset generated by the Wild Blueberry Pollination Model,  a spatially explicit simulation model validated by field observation and experimental data collected in Maine USA during the last 30 years [2]. The blueberry yields predictive models require data that sufficiently characterize the influence of plant spatial traits, bee species composition, and weather conditions on production. In a multi-step process, we designed simulation experiments and conducted the runs on the calibrated version of the blueberry simulation model. The simulated dataset was then examined, and important features were selected to build four machine-learning-based predictive models. This simulated data provides researchers who have actual data collected from field observation and those who wants to experiment the potential of machine learning algorithms response to real data and computer simulation modelling generated data as input for crop yield prediction models.


Keywords


wild blueberry, yield, prediction, multiple linear regression, random forest, boosted decision tree, XGBoost

Specifications Table

https://github.com/sreeajay07/WildBlueberry-Pollination-Simulation/blob/main/Screenshot%202023-02-18%20at%201.50.41%20PM.png

Value of the Data
The dataset provides useful information on wild blueberry plant spatial traits, bee species composition and weather conditions. Therefore, it enables researchers to build machine learning models for early prediction of blueberry yield. 
This dataset can be essential for other researchers who have field observation data but wants to test and evaluate the performance of different machine learning algorithms by comparing use of real data against computer simulation generated data as input in crop yield prediction.  
Researchers can use this dataset to benchmark wild blueberry crop yield prediction models comparing to results already known. 
Educationalists at different level can use the dataset for training machine learning classification or regression problems.
1. Data Description
The dataset used for predictive modelling was generated by the Wild Blueberry Pollination Simulation Model, which is an open-source, spatially-explicit computer simulation program (Figure 1) that enables exploration of how various factors, including plant spatial arrangement, outcrossing and self-pollination, bee species compositions and weather conditions, in isolation and combination, affect pollination efficiency and yield of the wild blueberry agro-ecosystem. The simulation model has been validated by the field observation and experimental data collected in Maine USA and Canadian Maritimes during the last 30 years [2] and now is a useful tool for hypothesis testing and theory development for wild blueberry pollination researches.











Figure 1. A simulated wild blueberry field on Julian date 136 of the production season. The green dots are quadrats in which stems are in bud (before bloom) stage, yellow dots are quadrats in which stems are in bloom, red dots are quadrats in which flowers on stems have become fruit (after bloom). Mixed yellow (flower) and green (bud) stem show the pattern of successive waves of flowering within a clone. Red stems with different color saturation indicate the percentage of fruit set, i.e., bright red stems have higher fruit set than the dark red ones. Black area are bare spots in the field caused by herbicide applications and erosion [2].
This article presents the dataset of 777 records. The data is associated with the article [1]. A detailed description of the extracted features is shown in Table 1.
Table 1. Features and their description 


An initial investigation of the simulation derived data was conducted to determine distributional patterns described by a statistical summary (Table 2).
Table 2. Field spatial traits, bee species composition and weather variables associated with wild blueberry yield (minimum, maximum, mean, std. deviation, and correlation coefficient r) in the simulated dataset.


2. Experimental Design, Materials and Methods
2.1 Simulation experiments
For machine learning model development and analysis, the calibrated version of the simulation model was used and performed a set of simulation experiments to develop a simulated dataset. The simulation experiments aimed to characterize the influence of wild blueberry spatial arrangement, bee species composition in the field, and weather conditions on yield. Therefore, the parameters (i.e., the factors of the simulation model) used to configure the simulation experiments are three-fold (Table 3): 1) the average size of blueberry clones within a field; 2) foraging density of each bee taxon group; and 3) weather information such as temperature, precipitation and wind speed. The range of blueberry clone size has been observed from several to hundreds of square meters, but in most cases, they are smaller than 50 square meters [3]. We set the range of clone sizes between 10 and 40 square meters in the simulation to cover typical scenarios. Native bee density in a blueberry field could be very much different from that of the commercial Honeybee, so we set different ranges of density for different bee taxa (Table 3). As for weather parameters of the simulation model, we collected the high and low daily air temperature and precipitation from the Julian day of 121 to 181 between the year 2015 and 2019 of the region of Bangor, Maine of the USA from The Weather Channel (https://weather.com)  and averaged the five years data to form the weather input. This weather condition is regarded as the current (or the moderate) climate condition. We then systematically increased or decreased the corresponding daily temperature and precipitation to their 125% and 75% level to create the four climate conditions that are: Warm and Dry, Warm and Wet, Cool and Dry, Cool and Wet, respectively. Once the factors of the simulation experiments had been determined, we designed experiments and specified the number of levels of each factor for effectively sampling the model space. According to the statistics of field observations [3], we roughly calculated the levels of (i.e., the number of sampling space within) each factor, which are: 6 levels for clone size; 7 levels for Honeybee density; 10 levels for Bumblebee density; 12 levels for Andrena and Osmia bee density, respectively; and 3 levels for air temperature and precipitation, respectively.

Table 3. Parameters used to configure the simulation experiments


2.2 Preprocessing
In order to make the dataset more useful, some pre-processing tasks should be performed. The data includes 13 independent variables and in a dataset, there may be features that are not completely relevant or spurious and thus not explanatory of blueberry yield.  The contribution of these types of features is often low for predictive modelling compared to the most significant features obtained as the result of feature selection. As a result, we used Python scikit-learn library version 0.21.3 [4] for this task of pre-processing i.e. feature selection. The selected features were later applied to train and build the machine learning models.

Acknowledgments
We acknowledge funding by the National Natural Science Foundation of China (61871061) and Program of Basic Research and Frontier Technology of Chongqing Municipal Science Commission (cstc2017jcyjAX0453) to HQ.

Declaration of Competing Interest/Conflict of interest
The authors declare that they have no known competing financial interests or personal relationships which have, or could be perceived to have, influenced the work reported in this article.
References
[1]	E. Y. Obsie, H. Qu, and F. Drummond, “Wild blueberry yield prediction using a combination of computer simulation and machine learning algorithms,” Comput. Electron. Agric., 2020, doi: In Press.
[2]	H. Qu and F. Drummond, “Simulation-based modeling of wild blueberry pollination,” Comput. Electron. Agric., vol. 144, pp. 94–101, 2018.
[3]	F. A. Drummond, “Behavior of bees associated with the wild blueberry agro-ecosystem in the USA,” Int. J. Entomol. Nematol., vol. 2, no. 1, pp. 27–41, 2016.
[4]	F. Pedregosa et al., “Scikit-learn: Machine learning in Python,” J. Mach. Learn. Res., vol. 12, no. Oct, pp. 2825–2830, 2011.




