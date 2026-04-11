# Theory for Experiment 17: Exploring Statistical and Specialized Data Visualization Techniques

## 1. Introduction to the Libraries Used
Data visualization is a crucial step in data analysis that helps in understanding patterns, trends, and outliers. This experiment utilizes four fundamental Python libraries:

* **NumPy (`np`)**: Used for numerical computing and generating synthetic data (arrays and random numbers).
* **Pandas (`pd`)**: Used for data manipulation and analysis, specifically through its DataFrame object which organizes data into a 2D tabular format.
* **Matplotlib (`plt`)**: The foundational plotting library in Python, used for creating static, interactive, and animated visualizations.
* **Seaborn (`sns`)**: A data visualization library built on top of Matplotlib that provides a high-level interface for drawing attractive and informative statistical graphics.

---

## 2. Data Generation and Manipulation Functions
Before visualizing data, synthetic datasets were generated using the following functions:

* `np.random.seed(seed_value)`: Ensures reproducibility. It initializes the random number generator so that the same sequence of random numbers is produced every time the code is run.
* `np.random.randint(low, high, size)`: Generates an array of random integers between the specified `low` (inclusive) and `high` (exclusive) bounds.
* `pd.DataFrame({...})`: Constructs a two-dimensional, size-mutable, and potentially heterogeneous tabular data structure containing labeled axes (rows and columns).
* `np.where(condition, x, y)`: Returns elements chosen from `x` or `y` depending on the condition. It functions like a vectorized if-else statement (used here to assign 'Approved' or 'Rejected' loan statuses).
* `df.corr()`: A Pandas DataFrame method that computes the pairwise correlation of columns, excluding NA/null values. It defaults to the Pearson correlation coefficient.
* `df.head()`: Returns the first 5 rows of the DataFrame, useful for quickly verifying the dataset structure.

---

## 3. Plotting and Visualization Functions

### General Matplotlib Configurations
* `plt.figure(figsize=(width, height))`: Creates a new figure object. The `figsize` parameter controls the dimensions of the plot in inches.
* `plt.title()`, `plt.xlabel()`, `plt.ylabel()`: Used to add a descriptive title and label the x and y axes, respectively.
* `plt.show()`: Renders and displays the constructed plot to the screen.
* `plt.legend()`: Places a legend on the axes to identify different data series.

### A. Area Plot* `plt.fill_between(x, y1, y2=0, ...)`: Fills the area between two horizontal curves. In this experiment, it is used to shade the region between the x-axis and the data points, creating an area plot.
    * **Parameters used:** `color` specifies the fill color, and `alpha` controls the transparency (0.0 to 1.0) so overlapping areas remain visible.

### B. Pie and Donut Charts


[Image of a pie chart]

* `plt.pie(x, ...)`: Plots a pie chart where the fractional area of each wedge is given by `x/sum(x)`.
    * **Parameters used:** `labels` assigns names to wedges, `autopct` formats the percentage values overlaid on the slices (e.g., `'%1.2f%%'` for two decimal places), and `explode` offsets specific slices from the center for emphasis.



[Image of a donut chart]

**Donut Chart Implementation:** Matplotlib does not have a native donut chart function. It is created by drawing a standard pie chart and then overlaying a white/colored circle in the center.
* `Circle((x, y), radius, fc)`: Creates a circular patch.
* `plt.gcf().gca().add_artist(circle)`: Gets the current figure (`gcf`), gets the current axes (`gca`), and adds the circle patch to the plot, masking the center of the pie chart.

### C. Boxplot (Outlier Detection)


[Image of a boxplot]

* `sns.boxplot(x=...)` / `plt.boxplot(...)`: Draws a box plot to show distributions with respect to categories. It visualizes the five-number summary (minimum, first quartile, median, third quartile, and maximum) and helps in visually identifying outliers (plotted as individual points beyond the "whiskers").

### D. Heatmap (Correlation Matrix)

* `sns.heatmap(data, ...)`: Plots rectangular data as a color-encoded matrix. Highly effective for visualizing correlation matrices.
    * **Parameters used:** `annot=True` writes the data value in each cell, and `cmap` specifies the colormap (e.g., `'coolwarm'`) to visually distinguish between positive, negative, and neutral correlations.

### E. Bubble Plot (Advanced Scatter)

A bubble plot is an extension of a scatter plot where a third dimension of data is represented by the size of the markers.
* `plt.scatter(x, y, s, c, ...)`: Draws a scatter plot.
    * **Parameters used:** `s` dictates the size of the marker (creating the "bubble"), `c` dictates the color, `cmap` applies a colormap to the values, and `alpha` adds transparency.
* `plt.colorbar()`: Adds a color scale next to the plot to map the colors of the bubbles to their corresponding numerical values.
* `sns.scatterplot(..., size, hue, sizes, palette)`: The Seaborn equivalent, which handles legends and scaling automatically. `size` maps the bubble sizes to a variable, and `hue` maps colors to a variable.

### F. Histogram

* `plt.hist(x, bins, ...)`: Computes and draws the histogram of array `x`. It groups numerical data into continuous intervals (bins) to visualize the underlying frequency distribution.
    * **Parameters used:** `bins` defines the number of equal-width bins, `color` fills the bars, and `edgecolor` outlines the bars for better visibility.

---

## Summary Statement for Journal
By utilizing these functions, the experiment successfully demonstrated how to transform raw, tabular data into meaningful visual representations. Functions like heatmap and boxplot provided statistical insights (correlations and outliers), while area, pie, and bubble plots facilitated the comparative analysis of categorical and multi-dimensional numerical data.
