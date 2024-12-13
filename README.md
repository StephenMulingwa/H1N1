# Predicting H1N1 Vaccine Uptake Using Machine Learning Models

## Introduction
This project focuses on predicting the likelihood of individuals receiving the H1N1 flu vaccine using data collected from the National 2009 H1N1 Flu Survey. The survey includes various demographic, behavioral, and health-related features such as age, education, employment status, and health concerns that may influence vaccination decisions. Given the public health importance of vaccination in preventing the spread of infectious diseases, understanding the factors that drive vaccine uptake is critical. The project aims to build a machine-learning model that leverages these features to predict whether individuals will likely receive the H1N1 vaccine. This predictive model can help guide public health strategies and improve vaccination outreach efforts, especially during future pandemics.

## Notebook Structure
1. Business Understanding
2. Importing Libraries
3. Data Staging
4. Data Understanding
5. Data Preparation
6. Explanatory Data Analysis
7. Data Preprocessing
8. Modelling

## Business Understanding
The primary goal of this project is to support public health efforts by understanding the factors influencing vaccination uptake during the 2009 H1N1 influenza pandemic. By analyzing data from the National 2009 H1N1 Flu Survey, the project aims to identify key demographic, behavioral, and attitudinal predictors of vaccination. This understanding is crucial for informing future vaccination campaigns, especially for addressing hesitancy and improving outreach strategies. Stakeholders, such as public health policymakers, healthcare organizations, and vaccination campaign planners, can use these insights to design targeted interventions that increase vaccine acceptance and coverage, ultimately reducing the spread of infectious diseases and safeguarding public health

### Project Overview
The objective of this project is to predict whether individuals received the H1N1 flu vaccine using data from the National 2009 H1N1 Flu Survey. The dataset includes a wide range of variables, such as demographic details, behavioral patterns, health conditions, and opinions on vaccine efficacy, which may influence the decision to get vaccinated. By analyzing these factors, the project aims to develop a machine learning model that can predict vaccine uptake, focusing on understanding the key drivers behind this decision. This model will be built using classification algorithms, and the performance will be evaluated to determine the most significant predictors. The insights gained from this project can inform future public health campaigns, targeting those less likely to get vaccinated and improving vaccination rates in communities.
### Problem Statement
During the 2009 H1N1 influenza pandemic, significant challenges arose in achieving widespread vaccine uptake, despite the availability of an effective vaccine. Understanding why some individuals chose to receive the vaccine while others did not is a critical problem for public health, as similar barriers persist in contemporary vaccination efforts, such as those for COVID-19. This project seeks to address the problem of predicting vaccination behavior based on individual characteristics, including demographics, health behaviors, and attitudes toward vaccination. By identifying the factors most strongly associated with vaccine uptake, public health authorities can better tailor communication strategies and interventions to address vaccine hesitancy and improve immunization rates in future health crises.

### Objectives
1. To predict whether individuals received the H1N1 or seasonal flu vaccine.
2. To identify key factors influencing vaccination decisions.
3. To provide insights for public health vaccination campaigns.
4. To evaluate the performance of the predictive model using appropriate metrics.
5. To inform strategies for improving vaccine coverage and addressing hesitancy.

### Research Questions
1. What demographic, behavioral, and attitudinal factors are most strongly associated with receiving the H1N1 or seasonal flu vaccine?
2. Can a predictive model accurately classify individuals based on their likelihood of vaccination?
3. How do perceptions of vaccine safety and efficacy influence vaccination decisions?
4. Are certain population groups more likely to decline vaccination, and why?
5. How can insights from the 2009 H1N1 vaccination data inform future public health campaigns?

## Data Understanding
The dataset for this project is sourced from the National 2009 H1N1 Flu Survey, conducted during the H1N1 influenza pandemic. It contains information on individuals' demographic characteristics, health behaviors, and attitudes toward vaccines, along with their self-reported vaccination status for the H1N1 and seasonal flu vaccines. The dataset includes both categorical and numerical features, with variables such as age, income, education, perceptions of vaccine safety, and healthcare access. Initial exploration reveals potential data quality issues, including missing values and imbalanced target classes, which will require preprocessing and careful handling. By analyzing the properties and relevance of these features, the project aims to assess how well the data can support the development of a predictive model to address the problem of vaccine hesitancy and improve public health strategies.

## Data Analysis
The data analysis reveals key insights into the factors influencing H1N1 vaccine uptake, with a notable class imbalance in the target variable, where 78.3% of individuals did not take the vaccine. Correlation analysis showed significant relationships between certain variables, such as behavioral_large_gatherings with behavioral_outside_home, and doctor recommendations with vaccine uptake. Additionally, variables like perceived risk and doctor recommendations were found to strongly influence vaccine uptake, as shown by visualizations where higher perceived risk levels and doctor recommendations correlated with increased vaccine uptake. The analysis also highlighted the potential for multicollinearity among some features, though the low-to-moderate correlation between most independent variables ensured minimal multicollinearity, which is beneficial for building reliable predictive models. The class imbalance and correlations found in the data informed the modeling process, where different algorithms were tested, with logistic regression proving to be the best performer.

## Data Visualizations
### Distribution of H1N1 Vaccine Uptake

![image](https://github.com/user-attachments/assets/0c43ebd2-f3f0-48b9-9ca4-3949a9a007e5)

The target variable H1N1 Vaccine has a class imbalance with with class No being the highest at 78.3%

### H1N1 Vaccine Uptake vs. Perceived Risk

![image](https://github.com/user-attachments/assets/4aace8d4-283b-4833-a899-f5a4b0e0ffac)

The bar chart illustrates the relationship between the perceived risk of H1N1 (on a scale of 1 to 5) and vaccine uptake. It shows that higher perceived risk (levels 4 and 5) correlates with increased vaccine uptake, whereas lower perceived risk (levels 1 and 2) is associated with significantly fewer people choosing to vaccinate.

### H1N1 Vaccine Uptake vs. Doctor Recommendation

![image](https://github.com/user-attachments/assets/fc0f0f04-0760-493e-9880-a0d76023a5fe)

The bar chart highlights the influence of doctor recommendations on H1N1 vaccine uptake. Individuals who received a doctor’s recommendation (value 1) showed a significantly higher proportion of vaccine uptake than those who did not (value 0), where most chose not to vaccinate.

### Model Performance 
I built 4 models: the first was the baseline model, followed by logistic regression, decision tree, and random forest. The logistic regression model had the best performance, achieving a test accuracy of 0.8722 with a precision of 0.89, recall of 0.86, and an F1-score of 0.87 for class 1 (diabetes) and precision of 0.86, recall of 0.89, and an F1-score of 0.87 for class 0 (non-diabetes). The confusion matrix for logistic regression showed 3055 true negatives, 382 false positives, 497 false negatives, and 2942 true positives.
The random forest model, despite having the highest training accuracy of 0.9712, showed a significant drop in test accuracy to 0.8266, with precision of 0.77, recall of 0.94, and an F1-score of 0.84 for class 1, and precision of 0.92, recall of 0.71, and an F1-score of 0.80 for class 0. The confusion matrix for random forest showed 2444 true negatives, 993 false positives, 199 false negatives, and 3240 true positives, indicating potential overfitting.
The decision tree model had a test accuracy of 0.8040, with the precision of 0.81, recall of 0.80, an F1-score of 0.80 for class 1, a precision of 0.80, recall of 0.81, and an F1-score of 0.81 for class 0. The confusion matrix for the decision tree showed 2789 true negatives, 648 false positives, 700 false negatives, and 2739 true positives. Overall, the logistic regression model outperformed the others in terms of both accuracy and balance in precision, recall, and F1-score.

#### Logistic Model

![image](https://github.com/user-attachments/assets/dfcb3e84-d84b-4bec-88ec-a02a313d95e3)

The confusion matrix evaluates the performance of the logistic regression model on test data. It shows that the model correctly classified 3055 true negatives (class 0) and 2942 true positives (class 1), achieving high accuracy for both classes. However, there are 382 false positives and 497 false negatives, indicating some misclassifications that could be improved with further model optimization or additional features.

![image](https://github.com/user-attachments/assets/d917e411-a6d5-416f-a24e-aacd85674a59)

The logistic Model is the best-performing model since it has the highest area under the curve of 0.94

## Conclusion
The H1N1 vaccine uptake dataset analysis revealed critical factors influencing vaccine adoption, such as perceived risk, doctor recommendations, and behavioral factors. Despite the class imbalance in the data, careful preprocessing and model selection, including the use of logistic regression, produced a highly accurate and balanced model. The findings suggest that increasing perceived risk and encouraging doctor recommendations could be effective strategies to boost vaccine uptake. While the logistic regression model provided the best performance, further improvements could be made through feature engineering or exploring more advanced models.

## Recommendations
1. Target education campaigns to raise awareness about the perceived risk of H1N1, especially for those with lower risk perception.
2. Encourage doctor recommendations for H1N1 vaccination to increase uptake, as individuals who received a doctor's recommendation showed significantly higher vaccine adoption.
3. Monitor and manage behavioral factors, such as participation in large gatherings or time spent outside the home, as these were correlated with vaccine uptake.

## References

Slides Presentation Link: [Presentation.pdf](https://docs.google.com/presentation/d/1cqmISybbRLDcvXncI4ppHu_IW3QOAFD5tz7uTf8y_mE/edit#slide=id.g31cd5d8ee82_2_331)
