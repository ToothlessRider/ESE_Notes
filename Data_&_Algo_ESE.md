#  Data_&_Algo_ESE
> Author : Aaron Augustine

> Star the gist so that I can get a consensus on how many people are using this resource
> 
[Github Repo Link for all ESE Notes](https://github.com/ToothlessRider/ESE_Notes.git).


## Previous Year Questions 
Q1. a. **An algorithm has two phases. The first phase, initialization, takes time O(n^3^). The second phase, which is the main computation, takes time O(n^2^). What is the most accurate description of the complexity of the overall algorithm**
Ans. 
1.  The initialization phase takes $O(n^3)$time.
2.  The main computation phase takes $O(n^2)$time.

The total time complexity 𝑇(𝑛) of the algorithm is the sum of the time complexities of both phases:

$T(n) = O(n^3)+O(n^2)$

When adding time complexities, the term with the highest order of growth dominates, because it grows faster than the others as 𝑛 increases. Here, $O(n^3)$grows faster than $O(n^2)$.

Thus, the most accurate description of the overall complexity of the algorithm is:

$T(n)=O(n^3)$

This is because the $O(n^3)$term will dominate the $O(n^2)$ term for sufficiently large 𝑛.

Q1. b. **Suppose we have an O(n) time algorithm that finds the median of an unsorted array. Now consider a QuickSort implementation where we first find the median using the above algorithm, then use the median as a pivot. What will be the worst-case time complexity of this modified QuickSort?**
Ans.
To determine the worst-case time complexity of the modified QuickSort algorithm that uses the median as the pivot, let's analyze the steps involved:

1.  **Finding the Median**: The given algorithm finds the median of an unsorted array in 𝑂(𝑛) time.
2.  **Partitioning around the Median**: Once the median is found, it is used as the pivot to partition the array. This partition step is 𝑂(𝑛)

In QuickSort, after partitioning, the array is divided into two subarrays, each approximately half the size of the original array because we are using the median as the pivot. This ensures that the array is always evenly split, which is ideal for QuickSort.

Let's denote the time complexity of the modified QuickSort algorithm as 𝑇(𝑛)

The recurrence relation for this modified QuickSort algorithm can be written as: 𝑇(𝑛)=𝑂(𝑛)+𝑇(𝑛/2)+𝑇(𝑛/2)
Here, 𝑂(𝑛) represents the time taken to find the median and partition the array, and the two 𝑇(𝑛/2) terms represent the recursive calls on the two subarrays.

Simplifying the recurrence relation, we get: 𝑇(𝑛)=𝑂(𝑛)+2𝑇(𝑛/2)

This is a standard recurrence relation that can be solved using the Master Theorem. For the recurrence: 𝑇(𝑛)=𝑎𝑇(𝑛𝑏)+𝑓(𝑛)

where 𝑎=2, 𝑏=2, and 𝑓(𝑛)=𝑂(𝑛)


**![](https://lh7-us.googleusercontent.com/bMc3F40pftboBYm4ec5mbZeKgbzTRUz8yX7RRCQwJBwYicSiau5PKB6c2StYtSWECT0K-C0qR0PUaFQqWNwbOoqkVXLaVc-HNj_S5jKjDPM84-NJidh53tl3hs58xAdgYOJxWqQ_MVuyP_6SkZdmlRg)**
**![](https://lh7-us.googleusercontent.com/HwF_cjaXQlFtthILrwBKNPHOoEWbLDGnAHP5-rEHI4ZX48PCA99S3Zrs15Xr5xd6QKcY5Sn22UfZUPP5TUbABmG9Wzzni6CXd2_eXlwSzk4PAIn7nCAXGwBcTxkYhRV20C0jBNAQVYinBAF0rE1UbPA)**

According to the Master Theorem for this case, the time complexity is: 𝑇(𝑛)=𝑂(𝑛log⁡𝑛)

Therefore, the worst-case time complexity of the modified QuickSort algorithm that uses the median as the pivot is 𝑂(𝑛log⁡𝑛)

<hr>

Q2. a.**Suppose you are playing game of shooting balloon. You expect to shoot n
balloons in the board, assuming you are sharpshooter, 100% hit. There are two
scenarios, you need find the appropriate Big Oh notation for each scenario. In
these problems, one unit of work is shooting one balloon.
(i). Scenario 1: For every 2 balloons you are able to shoot, one new balloon is inserted in the board. So, if there were 20 balloons, after you shoot the first 2, there are 19 on the board. After you shoot the next 2, there are 18 on the board. How many balloons do you shoot before the board is empty?**

Ans. 
1.  **Initial Conditions**:
- Let 𝑛 be the initial number of balloons on the board.
- You shoot balloons two at a time, and for every two balloons you shoot, one new balloon is added.

2.  **Step-by-Step Process**:
- Initially, there are n balloons.
- After shooting 2 balloons, 1 new balloon is added, so the number of balloons decreases by 1. The board now has 𝑛−1 balloons.
- After shooting another 2 balloons, another balloon is added, reducing the count by 1 again. The board now has 𝑛−2 balloons.
- This process continues until all the balloons are gone.

3.  **Iterations**:
- Each iteration involves shooting 2 balloons and having 1 new balloon added.
-  After each iteration, the total number of balloons decreases by 1.

4.  **Total Iterations**:
- To reduce the number of balloons from 𝑛 to 0, you will need 𝑛 iterations because each iteration reduces the count by 1.

6.  **Total Number of Balloons Shot**:
- In each iteration, you shoot 2 balloons.
- Therefore, the total number of balloons shot is 2×𝑛.

### Conclusion:

The total number of balloons shot before the board is empty is proportional to the initial number of balloons times 2. Therefore, the Big-O notation for the number of balloons you need to shoot before the board is empty is:
>O(n)

<hr>

Q2. a. (ii). **Scenario 2 for the above problem of shooting the balloon: By the time you have shoot the first n balloons, n-I new balloons have been inserted on the board. After shootng those n-1 balloons, there are n-2 new balloons are inserted on the board. After checking out those n-2 balloons . there are n-3 new balloons on the board. This same pattern continues until on new balloon are inserted on the board. How many total balloons do you shoot before the board is empty?** 

Ans. 




<hr>

Q2. b. **Assuming you had an antique computer that could perform one comparison
every 1/1 ,OOO of a second, an insertion sort of 10,000 items should take about 7 hours. Calculate the minimum amount of time taken to sort 250 elements**

Ans. 
Given that an insertion sort of 10,000 items takes about 7 hours, we can directly calculate the time it takes to sort 250 elements using linear interpolation.

If sorting 10,000 elements takes 7 hours, then sorting 1 element would take:

$\frac{7 hours}{10,000 elements} = \frac{x hours}{1 element}$

Solving for 𝑥:

$x = \frac{7 \times 1 }{10,000}\text{ hours per element}$


Now, we can use this to find out how long it takes to sort 250 elements:

$\text{Time to sort 250 elements} = \frac{250 \times 7}{10,000} \text{ hours}$

$\text{Time to sort 250 elements} = \frac{1750}{10,000} \text{ hours}$

$\text{Time to sort 250 elements} = 0.175 \text{ hours}$

So, sorting 250 elements using insertion sort would take approximately 0.175 hours, or 10.5 minutes.

<hr>

Q2. c. **Write the time complexity of the following algorithms.**
(i)
```
int value = 0;
for(int i = 0; i < n; i++) {
    for(int j = 0; j < n; j++) {
        value += l;
    }
}

```
Ans. 
(i)The total number of operations is 𝑛×𝑛=𝑛^2^
> Time complexity = $O(n^2)$

<hr>

(ii)
```
int main() {
    int i, n = 8;
    for (i = 2; i <= n; i = pow(i, 2)) {
        cout << "Hello World !!!\n";
    }
    return 0;
}

```
Ans. 
(ii) The loop condition 𝑖<=𝑛 fails when 𝑖=16 for 𝑛=8. The number of iterations is determined by how many times you can square 𝑖 before it exceeds 𝑛. This is approximately log⁡log⁡𝑛 times.
> TIme Complexity = O(loglogn)

<hr>

(iii)
```
void function(int n) {
    int count = 0;
    for (int i = n / 2; i <= n; i++) {
        for (int j = 1; j <= n; j = 2 * j) {
            for (int k = 1; k <= n; k = k * 2) {
                count++;
            }
        }
    }
}

```
Ans. 

(iii) The total number of operations is: 𝑂(𝑛)×𝑂(log⁡𝑛)×𝑂(log⁡𝑛)=𝑂(𝑛log^⁡2^𝑛)

> Time Complexity = 𝑂(𝑛log⁡^2^𝑛)

<hr> 

Q3. **What is the order of each of the following tasks? Choose from 0(1), O(log2 n),  O(n), O(nlog2 n), O(n2), O(2n)...etc; each order may appear more than once.)
(i) What is the time complexity of quicksort on already sorted data elements with the last element chosen as a pivot.
(ii) What is the runtime of Dijkstra's algorithm when the implementation is based on a binary heap (V — number of vertices, E — number of edges)?
(iii) What is the best case time complexity of selection sort?
(iv) What is the time complexity of the Breadth First Search using adjacency list
is
(v) What is the space complexity of the Depth First Search?**

Ans. 
(i) The time complexity of Quicksort on already sorted data elements with the last element chosen as the pivot is 𝑂(𝑛^2^)
(ii) The runtime of Dijkstra's algorithm when implemented using a binary heap is 𝑂((𝑉+𝐸)log⁡𝑉)
(iii) The best case time complexity of selection sort is 𝑂(𝑛^2^)
(iv) The time complexity of Breadth-First Search using an adjacency list is 𝑂(𝑉+𝐸)
(v) The space complexity of Depth-First Search is 𝑂(𝑉+𝐸)

<hr>

Q3. b. **Explain Big O (Big - Oh ) and Big- O (Big-Theta) asymptotic notation.**
Ans. 
#### Big O (Big-Oh) Notation

Big O notation is used to describe an upper bound on the time complexity or space complexity of an algorithm. It provides an asymptotic measure of the performance of an algorithm as the input size grows. Specifically, Big O notation characterizes functions according to their growth rates: how quickly they grow as the size of the input increases.

Formally, if 𝑓(𝑛) and 𝑔(𝑛) are two functions, we say that 𝑓(𝑛)=𝑂(𝑔(𝑛)) if there exist positive constants 𝑐 and 𝑛0​ such that for all 𝑛≥𝑛0​:

𝑓(𝑛)≤𝑐⋅𝑔(𝑛)

In other words, beyond a certain point, 𝑓(𝑛) grows no faster than 𝑔(𝑛) up to a constant factor. Big O notation is typically used to describe the worst-case scenario of an algorithm.

#### Big Θ (Big-Theta) Notation

Big-Theta notation provides a tight bound on the time complexity or space complexity of an algorithm. It represents both the upper and lower bounds, meaning it gives an exact asymptotic behavior of a function.

Formally, if 𝑓(𝑛) and 𝑔(𝑛) are two functions, we say that 𝑓(𝑛)=Θ(𝑔(𝑛)) if there exist positive constants 𝑐1​, 𝑐2​, and 𝑛0​ such that for all 𝑛≥𝑛0:

𝑐1⋅𝑔(𝑛)≤𝑓(𝑛)≤𝑐2⋅𝑔(𝑛)

In other words, 𝑓(𝑛) grows at the same rate as 𝑔(𝑛)up to constant factors. Big-Theta notation is used to describe the average-case complexity or the tight bounds of an algorithm.

<hr>

Q3. c. **Sort the following elements using insertion sort algorithm.
15, 20, 10, 30, 50, 18, 5, 45**

Ans. 

**Steps of Insertion Sort**

1.  Start with the second element (index 1) and compare it with the first element.
2.  Insert the second element in the correct position relative to the first element.
3.  Move to the next element and compare it with the previous elements, inserting it into its correct position.
4.  Repeat until the entire array is sorted.
```
+------+-------------------------------+
| Step |      	Array State            |
+------+-------------------------------+
|  0   | 15, 20, 10, 30, 50, 18, 5, 45 |
|  1   | 15, 20, 10, 30, 50, 18, 5, 45 |
|  2   | 10, 15, 20, 30, 50, 18, 5, 45 |
|  3   | 10, 15, 20, 30, 50, 18, 5, 45 |
|  4   | 10, 15, 20, 30, 50, 18, 5, 45 |
|  5   | 10, 15, 18, 20, 30, 50, 5, 45 |
|  6   | 5, 10, 15, 18, 20, 30, 50, 45 |
|  7   | 5, 10, 15, 18, 20, 30, 45, 50 |
+------+-------------------------------+

```

<hr> 

0.4 a. **Consider a situation where swap operation is very costly. Which sorting algorithms should be preferred so that the number of swap operations are minimized in general?**

Ans. 


<hr> 

Q4. b. **Write the algorithm for quick sort.**

Ans. 


<hr> 

Q4. c. **Show how depth-first search works on the following graph starting from node q.
Assume that the for loop in the DFS procedure considers the vertices in alphabetical order, and assume that each adjacency list is ordered alphabetically. Show the discovery and finishing times for each vertex, and show the classification of each edge.**

Ans. 


<hr> 


## Complexity Table : 
| Algorithm | Time Complexity ( Adj Mat ) | Time Complexity ( Adj List )| Space Complexity ( Adj Mat )| Space Complexity  ( Adj List )|
|--|--|--|--|--|
|BFS |  O(V^2^) | O(V+E) |O(V^2^) | O(V+E) |
|DFS | 

> [Youtube reference](https://www.youtube.com/watch?v=N2P7w22tN9c&t=387s&ab_channel=GateSmashers) 

## Breadth First Search 
Q1. What is a graph ?
Ans. 
* It is a **non-linear** data structure consisting of vertices and edges.
* Vertices = nodes
* Edges = lines that connect the nodes

<hr>

Q2. What are the differences between an Adjacency List and Adjacenct Matrix ? 
Ans. 
**![](https://lh7-us.googleusercontent.com/3vkLzRT3PLbzpNnX13g2egiFuvb8Vl-2dD0AUvMbEpTHojGJRzucGjwqeegWfixUdK2-RH3N0dD3EWt7V1rXEqSy2r42q_oqojmx8SjYLAP90pyKtXpUTIeb5SIMNCLHUSUCJAO5gN8mhyF4iwRIxAY)**
**Adjacency List**
1. It is an array of lists, where the index displays a vertex and the second column shows all connected vertices.

**![](https://lh7-us.googleusercontent.com/JPdj7jY8C6ocHhgh1tH0uUNlc7T3kEDwrE19m2G13HMDKqY2Es6tSgnFOBdnYvXQ6Fe7uMsi5YLCMF9k_NLylmgu4imihZpeqeaP7pKQ1lnHgKyGMherkuMqOnUTEMWN7woiRBlRtrY84xMPWZoZqPE)**
**Adjacency Matrix**
1. It is a matrix of size V x V, where V = number of vertices.
2. The element at row i and column j is 1 only if that edge exists. Else it is 0.
**![](https://lh7-us.googleusercontent.com/ObF_SVSjnO2yMxUJcS4chsDZLvG9Z6v9HegFyq9Jh6scgdUVIotngGM-LW16ggpuBy04MPFRd7n_5oqUh5Gr_F3KcmFxJHHtKOrTL0h5DnvVstlAJzq_aUxbuuzXEflSlubG3i97XPiG5aICkOlcutU)**

<hr>

Q3. What is Breadth First search and what are the steps followed in BFS ?
Ans. 
**Steps** : 
1. Explore the graph level by level
2. First the vertices that are one step away then those that are two steps away
3. At each step we add the expored vertex to the head of the queue

**Pseudocode** :

```
// Function BFS(i) - BFS starting from vertex i
function BFS(i) 
    // Initialization
    for j = 1..n {
        visited[j] = 0
    }
    Q = []

    // Start the exploration at i
    visited[i] = 1
    append(Q, i)

    // Explore each vertex in Q
    while Q is not empty
        j = extract_head(Q)
        for each (j, k) in E
            if visited[k] == 0
                visited[k] = 1
                append(Q, k)
```
Time Complexity : O(V+E)

* BFS can record how long the path is to each vertex




## Depth First Search


## Djikstras Algorithm
Q1. What are greedy algorithms ? 

## Bellman Ford

