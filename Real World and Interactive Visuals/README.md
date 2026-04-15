# Experiment 18: Real World and Interactive Visualizations

**Name:** Khush Chauhan  
**PRN:** 25070123062  
**Batch:** A3  
**Date:** 10/04/2026

---

## 🎯 Aim
To understand, design, and implement various real-world and interactive data visualizations—including **Treemaps, Dendrograms, Venn Diagrams, Sankey Diagrams, 3D Scatter Plots, and Radar Charts**—using Python libraries such as Plotly, Matplotlib, and SciPy.

## 📖 Introduction
In modern data analytics, standard static graphs are often insufficient for conveying complex, multi-dimensional, or hierarchical data. Real-world visualizations like Sankey diagrams and Treemaps help illustrate flows and proportions effectively. Interactive visualizations, specifically those powered by **Plotly**, allow users to hover, zoom, and pan across the data, providing a deeper and more intuitive understanding of underlying patterns.

---

## 📊 Visualizations Implemented & Theoretical Concepts

### 1. Treemap (Company Department Budget)
* **Concept:** Displays hierarchical data as nested rectangles. The area of each rectangle is proportional to its specific quantitative value.
* **Theory:** Treemaps utilize space-filling tiling algorithms (like the squarified algorithm) to maximize space utilization. They are particularly powerful because they can represent two dimensions of data simultaneously: node size (e.g., total budget) and node color (e.g., year-over-year growth), allowing for rapid identification of extremes within complex hierarchies.
* **Library:** `plotly.express`
* **Key Functions:** `px.treemap()`

### 2. Dendrogram
* **Concept:** A tree-like diagram used to visualize hierarchical clustering, showing the sequence of merges or splits.
* **Theory:** Rooted in agglomerative (bottom-up) clustering, a dendrogram visually represents the pairwise distance (often Euclidean) between data points. The y-axis denotes the linkage distance at which clusters merge. By drawing a horizontal line across the dendrogram at a specific height, analysts can determine the optimal number of distinct clusters based on data dissimilarity.
* **Library:** `scipy.cluster.hierarchy`, `matplotlib.pyplot`
* **Key Functions:** `linkage(method='ward')`, `dendrogram()`

### 3. Venn Diagram
* **Concept:** Illustrates logical relationships and overlaps between different sets of items.
* **Theory:** Based on mathematical Set Theory, Venn diagrams represent universal sets and subsets using closed curves. They map out unions (elements in either set), intersections (elements in both sets), and complements. In data science, they are crucial for evaluating Boolean logic (AND, OR, NOT) and identifying overlapping cohorts or mutually exclusive categories.
* **Library:** `matplotlib_venn`, `matplotlib.pyplot`
* **Key Functions:** `venn2()`

### 4. Sankey Diagram (Student Flow)
* **Concept:** Depicts the flow from one set of values to another, where the width of the arrows represents the flow quantity.
* **Theory:** Sankey diagrams act as directed acyclic graphs (DAGs) that rely on the principle of conservation of mass or energy—meaning the total input into a node typically equals the total output. They map state transitions over time or stages, making bottlenecks, drop-offs, and major pathways instantly visible through the proportional width of the links.
* **Library:** `plotly.graph_objects`
* **Key Functions:** `go.Sankey()`

### 5. 3D Scatter Plot (Student Performance)
* **Concept:** Extends 2D plotting into three dimensions (X, Y, Z) to identify clusters in multidimensional spaces.
* **Theory:** Adding a third spatial dimension allows analysts to map three continuous variables simultaneously. By incorporating size and color into the data points, a 3D scatter plot can effectively represent up to 5 dimensions of data. The interactivity provided by libraries like Plotly is theoretically vital here to overcome "spatial occlusion" (where closer points hide points behind them) by allowing users to rotate the axes.
* **Library:** `plotly.express`
* **Key Functions:** `px.scatter_3d()`

### 6. Radar Chart (Skill Assessment)
* **Concept:** Also known as a Spider Chart, it displays multivariate data on axes radiating from a central point.
* **Theory:** Radar charts map multiple quantitative variables on a polar coordinate system. To be mathematically accurate and visually fair, the variables must often be normalized to a common scale. By connecting the plotted points into a polygon, the chart creates a geometric "profile" of a subject, making it incredibly easy to compare individual profiles against a baseline, average, or an ideal target.
* **Library:** `plotly.graph_objects`
* **Key Functions:** `go.Scatterpolar()`

---

## 🛠️ Tech Stack
| Library | Primary Use Case in Experiment |
| :--- | :--- |
| **Plotly** | High-end interactive visualizations (Sankey, Radar, Treemap, 3D) |
| **Matplotlib** | Foundational static plotting and Set Theory visualizations (Venn) |
| **SciPy** | Statistical functions and hierarchical clustering calculations |
| **Pandas** | Data structure creation, aggregation, and manipulation |

---

## 💡 Conclusion
Through this experiment, we successfully implemented advanced visual representations of data, blending statistical theory with modern graphic techniques. We observed that while **Matplotlib** provides strong foundational tools for static and mathematically rigorous plots (like Dendrograms and Venn Diagrams), **Plotly** offers the superior interactivity needed to navigate multi-dimensional spaces and complex hierarchies, which is essential for modern exploratory data analysis (EDA) and dynamic dashboarding.
