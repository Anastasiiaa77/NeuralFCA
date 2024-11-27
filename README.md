# OSDA
NeuralFCA Artamonova Anastasia

# Big homework description
For big homework I choose the following dataset: 

* 70k+ Job Applicants Data (Human Resource) [link](https://www.kaggle.com/datasets/ayushtankha/70k-job-applicants-data-human-resource)

## Dataset:  70k+ Job Applicants Data (Human Resource)
### Description
The dataset titled "Employability Classification of Over 70,000 Job Applicants" (but we will use only 1000 observations, for speed performance) contains a comprehensive collection of information regarding job applicants and their respective employability scores. From the survey results, we have a dataset with the following columns:
* Age: age of the applicant, >35 years old or <35 years old (categorical)
* EdLevel: education level of the applicant (Undergraduate, Master, PhD…) (categorical)
* Gender: gender of the applicant, (Man, Woman, or NonBinary) (categorical)
* MainBranch: whether the applicant is a profesional developer (categorical)
* YearsCode: how long the applicant has been coding (integer)
* YearsCodePro: how long the applicant has been coding in a professional context, (integer)
* PreviousSalary: the applicant's previous job salary (float)
* ComputerSkills: number of computer skills known by the applicant (integer)
* Employed: target variable, whether the applicant has been hired (categorical).
### Preprocessing
First of all, I deleted the columns ['HaveWorkedWith', 'Country'], in order to correctly apply OHE to categorical features (Otherwise, we will have too much features after using OHE (>1000)). For numeric features, I set a threshold based on the mean value in the column, so all values in a particular column were divided into 2 set (greater than the threshold and less than the threshold, respectively). After binarization, we get 21 features from 14. Then I selected the top 50 concepts and built NN using them. After learning, we have graph:
[[JOB](https://github.com/RomanGladkikh/OSDA/blob/main/NeuralFCA/images/job_fitted.png)]
### Results

Model | Accuracy | F1-score | 
--- | --- | --- |
KNeighborsClassifier | 0.783 | 0.782 | 
DecisionTree | 0.783 | 0.781 | 
RandomForest | 0.810 | 0.805 | 
LogisticRegression | 0.820 | 0.818 | 
**NeuralFCA** | **0.823** | **0.824** |

FCA exhibited wery good results on the "70k+ Job Applicants Data (Human Resource)" dataset with Accuracy and F1 Score 0.823 and 0.824. In comparison, other machine learning models showed worse results than NeuralFCA
![alt text](https://github.com/RomanGladkikh/OSDA/blob/main/NeuralFCA/images/job_fitted.png)



