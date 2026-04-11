# Experiment 16: Basic Charts and Visual Encoding

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** A3  
**Date:** 08/04/2026  

---

## 1. Aim
To explore and implement basic data visualization techniques and visual encoding using Python libraries (Matplotlib and Seaborn) to analyze trends, distributions, comparisons, and relationships within datasets.

## 2. Introduction to Libraries Used
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, visualization tools provide an accessible way to see and understand trends, outliers, and patterns.

* **Pandas (`pd`):** Used for data manipulation and analysis. It allows data to be structured into a DataFrame, making it easy to pass into plotting functions.
* **Matplotlib (`plt`):** A comprehensive, low-level plotting library in Python used for creating static, animated, and interactive visualizations.
* **Seaborn (`sns`):** A high-level data visualization library based on Matplotlib. It provides a specialized interface for drawing attractive and informative statistical graphics.
* **NumPy (`np`):** Used for numerical computations, specifically in this experiment for calculating numerical ranges (`np.arange`) to position grouped bar charts correctly.

## 3. Common Utility Functions
Throughout the experiment, several functions are used repeatedly to format and display the graphs.

* `plt.title(label)`: Adds a title to the chart.
* `plt.xlabel(label)` / `plt.ylabel(label)`: Assigns labels to the X and Y axes, explaining what the data points represent.
* `plt.show()`: Renders and displays the current figure.
* `plt.figure(figsize=(width, height))`: Creates a new figure with specified dimensions.
* `plt.legend()`: Displays a legend on the plot, using the label parameters defined in the plotting functions.
* `plt.grid(axis='y')`: Adds grid lines to the graph (in this case, only along the Y-axis) to make reading values easier.

---

## 4. Step-by-Step Procedure and Plotting Functions

### Step 1: Data Preparation
* **Function:** `pd.DataFrame(data)`
* **Explanation:** Raw data is created using Python dictionaries. The DataFrame function converts this dictionary into a 2D tabular data structure (rows and columns), which is the standard format required by Matplotlib and Seaborn for seamless plotting.

### Step 2: Line Charts (Trend Analysis)
* **Purpose:** Line charts are used to visualize data that changes continuously over time (trends).
* **Function:** `plt.plot(x, y, marker, color, label)`
* **Explanation:** Plots the data points on the X and Y axes and connects them with a line. The `marker` argument (e.g., `'o'`, `'s'`) highlights individual data points with circles or squares. In the advanced line chart, multiple `plt.plot()` functions are called on the same figure to overlay different data series (Study Hours and Marks) for comparison.

### Step 3: Bar Charts (Comparison)
* **Purpose:** Bar charts are ideal for comparing categorical data or tracking changes across different groups.
* **Function:** `plt.bar(x, height, color, width)`
* **Explanation:** Generates vertical rectangles (bars) where the length is proportional to the value it represents.
* **Advanced Implementations:**
  * **Data Annotations:** The code iterates through the bars using a `for` loop. `bar.get_height()`, `bar.get_x()`, and `bar.get_width()` extract the exact dimensions of each bar. `plt.text()` is then used to explicitly print the numerical value on top of each bar.
  * **Grouped Bar Chart:** To place two bars side-by-side for the same category, `np.arange()` creates an array of numerical positions. The width is manually added or subtracted from the X-coordinates (`x - width/2` and `x + width/2`) to offset the bars so they do not overlap.

### Step 4: Histograms (Data Distribution)
* **Purpose:** Histograms group continuous data into distinct ranges (bins) to show the frequency distribution of a dataset.
* **Function:** `plt.hist(x, bins, edgecolor, alpha)`
* **Explanation:** Instead of plotting individual values, this aggregates data into bins (set to 3 in the experiment). The `edgecolor` highlights the borders of the bars, and `alpha` adjusts the transparency of the color.

### Step 5: Scatter Plots (Relationships/Correlation)
* **Purpose:** Scatter plots use Cartesian coordinates to display values for typically two variables, highlighting how one variable affects another (correlation).
* **Function:** `plt.scatter(x, y, c)`
* **Explanation:** Plots individual data points as dots without connecting them.
* **Conditional Visual Encoding:** In the advanced scatter plot, a new categorical column (`'Result'`) is evaluated using a list comprehension (`['lightcoral' if r=='Fail' else 'turquoise' ...]`). This dynamically assigns colors (`c=colors`) based on the data conditions, allowing visual separation of "Pass" and "Fail" categories.

### Step 6: Implementation using Seaborn
* **Purpose:** To replicate the above charts using Seaborn, which automatically handles styling, color palettes, and complex statistical calculations with simpler syntax.
* **Functions:**
  * `sns.lineplot(x, y, data)`: Plots a customized line chart directly from the DataFrame column names.
  * `sns.barplot(x, y, data)`: Plots a stylized bar chart.
  * `sns.scatterplot(x, y, data)`: Plots a stylized scatter plot.
  * `sns.histplot(data, bins, kde)`: Plots a histogram. The addition of `kde=True` (Kernel Density Estimate) is a significant feature—it overlays a smooth, continuous probability curve over the discrete bins to better visualize the distribution shape.

---

## 5. Conclusion
The experiment successfully demonstrates how visual encoding (mapping data to shapes, colors, and positions) transforms raw tabular data into interpretable graphics. Matplotlib provides foundational, granular control over every visual element, while Seaborn streamlines the process for complex, aesthetically pleasing statistical visualizations.
