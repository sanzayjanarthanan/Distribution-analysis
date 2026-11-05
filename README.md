# Task 27 – Distribution Analysis (Iris Dataset)

**Veda Technology · AI & ML Track · Level 1 · Day 27**

## Objective
Create a histogram for a numerical variable and analyze the distribution of its values, to understand how numerical data is distributed.

## Tools Used
- Python
- Pandas
- Matplotlib
- Seaborn (only to load the dataset)
- Jupyter Notebook

## Dataset
Iris dataset (`sns.load_dataset("iris")`) – 150 flowers, 5 columns. The numerical variable analysed is **`petal_length`** (in cm).

## Files in this Repository
| File | Description |
|------|-------------|
| `distribution_analysis.ipynb` | Notebook with the code and histogram |
| `iris.csv` | Dataset used |
| `histogram.png` | Histogram of petal length |
| `README.md` | Description of the distribution and observations |

## 1. Histogram

```python
plt.hist(data, bins=15, color="steelblue", edgecolor="black")
plt.axvline(data.mean(), color="red", linestyle="--", label="Mean")
plt.axvline(data.median(), color="green", linestyle="--", label="Median")
plt.title("Distribution of Petal Length (Iris Dataset)")
plt.xlabel("Petal Length (cm)")
plt.ylabel("Frequency")
```

![Histogram](histogram.png)

**Choice of bins:** Different bin counts (10, 15, 20) were tried. 15 bins showed the shape of the distribution clearly without being too coarse or too noisy.

## 2. Summary Statistics

| Statistic | Value |
|-----------|-------|
| Count | 150 |
| Minimum | 1.0 cm |
| Maximum | 6.9 cm |
| Mean | 3.76 cm |
| Median | 4.35 cm |
| Standard deviation | 1.77 cm |
| Skewness | -0.27 |

## 3. Description of the Distribution
Petal length is **bimodal**: the histogram has two separate groups instead of a single bell shape. One group lies between 1.0 and 1.9 cm, and the other starts at 3.0 cm and goes up to 6.9 cm. The values are widely spread (standard deviation 1.77 cm), and the overall skewness is slightly negative (-0.27).

## 4. Observations
1. **Two clear clusters.** 50 flowers have petal length below 2 cm and 100 flowers have 3 cm or more. No flower falls between 2 and 3 cm, so there is a clear gap between the groups. This suggests that the data contains different underlying groups (the Iris dataset contains three species).
2. **Mean and median differ.** The mean (3.76) is lower than the median (4.35). Because the two groups are mixed, the mean falls in the empty gap and does not represent a typical flower. A single average would be misleading for this variable.
3. **Mild left skew, but shape matters more.** Skewness of -0.27 indicates a slight tail towards smaller values, but the bimodal shape is the more important feature of this distribution.
4. **Wide spread.** A high standard deviation relative to the range shows that petal length varies a lot across the dataset.

## 5. Key Learnings
- Summary statistics alone (mean, median) can hide the real shape of the data. Always plot the distribution.
- The number of bins changes how the histogram looks, so experiment before concluding.
- A bimodal distribution is a hint that the data may contain different groups, which can be useful for classification later.

## Interview Questions – Key Answers
1. **What is a histogram?** A chart that splits numerical data into bins and shows how many values fall in each bin.
2. **What does a histogram show?** The shape of the data: concentration, spread, skewness, gaps and possible outliers.
3. **What is skewness?** A measure of asymmetry in a distribution. In right skew the tail is on the right and mean > median. In left skew the tail is on the left and mean < median.

## How to Run
```bash
pip install pandas matplotlib seaborn jupyter
jupyter notebook distribution_analysis.ipynb
```
