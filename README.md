# H1N1-Vaccine-Analysis.
![image](https://github.com/user-attachments/assets/f9d0bccc-281b-41a1-81d3-d3dbdabe351b)

- Vaccine is a biological substance introduced to an individual that stimulates the immune system to recognize and fight specific pathogens without causing the disease itself.
- Vaccination is an effective tool that plays a crucial role in public health in preventing the spread of a disease. However there are several factors that impact vaccination rates such as Vaccination accessibility, Socioeconomic factors, beliefs or opinions and etc.

## Business Understanding.
### Problem Statement.
Despite the availability of H1N1 Flu vaccine, majority of the individuals do not get the vaccine. Identifying factorsthat influence vaccine uptake can help improve public health interventions.

### Objectives.
- Develop a predictive model to determine whether individuals received the H1N1 vaccine.
- Estimating Herd Immunity using Vaccination Coverage and risk based factors.
- Understanding Behavioral, Attitudinal and Health Factors in Vaccination.
- Evaluate the role of Healthcare recommendation in vaccine decision.
- Identify descipancies in vaccine access and acceptance.

### Key business 
1. Who is likely to get the H1N1 vaccine?
2. Are we reaching the protective vaccine coverage levels?
3. What influences individual vaccine decisions?
4. How do Healthcare practitioners influence vaccine decisions?
5. Which groups have the lowest vaccine uptake?

## Data Overview.
The data was collected from the National H1N1 Flu survey.
  - The dataset comprises of 26707 rows and 38 columns after merging of 2 datasets(Training label and Training Features.
  - After a thorough data preparation (removing missing values, duplicates, unnecessary columns) the dataset comprised of 19656 rows and 30 columns.

## Data Analysis
### Are we reaching the protective vaccine coverage levels?
1. **Identify individuals who have and have not received the H1N1 Vaccine**.
![download](https://github.com/user-attachments/assets/374f8691-4e51-42dd-9289-7adb09a80b31)
- The visualization above shows that majority of the individuals have not gotten the H1N1 Flu Vaccine.

2. **Assessing Behavior risk factors**
![download](https://github.com/user-attachments/assets/b59fbdd5-364a-4979-8077-04a827e5f166)
- Behavioral factors such as hygiene(washing of hands), exposure avoidance influence vaccination rates. In the graph above, it illustrates how this behaviors encourage people from getting vaccinated. 

### What influences individual vaccine decisions?
1. **Estimate the relationship between Age and H1N1 vaccination.**
![download](https://github.com/user-attachments/assets/7c4d0d11-fcfc-442f-a149-c2e27628c14c)
- The graph above shows how the 55 – 64 yrs are the most vaccinated age group especially the females. They are obligated to get vaccinated since them and 65+ yrs will be highly affected with the disease causse of their low immunity.

2. **Estimate how Opinion concerning the vaccine affects Vaccine Uptake.**
![download](https://github.com/user-attachments/assets/ec472dc9-be99-4d74-81db-ad85c1c043b6)
- This illustrates how opinion or perception influences individuals in making decision about getting vaccinated. For example the first barplot shows how majority off the individuals avoid the H1N1 vaccination since they perceive that the vaccine causes sickness. Nonetheless it is evident that the respondents have some knowledge that the H1N1 vaccine is effective and that without vaccination you are more more prone to the H1N1 flu.

### How do Healthcare practitioners influence vaccine uptake?
![download](https://github.com/user-attachments/assets/5aa8e406-f8cf-43ed-aea0-ab1c81cf9244)
- The graph above illustrates that minority of the individuals got recommendation from the doctor, that majority of the recommended individuals got vaccinated.
- Recommendation pays a vital role in vaccination decision of individuals.

### Which group has the lowest vaccine uptake?
1. **Distribution of Racial groups.**

![download](https://github.com/user-attachments/assets/91d1acf0-a539-46df-ad51-40336adf3742)
- The distribution above shows how majority of the vaccinated individuals are of white racial group.

2. **Estimate vaccine coverage by Region.**
![download](https://github.com/user-attachments/assets/e06f6d20-38ec-49fe-ac1c-998bca3d3d38)
- It is shown that `lzgpxyithas` the lowest vaccination range as compared to other regions. This shows vaccine access disparity in regions hence affecting vaccine coverage.

 ## Model
 - Data Preprocessing ie  resampling the highly imbalanced classes, feature selection, scaling, dropped columns, label encoding. The model's Hyperparameters were tuned to get the best parameters for the best results.
 - Best Parameters for Random Forest using BayesSearch: OrderedDict([('max_depth', 18), ('max_features', 'sqrt'), ('min_samples_leaf', 1), ('min_samples_split', 3), ('n_estimators', 498)]) 

- *Random Forest Evaluation Metrics:*
  - Training time: 578.3828537464142 and prediction time: 0.7153973579406738 
  - Accuracy: 0.8895 
  - Precision: 0.9147 
  - Recall: 0.8626 
  - ROC-AUC: 0.9521
- BayesSearchCV had the best out put as compared to the other hyperparameters. I took into consideration recall metric since that is what my main focus was on.
`Recall: This measures how many actual positives were predicted correctly.`

#### ROC-AUC cuve
![download](https://github.com/user-attachments/assets/e439a82e-aac9-4606-86bc-60636721a055)
`The ROC-AUC curve measures the ability of the model to correctly differentiate between classes.` So the chart above explains that the model has a 95% probability of being able to distinguish between the 2 classes (class 0: Not vaccinated, Class 1: vaccinated).

#### Confusion matrix
![download](https://github.com/user-attachments/assets/38607034-380b-4a72-a52b-77d31b323868)
A confusion Matrix is used to evaluate the performance of a model by comparing the actual and the predicted class labels.

#### Classification Matrix
 | Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 0     | 0.87      | 0.92   | 0.89     | 2985    |
| 1     | 0.91      | 0.86   | 0.89     | 3071    |
| **Accuracy** |           |        | **0.89**  | **6056**|
| Macro avg | 0.89      | 0.89   | 0.89     | 6056    |
| Weighted avg | 0.89      | 0.89   | 0.89     | 6056    |


## Conclusion.
- **Influence of Behavioral and Attitudinal Factors:**

  - Behavioral risk factors, such as frequent hand-washing and avoiding large gatherings, are critical indicators that could be linked to an individual’s likelihood of receiving the H1N1 vaccine. Those who engage in these behaviors may have a higher level of health consciousness and may be more likely to accept preventive health measures, including vaccination.
   - Perceptions of vaccine efficacy and risk are strongly associated with vaccine decisions. Those who perceive the vaccine as more effective and view the risk of getting sick as higher are more likely to vaccinate. Conversely, those who worry about vaccine side effects, such as getting sick from the vaccine, tend to be less likely to receive it.

- **Role of Healthcare Practitioners:**

  - Healthcare recommendations have a significant impact on vaccine uptake. The data suggests that individuals who received a recommendation from their doctor (either for the H1N1 or seasonal flu vaccine) were more likely to get vaccinated. This underlines the importance of healthcare providers in influencing vaccination behavior.

- **Socioeconomic and Demographic Factors:**

  - Socioeconomic factors, such as income and education level, have a considerable effect on vaccination uptake. Higher levels of education and income appear to be correlated with higher vaccination rates, indicating that individuals with greater access to healthcare information and resources may be more likely to vaccinate.
  - Age, race, and geographic location also play a role in vaccine decisions. Disparities in vaccine uptake are particularly noticeable across different racial, socioeconomic, and geographic groups, which suggests that certain communities are underserved in terms of vaccine access and acceptance.

- **Discrepancies in Vaccine Access and Acceptance:**

  - There is evidence of disparities in vaccine uptake, with certain groups (such as lower-income households and specific racial groups) showing lower rates of vaccination. These discrepancies highlight the need for targeted interventions that address access issues and vaccine hesitancy in these communities.

- **Herd Immunity and Vaccine Coverage:**9

  - The data indicates that protective vaccine coverage levels may not have been reached for H1N1, which is critical for achieving herd immunity. The likelihood of reaching sufficient vaccine coverage is influenced by both individual vaccine decisions and broader population-level factors, such as herd immunity thresholds and distribution effectiveness.

## Recommendation.
- **Targeted Health Campaigns Based on Behavioral Insights:**
  - Public health campaigns should target individuals who are less likely to engage in preventive behaviors (e.g., not washing hands frequently, attending large gatherings, or touching their face). Emphasizing the importance of the H1N1 vaccine alongside these preventive behaviors could encourage a more holistic approach to health protection.
  - Additionally, addressing concerns about side effects and emphasizing the vaccine’s effectiveness could reduce hesitancy. Educational materials should be tailored to address common misconceptions about vaccine safety.

- **Enhance Healthcare Provider Engagement:**
  - Given the strong influence healthcare practitioners have on vaccine decisions, improving doctor-patient communication around vaccines should be prioritized. Health practitioners should actively recommend vaccines during consultations, particularly for high-risk groups, and be trained to address vaccine hesitancy and concerns directly.

- **Address Socioeconomic and Demographic Disparities:**
  - Targeted outreach is needed to ensure that underserved communities have access to vaccines and accurate information. Programs aimed at lower-income households, rural populations, and specific racial or ethnic groups should be implemented to reduce barriers to vaccination.
  - Mobile vaccination clinics(door to door vaccination eg. Polio) or partnerships with community organizations can help increase access to vaccines in underserved geographic regions.

- **Promote Vaccine Knowledge and Trust:**
  - Vaccine literacy programs should be implemented to increase individuals’ understanding of the benefits and safety of vaccination. This could include addressing common fears about vaccine side effects and providing data on the long-term benefits of vaccination in preventing disease spread(herd immunity is achieved)
  - Using trusted community leaders to endorse vaccination within specific communities may help overcome resistance, especially in groups with higher vaccine hesitancy.

- **Increase Focus on Behavioral Risk Factors:**
  - Encourage individuals who engage in risk-reducing behaviors (eg hand washing) to view vaccination as part of their broader health strategy.

- **Improving Vaccine Accessibility:**
  - Policies should be implemented to ensure equitable vaccine distribution, particularly in areas where access is limited. This includes extending vaccine availability through pharmacies, clinics.

- **Research on Long-Term Vaccine Uptake:**
  - More research is needed to understand the long-term trends in vaccine uptake, especially in light of future pandemic responses. Understanding how past experiences (e.g., H1N1) shape attitudes toward future vaccines can guide policy-making and improve public health preparedness.
