<h1>📊 Descriptive Statistics in Python</h1>

<p>
Descriptive statistics summarize and describe the basic features of a dataset.
Common statistical measures include mean, median, mode, variance, standard deviation,
range, skewness, kurtosis, and percentiles.
</p>

<h2>📁 Dataset Example</h2>

<pre><code>
import pandas as pd

df = pd.DataFrame({
    "A": [10, 20, 30, 40, 50],
    "B": [5, 8, 6, 7, 9],
    "C": [100, 120, 140, 160, 180]
})
</code></pre>

<h2>📌 Basic Descriptive Statistics</h2>

<pre><code>
df.describe()
</code></pre>

<h3>📋 Output Includes:</h3>
<ul>
    <li>Count</li>
    <li>Mean</li>
    <li>Standard Deviation</li>
    <li>Minimum</li>
    <li>25%, 50%, 75% Percentiles</li>
    <li>Maximum</li>
</ul>

<h2>📌 Individual Statistical Measures</h2>

<table border="1" cellspacing="0" cellpadding="6">
    <tr>
        <th>Measure</th>
        <th>Code</th>
    </tr>
    <tr>
        <td>Mean</td>
        <td><code>df.mean()</code></td>
    </tr>
    <tr>
        <td>Median</td>
        <td><code>df.median()</code></td>
    </tr>
    <tr>
        <td>Mode</td>
        <td><code>df.mode()</code></td>
    </tr>
    <tr>
        <td>Standard Deviation</td>
        <td><code>df.std()</code></td>
    </tr>
    <tr>
        <td>Variance</td>
        <td><code>df.var()</code></td>
    </tr>
    <tr>
        <td>Minimum</td>
        <td><code>df.min()</code></td>
    </tr>
    <tr>
        <td>Maximum</td>
        <td><code>df.max()</code></td>
    </tr>
    <tr>
        <td>Range</td>
        <td><code>df.max() - df.min()</code></td>
    </tr>
    <tr>
        <td>Quantiles</td>
        <td><code>df.quantile([0.25, 0.5, 0.75])</code></td>
    </tr>
</table>

<h2>📌 Skewness & Kurtosis</h2>

<ul>
    <li><code>df.skew()</code> – Skewness</li>
    <li><code>df.kurt()</code> – Kurtosis</li>
</ul>

<h2>📌 Correlation & Covariance</h2>

<ul>
    <li>Correlation → <code>df.corr()</code></li>
    <li>Covariance → <code>df.cov()</code></li>
</ul>

<h2>📌 Complete Summary Function</h2>

<pre><code>
def full_summary(data):
    summary = {
        "Mean": data.mean(),
        "Median": data.median(),
        "Mode": data.mode().iloc[0],
        "Std Dev": data.std(),
        "Variance": data.var(),
        "Min": data.min(),
        "Max": data.max(),
        "Range": data.max() - data.min(),
        "Skewness": data.skew(),
        "Kurtosis": data.kurt()
    }
    return pd.DataFrame(summary)

full_summary(df)
</code></pre>

<h2>📌 Visualization (Optional)</h2>

<h3>Histogram</h3>
<pre><code>
df.hist(figsize=(8,6))
plt.show()
</code></pre>

<h3>Boxplot</h3>
<pre><code>
df.plot(kind='box', figsize=(6,5))
plt.show()
</code></pre>
