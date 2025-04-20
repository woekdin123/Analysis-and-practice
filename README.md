# Analysis-and-practice
# Finding Outliers in Data

Outliers are data points that significantly deviate from the overall pattern of a dataset. Detecting outliers is crucial for data cleaning, anomaly detection, and improving model performance. Several statistical and machine learning-based methods can be used to identify outliers.

## 1. **Z-Score Method**

The Z-score measures how many standard deviations a data point is from the mean. Outliers are typically defined as points where:

$$\[
Z = \frac{X - \mu}{\sigma}
\]$$

Where:
- \( X \) is the data point,
- $$\( \mu \)$$ is the mean,
- $$\( \sigma \)$$ is the standard deviation.

A common threshold for identifying outliers is:
- $$\( |Z| > 3 \)$$ (for normally distributed data).

## 2. **Interquartile Range (IQR) Method**

![0_Zz3XmuErUXmIcy6C](https://github.com/user-attachments/assets/445eee15-4aeb-4f41-a21b-fcc9d9aaaa8c)

The IQR method is based on the quartiles of the dataset:

\[
IQR = Q3 - Q1
\]

Where:
- \( Q1 \) (first quartile) is the 25th percentile,
- \( Q3 \) (third quartile) is the 75th percentile.

A data point is considered an outlier if:
\[
X < Q1 - 1.5 \times IQR \quad \text{or} \quad X > Q3 + 1.5 \times IQR
\]

## 3. **Modified Z-Score Method**

For datasets with a non-normal distribution, a modified Z-score is used:

$$\[
M = \frac{0.6745 \times (X - \tilde{X})}{MAD}
\]$$

Where:
- $$\( \tilde{X} \)$$ is the median,
- \( MAD \) is the median absolute deviation:
  \[
  MAD = $$\text{median}(|X_i - \tilde{X}|)
  \]$$

Outliers are detected when \( |M| > 3.5 \).

## 4. **Boxplot Method**

Boxplots visually represent outliers using IQR. Any points outside the whiskers (1.5 × IQR rule) are outliers.

## 5. **Machine Learning-Based Methods**

### a) **Isolation Forest**
A tree-based method that isolates anomalies based on data partitioning.

### b) **Local Outlier Factor (LOF)**
Measures the local density deviation of a data point compared to its neighbors.

### c) **DBSCAN (Density-Based Clustering)**
Clusters points based on density and labels sparse points as outliers.

## Conclusion
Choosing the right method depends on the dataset distribution, size, and the nature of the problem. For normally distributed data, Z-score works well, whereas IQR is useful for skewed distributions. Machine learning-based methods are preferred for high-dimensional datasets.

---

