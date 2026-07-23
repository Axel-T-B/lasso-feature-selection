# Genomic Feature Selection: LASSO Comparative Analysis

A Python-based machine learning pipeline evaluating the feature selection capabilities of Base LASSO, Elastic-Net, Random LASSO, and Hi-LASSO in extreme high-dimensional (p >> n) genomic environments. 

## Project Overview
This project simulates genomic clinical environments to test algorithms on their ability to isolate disease-driving biomarkers while avoiding over-shrinkage under extreme clinical noise. The final Hi-LASSO pipeline was validated against real Glioblastoma (GBM) clinical data across 19,777 genes, discovering 7 novel candidate biomarkers.
**Methodology Note:** To optimize for extreme high-dimensional (p >> n) environments and ensure an unbiased comparative baseline, this pipeline modifies both the traditional Random LASSO and Hi-LASSO architectures. Feature selection in simulations is driven by a custom relative coefficient threshold grid rather than native arbitrary thresholds or binomial gatekeepers. Statistical robustness of the selected biomarkers is validated post-hoc via 1-sample T-tests (synthetic data) and Binomial Significance tests (clinical data).

## Tech Stack
* **Language:** Python
* **Data Processing:** Pandas, NumPy
* **Machine Learning:** Scikit-learn (Coordinate Descent, Penalized Regression)
* **Visualization:** Matplotlib, Seaborn
* **Optimization:** Parallel Processing (Joblib), Adaptive Threshold Grids

## Repository Structure
* `/Simulation_Data/` - Scripts and outputs for generating Dataset I-IV.
* `/Real_Data_Experiments/` - Clinical data validation on Glioblastoma (GBM) arrays.
* `/results/` - F1, AUPRC, and RMSE metrics across all tested models.
* `/figures/` - Output visualizations for research presentations.
* `Eval_*.ipynb` - Core model evaluation pipelines and hyperparameter tuning.

## Execution
To reproduce the evaluation pipelines and visualizations, run the notebooks in the following order:
1. `generate_data.ipynb`
2. `Eval_Base_Models.ipynb`
3. `Eval_Random_Lasso.ipynb`
4. `Eval_Hi_Lasso.ipynb`
5. `Final_Visualizations.ipynb` (Compiles metric outputs into comparative graphs)
6. `/Real_Data_Experiments/Eval_Hi_Lasso.ipynb` (Validates pipeline on real clinical dataset)
7. `/Real_Data_Experiments/Final_Visualizations.ipynb` (Creates a table and bar graph of top 10 genes)

## Documentation
* [Project Report (PDF)](presentation/Final_Report.pdf)
* [Final Presentation Deck (PDF)](presentation/Presentation.pdf)