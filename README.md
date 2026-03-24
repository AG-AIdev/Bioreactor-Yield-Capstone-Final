## Final Conclusion

This project successfully generated a synthetic upstream bioprocessing dataset and used it to model the relationship between key operational parameters and final batch yield. Although the dataset is synthetic, data from a real production batch was used as a baseline while the parameter ranges and variability were designed to resemble realistic mammalian-cell culture conditions and the yield function introduced structured, learnable patterns.

### Executive Summary (Nontechnical)
This project explored how changes in upstream fermentation / cell culture conditions such as pH, temperature, dissolved oxygen, and mixing affect final yield of biologics manufacturing. By training several machine learning models, we identified which conditions matter most and which modeling approaches best capture these relationships. The strongest model, Gradient Boosting, can reliably predict yield and provides insights that can support upstream process optimization.

### Data Cleaning Summary
Before modeling, the dataset was validated to ensure accuracy and consistency:
- Confirmed no missing values  
- Verified correct data types  
- Removed duplicate rows  
- Checked that all parameters fell within biologically reasonable ranges  

This ensured a clean foundation for EDA and modeling.

### Key Findings
1. **Baseline linear models** (Linear, Ridge, Lasso) captured broad linear trends and established a benchmark for comparison.  
2. **Tree‑based models** (Random Forest, Gradient Boosting) significantly improved predictive accuracy by capturing nonlinear effects such as:
   - Optimal pH ranges  
   - Temperature sensitivity around 37°C  
   - Positive influence of dissolved oxygen  
3. **Gradient Boosting** consistently delivered the strongest performance which improved further after hyperparameter tuning.  
4. **Neural Networks** performed competitively but did not surpass Gradient Boosting, suggesting that tree based boosting methods best capture the structure of this dataset.

### Actionable Recommendations
Based on model insights, the following upstream adjustments may improve yield:
- **Maintain pH within the optimal biological window**, as deviations sharply reduce yield.  
- **Minimize temperature fluctuations around 37°C** by reviewing probe calibration, tolerance and heat‑transfer / temperature uniformity.  
- **Optimize dissolved oxygen control**, potentially through improved aeration or oxygen enriched sparging.  
- **Reduce mixing time variability** to improve batch‑to‑batch consistency.

These recommendations are intended for process engineers and product development teams evaluating upstream performance.

### Next Steps
- Validate the Gradient Boosting model using real historical batch data.
- Incorporate additional upstream variables (e.g., feed strategy, viable cell density) to improve predictive power.
- Perform sensitivity analysis to quantify each parameter’s contribution to yield variability.
- Explore model‑based optimization to identify ideal operating setpoints.

### Overall Conclusion
The modeling results demonstrate that nonlinear machine learning methods provide substantial improvements over linear baselines when predicting yield from upstream parameters. Gradient Boosting was the best‑performing model, and hyperparameter tuning further strengthened its predictive accuracy. This workflow from synthetic data generation through EDA, data cleaning, feature engineering, modeling, and tuning provides a complete and defensible demonstration of predictive modeling in bioprocessing manufacturing
