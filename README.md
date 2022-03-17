# Tanzania Well Functionality: A Management Perspective
  By: Samira Chatrathi and Brian Reynolds


![images-1](https://user-images.githubusercontent.com/97462844/157954587-923cc500-8c4a-4de2-8cf3-53bea951f7ae.jpg)


# Overview
  In this project we take Tanzanian Well Data from the DrivenData competition to build a classification model to predict which wells are functional, non functional, and functional and need repair. 

# Business Understanding/Stakeholder
Tanzania has struggled with finding a solution to their water crisis for years. Not only is the affordability of clean water an issue, but the infrastructure and maintenance for water has also proven to be a consistent problem for Tanzania. As a means of supporting Tanzania's sustainable development, this ongoing issue needs to be fundamentally reevaluated. Our stakeholder is Water.org, a non-government organization that is looking to implement a vast manageable amount of water pumps within the country. Before deploying teams into Tanzania blindly, they want to see how they can optimize their time and resources to effectively predict whether a water pump is functional, non existent, or just broken and needs repair. Not only is Water.org focusing on fixing non functional wells themselves, but they are also focusing on prioritizing efficiency and optimizing long term scalability.

# Data
 The dataset includes information on 59,400 wells, each of which has 41 different features. We also implemented spacial data to see how certain physical characteristics could better support our model overall. In our EDA, we were able to see that 46% of the total wells in Tanzania were either non-functional, or broken and in need of repair. We broke up our data into two columns to further understand our analysis. We handled missing values and used SMOTE to address class imbalance within our modeling stage. Our features were separated into Physical and Politcal. This technique helped us understand where actionable insights can be associated with our features. 


# Modeling
After using our dummy classifier model, we were able to implement a decision tree where we could find the features with the highest level of importance. From our decision tree of political characteristics, payment, permit, region and source had the highest feature importance in our model. Region, specifically, helped us see which areas had high concentrations of probability of finding a functioning well vs. finding a broken well or a well that is functional and needs repair. While our simple Logisitc Regression with the political characteristics of importance gave us a precision level of 57%, so we knew we needed to make iterations.


<img width="620" alt="Screen Shot 2022-03-13 at 2 47 20 PM" src="https://user-images.githubusercontent.com/97462844/158074563-16ed9caf-26f5-4440-8a14-197a43c94cd6.png">


We then implemented a KNN model. We wanted to implement a form of lazy learning, where predictions are deferred until classifcation. Since we have domain knowledge associated with our target, we believe this would be a beneficial form of black box modeling. We also found that this allowed us to implement hyperparamter tuning, allowing us to make iterations to our paramters without changing the base features we wanted to study. This was our model with highest level of precision at 61%.

![image (2)](https://user-images.githubusercontent.com/97462844/158074528-fc1c7131-4516-43af-aeb7-659224f46a40.png)
# Evaluation

We implemented the Precision metric as it encompasses our False Positive, which in this case helps us prioritize wells that are predicted to be broken even when they are not. The precision metric helps us overcompensate for that possibility, so that is why we found it as an important metric. In terms of actionable insights, we found from our modeling that our political characteristics were encompassed the most within our feature selection. With that in mind, we believe the management of these political features should be the forefront moving forward.
  1. Water.org should help consolidate water management schemes for region, so that there isn't variation and overall consistency in management quality throughout the country.
  2. Water.org should also bridge the gap between Private, Public, and Government Involvement, so that all parties can work together in order to prioritize efficient management and long term scalability of productive techniques. 
  3. Water.org should also consider Water Transportation Systems. The wells that were in need of repair or were non-functional were found hubbed together in certain regions, water transportation systems can combat this issue for the benefit of the greater public and as a backup system


# Conclusion

In this notebook we were able to conduct exploratory data analysis to derive our most productive model. We gathered data from the DrivenData competition and intially began with a terenary model, having our target consist of functional, functional needs repair, and non-functional. We implemented the Precision metric as it encompasses our False Positive, which in this case helps us prioritize wells that are predicted to be broken even when they are not. The precision metric helps us overcompensate for that possibility. Once we began modeling, we began with a dummy classifier before moving to a Decision Tree that allowed us to see which features of our model would be the most productive. From our tree, we found that permit, region, payment, and source were the features with the highest level of importance. We then moved on to the a Simple Logistic regression to see how these feautures would preform, leading us to a 57% precision. In our K-nearest neighbors model,however, we binned functional and needs repair class into non-functional, used SMOTE to address class imbalance, tuned our hyperparamters, and ultimately reached a precision level of 61.6%. We managed a highest precision of 69% by consolidating our target to a binary 'Functional' or 'Needs service'.






