# What Drives the Price of a Car? 🚗💰

## Project Overview
This project digs into a large Kaggle dataset of used cars to answer a simple question: what really makes one car sell for more than another?​

Using basic data exploration and modeling, the goal is to spot which features buyers actually pay for.

The outcome is a clear set of insights and practical recommendations that a used car dealership can use to price cars smarter and highlight the features customers value most.

## Project organization
- Files and directories are purposefully named and minimal:
  - `used_car_price_prediction_insights.ipynb` — main, well-documented notebook
  - `README.md` — this file
  - `data/` — raw and feature-engineered datasets
  - `images/` — exported plots
- Notebook contains a clear title, a table of contents (headings), step-by-step sections, and narrative text.

## Business Understanding
Understand which features have the biggest impact on selling price of used cars, so a used car dealership can price cars more accurately and highlight the attributes.

Success means dealers can:
- Set competitive prices faster and with more confidence.
- Increase profit per car while staying attractive to buyers.
- Use clear, data-backed insights (simple rules) in daily pricing decisions.

## Modeling Approach
Multiple regression models are applied:
1. **Linear Regression** – Baseline for interpretability.
2. **Ridge Regression** – Handles correlated features, reduces variance.
3. **Lasso Regression** – Performs feature selection, simplifies the model.

All models predict log(price) to account for skewness in car prices. Cross-validation (5-fold) and grid search were used to select optimal hyperparameters for Ridge and Lasso models. Evaluation metrics include RMSE, MAE, and R². Coefficients and feature importances are interpreted and presented clearly.

## Key Findings
- **Top-performing model:** Polynomial Ridge Regression with numeric + categorical features.
- **Evaluation metrics on test data:**
  | Model                        | Test RMSE | Test MAE | Test R² |
  |-------------------------------|-----------|----------|---------|
  | Poly+Ridge (Numeric + Cat)    | 0.5235    | 0.3221   | 0.6517 |
  | Poly+Lasso (Numeric + Cat)    | 0.5267    | 0.3257   | 0.6475 |
  | Linear (Numeric + Cat)        | 0.5299    | 0.3265   | 0.6432 |
  | Linear (Numeric)              | 0.6168    | 0.4204   | 0.5164 |

**Insights for Dealers:**
- Categorical features like `manufacturer`, `condition`, `cylinders`, `fuel`, and `type` significantly improve predictions.
- Polynomial terms capture non-linear effects such as car age vs price.
- Newer cars, lower mileage, and better condition increase prices.
- Premium brands and certain fuel types (e.g., diesel) add value.

## Recommendations & Next Steps
- Deploy Poly+Ridge (Numeric + Categorical) model for pricing predictions.
- Integrate into dealership dashboards or internal tools for real-time pricing guidance.
- Periodically monitor model performance using RMSE and R²; retrain when necessary.
- Explore additional categorical features, polynomial degrees, and market factors in future iterations.
- Use Lasso as a secondary model for feature selection insights.

## Deployment Strategy
- The model provides actionable pricing and inventory insights.
- Sales teams can prioritize high-value cars and set competitive prices.
- Reports and dashboards will summarize feature effects and highlight opportunities.
- Continuous monitoring ensures model reliability and adaptation to market changes.

## Repository
The full Jupyter notebook with all analysis, visualizations, and model implementations is available [used_car_price_prediction_insights.ipynb](used_car_price_prediction_insights.ipynb).
