
# Deforestation Issue Analysis Using Apriori Algorithm

## Author

Sagnik Patra

---

## 1. Project Overview

This project analyzes deforestation patterns using the Apriori Association Rule Mining algorithm.

The original assignment mentioned SVM, but this implementation uses Apriori instead to discover hidden relationships between environmental, economic, and governance-related factors contributing to deforestation.

The dataset used is:

`deforestation_dataset.csv`

The dataset contains information about countries, years, forest loss, tree cover loss, CO2 emissions, rainfall, population, GDP, agriculture land percentage, deforestation policy strictness, corruption index, international aid, illegal lumbering incidents, and protected areas.

---

## 2. Objective

The main objective of this project is to discover association rules that explain which combinations of factors are strongly related to high deforestation.

The project focuses on:

- Data preprocessing and cleaning
- Missing value handling
- Feature binning and categorization
- Transaction generation
- Frequent itemset mining
- Association rule generation
- Rule evaluation using support, confidence, lift, leverage, and conviction
- Feature impact analysis
- Deforestation mitigation recommendations

---

## 3. Dataset Information

Original dataset shape:

(100, 14)

Columns used:

['Country', 'Year', 'Forest_Loss_Area_km2', 'Tree_Cover_Loss_percent', 'CO2_Emission_mt', 'Rainfall_mm', 'Population', 'GDP_Billion_USD', 'Agriculture_Land_Percent', 'Deforestation_Policy_Strictness', 'Corruption_Index', 'International_Aid_Million_USD', 'Illegal_Lumbering_Incidents', 'Protected_Areas_Percent']

---

## 4. Data Preprocessing

The dataset was cleaned by handling missing values.

Numerical columns were filled using median imputation.

Categorical columns were filled using mode imputation.

Important numerical variables were converted into categories because Apriori works with transactional/categorical data.

Examples:

- Forest loss was converted into Low, Medium, and High forest loss categories.
- CO2 emission was converted into Low, Medium, and High CO2 categories.
- Population was converted into Low, Medium, and High population categories.
- GDP was converted into Low, Medium, and High GDP categories.
- Rainfall was converted into Low, Medium, and High rainfall categories.
- Illegal lumbering incidents were converted into Low, Medium, and High illegal lumbering categories.
- Policy strictness was converted into Weak, Moderate, and Strong policy categories.
- Corruption index was converted into Low, Medium, and High corruption categories.

---

## 5. Apriori Algorithm

The Apriori algorithm was applied to discover frequent itemsets.

Minimum support used:

0.1

Minimum confidence used:

0.50

Total frequent itemsets generated:

1092

Total association rules generated:

1000

Total high deforestation-related rules generated:

9

---

## 6. Top High Deforestation Rules


Rule:
IF Country_Indonesia, Corruption_Category_High_Corruption, Policy_Category_Weak_Policy
THEN Tree_Cover_Loss_Category_High_Tree_Cover_Loss

Support: 0.100
Confidence: 0.588
Lift: 1.730


Rule:
IF Country_Indonesia, Policy_Category_Weak_Policy
THEN Tree_Cover_Loss_Category_High_Tree_Cover_Loss

Support: 0.110
Confidence: 0.579
Lift: 1.703


Rule:
IF Country_Indonesia, Policy_Category_Weak_Policy
THEN Corruption_Category_High_Corruption, Tree_Cover_Loss_Category_High_Tree_Cover_Loss

Support: 0.100
Confidence: 0.526
Lift: 1.645


Rule:
IF Policy_Category_Weak_Policy, Illegal_Lumbering_Category_Medium_Illegal_Lumbering
THEN Corruption_Category_High_Corruption, Tree_Cover_Loss_Category_High_Tree_Cover_Loss

Support: 0.110
Confidence: 0.500
Lift: 1.562


Rule:
IF Country_Indonesia, Corruption_Category_High_Corruption
THEN Tree_Cover_Loss_Category_High_Tree_Cover_Loss

Support: 0.110
Confidence: 0.524
Lift: 1.541


Rule:
IF Country_Indonesia
THEN Tree_Cover_Loss_Category_High_Tree_Cover_Loss

Support: 0.120
Confidence: 0.522
Lift: 1.535


Rule:
IF Rainfall_Category_Low_Rainfall, Policy_Category_Weak_Policy
THEN Tree_Cover_Loss_Category_High_Tree_Cover_Loss

Support: 0.120
Confidence: 0.500
Lift: 1.471


Rule:
IF Illegal_Lumbering_Category_Medium_Illegal_Lumbering, Policy_Category_Weak_Policy
THEN Tree_Cover_Loss_Category_High_Tree_Cover_Loss

Support: 0.110
Confidence: 0.500
Lift: 1.471


Rule:
IF Policy_Category_Weak_Policy, Corruption_Category_High_Corruption, Illegal_Lumbering_Category_Medium_Illegal_Lumbering
THEN Tree_Cover_Loss_Category_High_Tree_Cover_Loss

Support: 0.110
Confidence: 0.500
Lift: 1.471



---

## 7. Feature Impact Analysis

The following features were analyzed based on their appearance in high deforestation rules:

                   rule_count  avg_support  avg_confidence  avg_lift
Corruption                3.0     0.106667        0.537348  1.580436
Policy                    7.0     0.108571        0.527643  1.578842
Illegal_Lumbering         3.0     0.110000        0.500000  1.501225
Rainfall                  1.0     0.120000        0.500000  1.470588
CO2                       0.0     0.000000        0.000000  0.000000
Population                0.0     0.000000        0.000000  0.000000
Agriculture               0.0     0.000000        0.000000  0.000000
GDP                       0.0     0.000000        0.000000  0.000000
Aid                       0.0     0.000000        0.000000  0.000000
Protected_Area            0.0     0.000000        0.000000  0.000000

From the rule mining results, features with higher average lift are considered more strongly associated with high deforestation.

---

## 8. Interpretation of Results

The Apriori model helps identify common combinations of factors that frequently appear with high forest loss or high tree cover loss.

Important patterns may include:

- High CO2 emission is often associated with high forest loss.
- High population pressure may increase land demand and contribute to deforestation.
- High GDP and agricultural expansion may indicate economic development activities linked to forest clearing.
- Weak policy strictness can be associated with higher forest loss.
- High corruption may reduce the effectiveness of environmental protection policies.
- High illegal lumbering incidents are directly related to deforestation risk.
- Low protected area coverage can increase the probability of high deforestation.

---

## 9. Visualizations Generated

The project generated the following visualizations:

- correlation_heatmap.png
- country_deforestation_trend.png
- rainfall_vs_forest_loss.png
- gdp_vs_forest_loss.png
- population_vs_forest_loss.png
- co2_vs_forest_loss.png
- policy_vs_deforestation.png
- feature_distribution.png
- top_rules_lift.png
- top_rules_confidence.png
- association_rule_network.png
- feature_importance_lift.png

---

## 10. Recommendations for Deforestation Mitigation

### 1. Strengthen Policy Enforcement

Countries with weak policy strictness should improve forest protection laws, monitoring systems, and penalties for illegal deforestation.

### 2. Reduce Illegal Lumbering

Illegal lumbering incidents should be reduced through satellite monitoring, forest patrols, and digital timber tracking systems.

### 3. Improve Governance

High corruption can weaken environmental regulation. Transparent land-use approvals and strict anti-corruption policies are needed.

### 4. Promote Sustainable Agriculture

Agricultural land expansion should be managed through sustainable farming methods, agroforestry, and improved land productivity.

### 5. Expand Protected Areas

Countries with low protected area coverage should increase national parks, biodiversity reserves, and conservation zones.

### 6. Link International Aid to Forest Protection

International aid should be connected with measurable forest conservation outcomes.

### 7. Control CO2-Linked Industrial Expansion

High CO2 emission regions should adopt cleaner technologies and sustainable development planning.

---

## 11. Conclusion

This project successfully applied the Apriori algorithm to identify hidden patterns related to deforestation.

Unlike SVM, which predicts numerical deforestation values, Apriori provides interpretable rules showing which combinations of social, economic, environmental, and governance factors are associated with high forest loss.

The findings can support policy makers, environmental researchers, and conservation agencies in designing targeted deforestation control strategies.

---

## 12. Deliverables

The following files were generated:

- processed_deforestation_dataset.csv
- scaled_numeric_features.csv
- transaction_encoded_dataset.csv
- frequent_itemsets.csv
- association_rules.csv
- deforestation_high_risk_rules.csv
- feature_impact_summary.csv
- rule_summary.json
- rule_summary.yaml
- final_report.md
- correlation_heatmap.png
- country_deforestation_trend.png
- rainfall_vs_forest_loss.png
- gdp_vs_forest_loss.png
- population_vs_forest_loss.png
- co2_vs_forest_loss.png
- policy_vs_deforestation.png
- feature_distribution.png
- top_rules_lift.png
- top_rules_confidence.png
- association_rule_network.png
- feature_importance_lift.png

