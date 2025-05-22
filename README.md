# README: Determinants of Credit Ratings of State-Owned Enterprises

# Project Overview:
This project explores whether state ownership influences credit ratings and to what extent the country of origin or sector affects this relationship. Using a large financial dataset from Bloomberg containing over 3,500 rated companies across S&P, Moody’s, and Fitch, we applied machine learning models to identify potential rating biases for State-Owned Enterprises (SOEs).
Guiding question: Are SOEs treated differently from private firms by rating agencies, and do they benefit from implicit state support?

# Project Structure
- RawDataFromBloomberg: Excel data exports from Bloomberg
- Various csv files containing additional information 
- Final_Code.ipynb: Main notebook (cleaning, modeling, evaluation)

# Procedure
Data Collection & Cleaning
We began by importing and merging datasets from the three major credit rating agencies: S&P, Moody’s, and Fitch. After combining multiple Excel files per agency, we removed duplicate columns and firms to create a unified dataset for analysis.

Rating Reclassification
To simplify modeling, we grouped the 22+ original credit ratings into 6 broader categories: High grade, Upper medium grade, Lower medium grade, Non-investment grade speculative, Highly speculative, Substantial risk. This mapping was necessary to make the model outputs more interpretable and to mitigate inconsistencies across agencies.

Data Exploration
We analyzed: SOE vs. non-SOE representation, Sector distribution and Country distribution
We used the OpenAI API to classify SOEs by checking company ownership patterns via natural language processing on business descriptions.

Model Training:
Logistic Regression
We trained a multinomial logistic regression model with k-fold cross-validation.
Results:
- On non-SOEs, the model had better accuracy and AUC scores.
- On SOEs, the model consistently underestimated ratings.

Random Forest
A second model using Random Forests provided:
- More balanced error distribution and a better AUC score.
- insight on country- and sector-level effects on SOE ratings 
 
# Key insight
Both models displayed a tendency to underestimate the creditworthiness of SOEs. This supports the hypothesis that state ownership may positively influence credit ratings in practice, more than what the financial data alone would justify in our models.

 
