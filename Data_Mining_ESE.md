#  Data_Mining_ESE
> Author : Aaron Augustine

> Star the gist so that I can get a consensus on how many people are using this resource
> 
[Github Repo Link for all ESE Notes](https://github.com/ToothlessRider/ESE_Notes.git)

# Table of Contents 
1. [Previous Year Questions](#previous-year-questions)
2. [Data Warehouse, Online Analytical Processing](#dw-olap)



## Previous Year Questions

Q1. a. 
**Do as directed:**
1. **The measure of skewness coefficient is negative then the relation between mean, median and mode is given by**

Ans. 1. 
When the skewness coefficient is negative, it indicates that the distribution of data is **negatively skewed (or left-skewed)**. In a negatively skewed distribution, the tail on the left side is longer than the right side.

The relationship between the mean, median, and mode in a negatively skewed distribution is typically as follows:

$\text{Mean} < \text{Median} < \text{Mode}$

In summary:
- The **mean** is the lowest value among the three measures of central tendency.
- The **median** is in the middle.
- The **mode** is the highest value.

This pattern reflects the fact that in a negatively skewed distribution, the mean is pulled to the left by the longer tail of the distribution, while the mode remains the peak or highest frequency point, and the median lies between the mean and mode.

**![](https://lh7-us.googleusercontent.com/KK8sA2yXyh8e0yGfEZuZCvMNuHCDliHNAijl79bntzHtGDLPlqM8uXMsaNkTZQzazDVX-C9z8MHS8rThP3y8plqa0tPQSVUhd9_BmZq0l1VUVhMN-0RQPpl9YSQvTQY6MK-2XyKuUdBpcDt3HZEXTiQ)**

<hr>

2. **What do the two axes of the line graphs represent and what is the relation between them.**

Ans.
A line graph typically has:

- **X-axis (Horizontal)**: Represents the independent variable (e.g., time, age).
- **Y-axis (Vertical)**: Represents the dependent variable (e.g., sales, growth).

The relationship shown can be:
- **Positive**: Upward trend, indicating the dependent variable increases as the independent variable increases.
- **Negative**: Downward trend, indicating the dependent variable decreases as the independent variable increases.
- **No Relationship**: Flat or no clear trend.

Example : The following is a graph of temperature versus time where time is the independent variable and temperature is being represented with respect to different times in the day

**![](https://lh7-us.googleusercontent.com/QTAXvvopf5vDbQTJvzg_sSesGjN8pVn9HgafmfUkXmTVsYejd12Eb84-LhBhBTtj-wt8du0t0_DjfDTaMdGwrETZT4hs3i2qCQCblgnzH9VoGUkMPbwROCRWSqwungAM2JaLogCHbqvjRx-xSKVDyR4)**

<hr>

3. **Comment on symmetricity of proximity matrix.**

Ans.
A proximity matrix is a square matrix used in various fields such as statistics, data analysis, and machine learning to represent the distances or similarities between pairs of objects. The symmetricity of a proximity matrix depends on the nature of the measure used to compute the proximities.

### Symmetricity of a Proximity Matrix

1. **Symmetric Proximity Matrix**:
   - A proximity matrix is symmetric if the measure of proximity (distance or similarity) between any two objects is the same regardless of the order of the objects.
   - In mathematical terms, a proximity matrix $P$ is symmetric if $P_{ij} = P_{ji}$ for all $i$ and $j$.
   - Common examples of symmetric proximity matrices include those based on Euclidean distance, cosine similarity, or Pearson correlation coefficient.

   **Example**:
 $P = \begin{pmatrix}
   0 & 2 & 3 \\
   2 & 0 & 4 \\
   3 & 4 & 0
   \end{pmatrix}$
  
   This matrix is symmetric because $P_{ij} = P_{ji}$ for all $i$ and $j$.

2. **Asymmetric Proximity Matrix**:
   - A proximity matrix is asymmetric if the measure of proximity between any two objects can differ depending on the order of the objects.
   - In mathematical terms, a proximity matrix $P$ is asymmetric if there exists at least one pair of objects $i$ and $j$ such that $P_{ij} \neq P_{ji}$.
   - Asymmetric proximity matrices are less common but can arise in specific contexts, such as when measuring directed relationships or asymmetric similarity measures.

   **Example**:
$P = \begin{pmatrix}
   0 & 2 & 3 \\
   1 & 0 & 4 \\
   5 & 3 & 0
   \end{pmatrix}$
   
   This matrix is asymmetric because $P_{12} \neq P_{21}$, $P_{13} \neq P_{31}$ , etc.

### Interpretation and Applications

- **Symmetric Proximity Matrices**: These are used in many standard clustering and multidimensional scaling techniques, where the relationship between objects is assumed to be mutual and undirected.
  
- **Asymmetric Proximity Matrices**: These are used in specialized contexts where the relationship is directional, such as web page link analysis (PageRank), certain types of ecological data, or user preference data where the similarity may not be mutual.

### Conclusion

The symmetricity of a proximity matrix is determined by whether the measure used to compute the proximities is symmetric or asymmetric. Symmetric proximity matrices are more common and are used in many standard data analysis techniques, whereas asymmetric matrices are used in more specialized applications.

<hr>

4. **Give the strength and limitations of average clustering.**

Ans.

~~Not in ppts~~
### Strengths of Average Clustering

1. **Simple to Understand and Implement**: The algorithm is straightforward and easy to execute.
2. **No Need for Predefined Cluster Number**: The method does not require specifying the number of clusters in advance.
3. **Produces a Dendrogram**: Provides a visual representation of cluster hierarchy and relationships.
4. **Handles Various Data Types**: Compatible with different distance or similarity measures.
5. **Less Sensitive to Outliers**: Considers average distances, reducing the impact of noise and outliers.

### Limitations of Average Clustering

1. **Computational Complexity**: High time and space complexity, making it impractical for large datasets.
2. **Lack of Scalability**: Inefficient for very large datasets due to computational demands.
3. **Assumes Hierarchical Structure**: May not be suitable if the data lacks a hierarchical structure.
4. **Sensitive to Distance Measures**: Results vary with different distance or similarity measures.
5. **No Objective Cluster Number**: Determining the optimal number of clusters is subjective.
6. **Non-Intuitive Clusters**: Can produce clusters that are less meaningful compared to other methods.

<hr>

5. **With an example explain how initial seed plays an important role in
clustering.**

Ans.
The initial seed in clustering, particularly in methods like k-means, plays a crucial role because it significantly influences the resulting clusters. Here's a detailed example to illustrate this:

### Example: k-Means Clustering

#### Scenario

Suppose we have a dataset of points in a 2-dimensional space:

$\{(1, 2), (2, 1), (1, 1), (10, 10), (10, 11), (11, 10)\}$

We want to cluster these points into two clusters (k=2).

#### Initial Seed Selection

1. **Random Seed 1**:
   - Initial centroids: $(1, 2)$ and $(10, 10)$

   Iteration 1:
   - Assign points to nearest centroid:
     - Cluster 1: $(1, 2), (2, 1), (1, 1)$
     - Cluster 2: $(10, 10), (10, 11), (11, 10)$

   - Compute new centroids:
     - New centroid for Cluster 1: $((1.33, 1.33)$
     - New centroid for Cluster 2: $(10.33, 10.33)$

   The algorithm continues iterating, but these clusters are stable and represent the natural grouping in the data.

2. **Random Seed 2**:
   - Initial centroids: $(1, 2)$ and $(2, 1)$

   Iteration 1:
   - Assign points to nearest centroid:
     - Cluster 1: $(1, 2), (1, 1)$
     - Cluster 2: $(2, 1), (10, 10), (10, 11), (11, 10)$

   - Compute new centroids:
     - New centroid for Cluster 1: $(1, 1.5)$
     - New centroid for Cluster 2: $(8.25, 8)$

   Iteration 2:
   - Reassign points to nearest centroid:
     - Cluster 1: $(1, 2), (1, 1)$
     - Cluster 2: $(2, 1), (10, 10), (10, 11), (11, 10)$

   - The clusters become distorted and may not represent the natural grouping well, leading to incorrect clustering.

### Explanation

- **Initial Seed 1** leads to a natural separation of the points into two clusters that match intuitive groupings (one around $(1, 2)$ and one around $(10, 10)$ ).
- **Initial Seed 2** causes the algorithm to start with suboptimal centroids, leading to an unstable and incorrect clustering result.

### Conclusion

The initial seed selection is critical in k-means clustering because it affects the convergence and final clusters. Poorly chosen initial seeds can lead to suboptimal clustering results, while good initial seeds can lead to more accurate and meaningful clusters. This is why techniques like k-means++ are used to select better initial seeds to improve the performance and results of the k-means algorithm.

<hr>

Q1. b. **Calculate the dissimilarity between jack and mary using jaccard's similarity. Also give the contingency table for the same.**
| Name|Gender|Fever|Cough|Test-1|Test-1|Test-3|Test-4|
|--|--|--|--|--|--|--|--|
|Jack|M|Y|N|P|N|N|N|
|Mary|F|Y|N|P|N|P|N|
|Jim|M|Y|P|N|N|N|N|

Ans.


<hr>

Q1. c. **Differentiate between**
1. **Intrinsic and extrinsic measures**

Ans.
| Intrinsic | Extrinsic |
| -- | -- |
| 

<hr>

2. **Cohesion and separation**
3. **Symmetric and asymmetric attributes. Give an example**
4. **Agglomerative and divisive clustering**

Ans.


<hr>

Q2. a. **Consider the following data, where the return tells us if it's a up or down the characteristics required for the same. Using the following table, create a decision tree and predict whether return is up or down for the following tupl (Use Gini index as criterion). Find the class of (positive, Iow, low)**

| Past Trend | Open Interest | Trading Volume |Return | 
| -- | -- | -- | -- |
|Positive| Low | High | Up |
|Negative| High| Low | Down| 
|Positive| Low | High | Up |
|Positive| High | High | Up |
|Negative| Low | High| Down| 
|Positive| Low | Low | Down |
|Negative| High| High | Down| 
|Negative| Low| High | Down| 
|Positive| Low | Low | Down |
|Positive| High| High | Up |

Ans.

<hr>

Q2. b. **Explain briefly various measures associated with attribute selection?**

Ans. 

<hr>

Q2. c. **Suppose we have data on few individuals randomly surveyed. The data gives the responses towards interests to promotional offers made in the areas of Finanace, Travel, Reading, and Health. Sex is the output attribute to be predicted. <br>Apply Naive Bayesian classification algorithm to classify the new instance. (Finance = No,Travel = Yes, Reading = Yes, Health = No).**

| Finance | Travel | Reading | Health | Sex | 
| -- | -- | -- | -- | -- |
| Yes | No | Yes | No | Male |
| Yes | Yes | No | No | Male |
| No | Yes | Yes | Yes | Female |
| No | Yes | No | Yes | Male |
| Yes | Yes | Yes | Yes | Female |
 Yes | No | No | No | Female |
| Yes | No | No | No | Male |
| Yes | Yes | No  | No | Male |
| No | No | No | Yes | Female |
| Yes | No | No | no | Male |

Ans. 


<hr>

Q3. a. **Define the terms support, confidence, and lift. Discuss the importance of Association Rule Mining.**

Ans. 

<hr>

Q3. b. **Explain data mining as a ste in knowledge discovery process.**

Ans. 

<hr>

Q3. c. **Find all the faults in the following datasets.**
| # | id } Name | Birthday | Gender | is Teacher? | #stud | country | city | 
| -- | -- | -- | -- | -- | -- | -- | -- | 
1 | 111 | John | 21/10/90 | M | 0 | 0 | Ireland | Dublin | 
| 2 | 222 | Mary | 12/10/78 | F | 1 | 15 | Iceland | | 
| 3 | 333 | Alice | 19/04/00 | F | 0 | 0 | Spain | Madrid | 
| 4 | 444 | Mark | 1/11/97 | A | 0 | 0 | France | Paris | 
| 5 | 555 | Alex | 15/03/00 | M | 1 | 23 | Germany | Berlin | 
| 6 | 666 | Peter | 21/31/83 | M | 1 | 10 | Italy | Rome | 
| 7 | 777 | Calvin | 5/5/48 | F | 0 | 0 | Italy | Italy | 
| 8 | 888 | Rihanna |3/8/48 | F | 0 | 0 | Portugal | Libson |
| 9 | 999 | Anne | 5/9/42 | M | 0 | 5 | Switzerland | Geneva |

Ans. 

<hr>

Q3. d. **Discuss the various datamining tasks. What is the need for data mining? Briefly discuss the various roblems associated with data mining**

Ans. 

<hr>

Q4. a. **Compare and contrast bagging, boosting and stacking ensemble techniques.**

Ans. 

<hr>

Q4. b. **Discuss the various approaches used to find optimal number of dusters**

Ans. 

<hr>

Q4. c. **Calculate kappa coefficient for the following confusion matrix. Refrence Data**

| | Building | Dessert | Forest | Water | Building |
| -- | -- | -- | -- | -- | -- |
| Bareland | 15 | 1 | 3 | 2 | 1 | 
| dessert | 2 | 19 | 0 | 0 | 2 |
| Forest | 1 | 2 | 17 | 1 | 0 |
| Water | 1 | 0 | 3 | 10 | 3 | 
| Water Building | 3 | 2 | 0 | 2 | 10 | 

Ans. 

<hr>

Q4. d. **Discuss the various ways in which spatial data can be represented. Use appropriate figures to explain.**

Ans. 

<hr>

Q5. a. **Give an algorithm for K-means clustering. Consider the following 5
points { $x_1, x_2, x_3, x_4, x_5$ } with the following as a two dimensional sample: 
$x_1= (0,2), x_2 = (1,0), x_3 = (2,1), x_4 = (4,1), x_5 = (5,3)$  for clustering.<br> Illustrate K-means algorithm on the above dataset. The required number of
cluster is 2. Initially the cluster are formed from random distribution of samples <br> $C_1 = \{x_1, x_2, x_4\} \text { and } C_2 = \{ x_3, x_5\}$**

Ans. 

<hr>

Q5. b. **Discuss different ways of measuring inter-cluster similarity?**

| | A | B | C | D | E | F | 
| -- | -- | -- | -- | -- | -- | -- |
| A | 0 | 4 | 25 | 24 | 9 | 7 |
| B | 4 | 0 | 21 | 20 | 5 | 3 | 
| C | 25 | 21 | 0 | 1 | 16 | 18 | 
| D | 24 | 20 | 1 | 0 | 15 | 17 |
| E | 9 | 5 | 16 | 15 | 0 | 2 | 
| F | 7 | 3 | 19 | 17 | 2 | 0 | 

**For the above distance matrix, draw a dendogram using complete link inter- clustering.**
Ans. 

<hr>

Q5. c. **Consider the data set of 7 points of 2 dimension.<br> $Cluster_1$ = {(11, 14), (11, 13), (12, 13)} and <br>$Cluster_2$ = {(2,5), (3,4), (5, 4), (1, 3)} Calculate silhouette value for a point (12,13).**

Ans. 

<hr>


## Dw OLAP
Q1. **What is a Data Warehouse ? Give an example**

Ans. 
A decision support database that is maintained separately from the organization’s operational database

Support information processing by providing a solid platform of consolidated, historical data for analysis.

> “A data warehouse is a subject-oriented, integrated, time-variant, and nonvolatile collection of data in support of management’s  decision-making process.”

Data warehousing is an important preprocessing step for data mining, where we take heterogeneous databases ( i.e. different formats, id's, etc ) and do the following procedures on them : 
- Data selection
- Data cleaning
- Data intergration
- Data summarization 

Which then allows it to become a *Data Warehouse*
**![](https://lh7-us.googleusercontent.com/oGHuKKfioHFEjh60Pl1svCLXOF3MGCCkqIhNxNTcLg9sL8a9TsnVB_zhPipTurdEuHQr7dKpQgIqudW_TstuQgSgL0bgWqfJ0-gnD-1-PmiRCN0WdfmuX2XnCRNrKYZs1iQdcArePd6KtR4cyZIiVo0)**

It also provides OLAP tools for **interactive multidimensional data analysis**

Example : 
- Here you have two different databases that were made in different countries, so the names of the column attributes might differ, along with the number of columns 

**![](https://lh7-us.googleusercontent.com/IA4T_DLCLPZr6ejcDXEbkTGrfg2e_rTET6xg3c3hbH7fn8GD6N2aCG13peMFajxTSoVJ5-G8RLYLWH9GSqHS_0B73v1W-wR41wY47rCdmOHYoSFPdi3S59eRoOWintwKSfVTJQurYkmNFA8-pmeZLRY)**

<hr>

Q2. **What are the different steps in creating a data warehouse ?**

Ans. 
#### Data Selection
- Only data which are important for analysis are selected. ( employee info, dept, etc ) 
- *Subject Oriented*

#### Data Cleaning
- Tuples which are incomplete or logically inconsistent are cleaned

#### Data Integration
- Consistency of attribute names
- Consistency of attribute types
- Consistency of values
- Integration of data

#### Data Summarization
- Values are summarized according to the desired level of analysis
- For example, in the HK database, they give the time unit as well, but we are only interested in the day

<hr>

Q2. **Differentiate between OLTP and OLAP**
Ans. 

| Online Analytical Processing | Online Transaction Processing |
| -- | -- | 
| 





