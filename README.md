# Used Car Price Prediction (Pricing Analytics)

Built an end-to-end regression modeling pipeline to predict used car prices and translate results into dealership pricing actions (identify underpriced/overpriced inventory).

## Project Goal
Estimate **fair market value** for used cars using historical listings, so a dealership can:
- spot **underpriced** cars (pricing opportunity)
- spot **overpriced** cars (reduce stagnation / improve conversion)
- understand which features most influence price (e.g., power, year)

## Dataset
**Cars4U (India) — Used Cars Dataset**  
Typical columns include:
- Vehicle attributes: `Year`, `Kilometers_Driven`, `Fuel_Type`, `Transmission`, `Owner_Type`, `Engine`, `Power`, `Mileage`, `Seats`
- Target: `Price`

> Note: Dataset file is not included in this repo.

## Approach (End-to-End Workflow)
1. **Data Cleaning**
   - Missing value handling (median/mean as appropriate)
   - Outlier checks and removal of unrealistic values
   - Dropped extremely sparse feature(s) (e.g., `New_price` with heavy missingness)

2. **Exploratory Data Analysis (EDA)**
   - Distributions and outliers for numeric features
   - Category distributions (Location, Fuel Type, Transmission, Owner Type, etc.)
   - Correlation insights (e.g., Engine–Power, Power–Price)

3. **Preprocessing & Feature Engineering**
   - Split into train/test
   - Encoding categorical variables (One-Hot Encoding)
   - Optional transformations depending on model choice

4. **Modeling**
   - Regression models to predict `Price`
   - Model evaluation using standard regression metrics (R2 / Adj R2/ RMSE / MAE)

## Key Insights (example phrasing — edit to match your EDA)
- **Power** and **vehicle age (Year)** were among the strongest predictors of price.
- **Transmission** and **Fuel Type** showed meaningful price differences across segments.
- Some features showed strong relationships with each other (e.g., **Engine ↔ Power**), which informed modeling choices.

## Business Recommendations & Next Steps
- Use model outputs to identify **underpriced and overpriced** vehicles relative to market value
- Prioritize **high-value vehicles** (high power, newer models) for optimized pricing and faster revenue capture
- Reduce inventory stagnation by re-pricing vehicles with long listing durations using model guidance
- Periodically retrain the model to adapt to changing market conditions as the used-car market scales  
- Next steps: Segment vehicles using PCA and clustering for tier-based pricing as the Indian used-car market continues to grow (projected to exceed USD 73B by 2030; source: Mordor Intelligence)

