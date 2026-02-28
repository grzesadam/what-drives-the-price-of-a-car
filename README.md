# What Drives the Price of a Used Car?

## Executive Summary

This project analyzes a large dataset of used car listings to identify the main factors that influence used car prices. Using statistical analysis and machine learning models, we examine how vehicle attributes such as age, condition, mileage, drivetrain, and fuel type relate to price.

The primary audience for this report is a used car dealership interested in better understanding which vehicle characteristics customers value most, and how this knowledge can inform inventory and pricing decisions.

---

## Data Quality and Limitations

Before discussing the results, it is important to highlight several **significant data quality issues** in the dataset:

- **Duplicate VIN numbers** appear frequently in the data. Since a VIN should uniquely identify a vehicle, this strongly suggests that the dataset was not carefully curated and contains repeated or syndicated listings.
- A **very large number of distinct car models** are present, making it impractical to fully control for model-specific effects without substantial aggregation.
- Many features contain **missing or inconsistent values**, requiring filtering, imputation, or exclusion.

Because of these issues, the analysis should be interpreted as identifying **general trends**, not exact causal effects for individual vehicles.

---

## Modeling Approach

The analysis followed the CRISP-DM framework:

1. **Data Understanding and Cleaning**
   - Implausible prices and odometer values were removed.
   - Duplicate listings were filtered.
   - Categorical variables were encoded appropriately.
   - Derived features such as vehicle age were created.

2. **Modeling**
   - Multiple regression models were evaluated.
   - Polynomial features were tested to capture nonlinear effects.
   - Lasso regression was used to reduce overfitting and identify influential features.
   - Hyperparameters were tuned using cross-validation.

3. **Evaluation**
   - Models were evaluated using RMSE and \(R^2\) on a hold-out test set.
   - Feature importance was assessed using both model coefficients and permutation importance.

---

## Key Findings

### 1. Vehicle Age Is the Dominant Price Driver

Across all models and vehicle subsets, **vehicle age consistently emerged as the most important factor influencing price**.

- Newer vehicles command significantly higher prices.
- The relationship is strongly nonlinear: prices decline rapidly in the early years and more gradually thereafter.

**Implication for dealerships:**  
Inventory age should be a primary consideration when pricing and acquiring vehicles.

---

### 3. Mileage Matters

Mileage contributes to price differences.

- High mileage generally lowers price.
- However, mileage alone does not fully explain price variation without considering how old the vehicle is.

### 2. Vehicle Condition Has a Significant Effect 

After age and milage, **vehicle condition** has a aignificant impact on price.


**Implication for dealerships:**  
Reconditioning and clearly communicating vehicle condition can meaningfully increase perceived value.

---


### 4. Drivetrain and Fuel Type Effects Are Mostly Indirect

Features such as:
- front-wheel drive vs. rear-wheel drive,
- fuel type (e.g., hybrid),

sometimes appear as influential in the models. However, these effects are largely **proxies for specific vehicle models or trims**, not independent drivers of value.

For example:
- A rear-wheel-drive configuration often reflects a particular class of vehicle rather than a customer preference for drivetrain itself.

**Important caution:**  
These features should not be interpreted as causal price drivers in isolation.

---

## Recommendations for Used Car Dealers

Based on this analysis, the following recommendations are supported:

1. **Prioritize newer inventory**, as age is the strongest predictor of price.
2. **Invest in vehicle condition**, including reconditioning and accurate condition grading.
3. **Use mileage in context**, not as a standalone pricing factor.
4. **Avoid overinterpreting technical features** (drivetrain, fuel type) without considering the underlying vehicle model.
5. **Be cautious with automated pricing models** when data quality is uncertain; human oversight remains important.

---

## Conclusion

Despite limitations in the dataset, the analysis clearly shows that **age and condition dominate used car pricing**, while many other features play secondary or indirect roles. These findings align with practical dealership experience and can be used to support more informed inventory and pricing decisions.

Future work could improve these results by using cleaner data, aggregating models into broader vehicle categories, or incorporating regional market effects.