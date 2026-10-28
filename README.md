# Hypothesis Testing with Python

A statistical analysis comparing district-level literacy rates in **STATE21** and **STATE28** using a two-sample hypothesis test.

This project is based on a guided lab from Coursera's *The Power of Statistics* course in the Google Advanced Data Analytics learning path. It demonstrates how to use Python to compare two sample means and interpret the result using a p-value.

## Project Objective

The Department of Education wants to understand whether the difference in mean district literacy rates between two states is statistically significant. Since surveying every district is not feasible in this scenario, the analysis draws a sample of 20 districts from each state and compares their mean literacy rates.

## Repository Contents

| File | Description |
|---|---|
| `hypothesis test.ipynb` | Jupyter Notebook containing the analysis |
| `hypothesis test.html` | HTML export of the notebook |
| `education_districtwise.csv` | Dataset used for the analysis |

## Tools and Libraries

- **Python**
- **Pandas** — data loading, filtering, cleaning, and sampling
- **SciPy** — statistical hypothesis testing
- **Jupyter Notebook** — interactive analysis

## Analysis Workflow

1. **Load and prepare the data** — read the CSV file with Pandas and remove rows containing missing values.
2. **Filter the states** — select district records for STATE21 and STATE28 using the `STATNAME` column.
3. **Draw random samples** — select 20 districts per state with replacement. Fixed random seeds are used so the samples can be reproduced.
4. **Calculate sample means** — compute the mean of the `OVERALL_LI` literacy-rate column for each sample.
5. **Define the hypotheses** — test whether the two population mean district literacy rates differ.
6. **Run Welch's two-sample t-test** — use `scipy.stats.ttest_ind()` with `equal_var=False`, avoiding the assumption that the population variances are equal.
7. **Interpret the p-value** — compare it with the 5% significance level and draw a statistical conclusion.

## Hypotheses

- **Null hypothesis (H₀):** The population mean district literacy rates of STATE21 and STATE28 are equal.
- **Alternative hypothesis (H₁):** The population mean district literacy rates of STATE21 and STATE28 are different.

This is a **two-tailed test**, with a significance level of **α = 0.05**.

## Results

The guided analysis reports the following sample results:

| Metric | STATE21 | STATE28 |
|---|---:|---:|
| Sample size | 20 | 20 |
| Mean district literacy rate | Approximately 70.8% | Approximately 64.6% |

- **Observed difference in sample means:** approximately 6.2 percentage points
- **Reported p-value:** approximately 0.0064
- **Significance level:** 0.05

### Conclusion

Because the reported p-value (0.0064) is below 0.05, the null hypothesis is rejected. The sample provides statistically significant evidence of a difference between the population mean district literacy rates of STATE21 and STATE28.

STATE21 has the higher sample mean, while STATE28 has the lower sample mean. This result may help identify where further educational investigation is needed. However, statistical significance alone does not establish why the difference exists or determine how government funding should be allocated.

> The figures above are the results reported in the guided analysis. They depend on the dataset, sampling approach, and specified random seeds.

## How to Run

### 1. Install the dependencies

```bash
pip install pandas scipy jupyter
```

### 2. Open the notebook

Clone or download this repository, then open `hypothesis test.ipynb` in Jupyter Notebook or JupyterLab.

### 3. Run the cells

Make sure `education_districtwise.csv` is in the same directory as the notebook, then run the cells in order.

Alternatively, open the [HTML export](./hypothesis%20test.html) to read the analysis without running the code.

## Key Learnings

- Formulating null and alternative hypotheses
- Understanding two-tailed hypothesis testing
- Drawing reproducible random samples with Pandas
- Comparing two independent sample means
- Performing Welch's t-test with SciPy
- Interpreting p-values against a significance level
- Translating statistical results into a practical decision-making context

## Author

**Ankit Tripathi**  
GitHub: [@ankitt994](https://github.com/ankitt994)
