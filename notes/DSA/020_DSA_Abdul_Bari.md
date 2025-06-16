# Algorithms

## Algorithm vs Program
| **Algorithm**         | **Program**          |
| ---                   | ---                  |
| Designing stage       | Implementation stage |
| Need domain knowledge | Need coding skills   |
| Language agnostic     | Language dependent   |
| OS/HW independent     | OS/HW dependent      | 
| Analysis can be done  | Testing can be done  |

<br>

## Priori Analysis vs Posterior Analysis
| **Priori Analysis**   | **Posterior Analysis**    |
| ---                   | ---                       |
| Algorithm             |     Program               |
| Language agnostic     | Language dependent        |
| OS/HW independent     | OS/HW dependent           | 
| Time & Space function | Can be analysed using actual time units and space units  |

---
<br>

## characteristics

- Zero or more inputs.
- At least one output - some functions may not directly return output but might have side effects like writing to a file.
- Definiteness - Every step of the problem is crear and un ambiguous.
- Finiteness - Every algorithm should terminate after finite number of steps
- Effectiveness - Algorithm should optimal solution to the promlem. should use minimal time and space.

<br>

## How to Write
```
Algorithm Swap(a,b):
Begin
    temp :=  a
    a := b
    b := temp
End
```
<br>

## How to Analyse
- Time & Space complexity of an algorithm
    - In a program each simple statement take one unit of time.
- Also Network bandwith, power consumption and CPU registers are considered based on requirements.

**`Examples`**

```
Algorithm Sum(A,n):
    S:=0                      -> 1 Unit
    for(i:=0;i<n;i++){        -> max(1, n+1, n) = n + 1 Units
        S = S + A[i]          -> n Units
    }
    return S                  -> 1 Units
```
- Time: total time taken by above function will be `2n + 3`. This will be considered `O(n)` algorithm.
- Space: total space will be n + 3(`S -> 1, n -> 1, i -> 1, A -> n`). This will be considered `O(n)` algorithm.

---
<br>

```
Algorithm Multiply(A, B,n):
    out = []                                                    -> 1
    for(i:=0; i < n; i++){                                        -> n + 1 
        for(j:=0; j < n; j++){                                    -> (n+1) * n
            for(k:=0; k < n; k++){                                -> (n+1) * n * n
                out[i][j] = out[i][j] + (A[i][k] * B[k][j])     -> n * n * n
            }
        }       
    }
    return S                                                    -> 1 Units
```
- Time: $ O(2n^3 + 2n^2 + 2n + 3) = O(n^3) $
- Space: $ O(3n^2 + 4) = O(n^2)$  where (A, B and out -> $2n^2$, i, j, k, n -> 4)

---
<br>

```
for(i:=0; i < n; i++){      -> n
    for(j:=0; j<i; j++){    -> i

    }
}
```
- Time Complexity = $ 1 + 2 + 3 + \dots + n = \frac{n(n+1)}{2} = O(n^2)$

---
<br>

```
p := 0
for(i:=1; p < n; i++){ 
    p = p + i
}
```
$$
i = 1;  p = 1 \\
i = 2;  p = 1 + 2 \\
i = 3;  p = 1 + 2 + 3 \\
\vdots \\
i = k;  p = 1 + 2 + 3 + \dots + k \\
$$
- So Here k will be less than n for sure since p is incrementing faster than i and will reach the limit n before i reaches that limit. So this loop will stop at p > n

$$
\begin{split}
p                &> n \\
\frac{k(k+1)}{2} &> n \\
k^2              &> n \\
k                &> \sqrt{n}
\end{split}
$$

---
<br>

```
for(i:=1; i < n; i = i * 2){ 
    stmt;
}
```

- i will increase like this $ 1, 2, 2^2, 2^3, \dots , 2^k $

$$
\begin{split}
i   &> n \\
2^k &> n \\
k   &> log_{2}(n)
\end{split}
$$

---
<br>

```
for(i:=n; i < 1; i = i / 2){ 
    stmt;
}
```

- i will increase like this $ n, \frac{n}{2}, \frac{n}{2^2}, \frac{n}{2^3}, \dots , \frac{n}{2^k} $

$$
\begin{split}
i               &< 1 \\
\frac{n}{2^k}   &< 1 \\
n               &< 2^k \\
k               &> log_{2}(n)
\end{split}
$$

---
<br>

```
for(i:=0; i*i < n; i = i++){ 
    stmt;
}
```

- This will execute untill $ i^2 > n \rightarrow i > \sqrt{n}$

` Note: while loop is analysed similarly. Generally all the ideas we discussed above can be used with while loop also.`


## Classes of functions
- $\Omicron(1)$ -> constant
- $\Omicron(\log{n})$ -> logrithemic
- $\Omicron(n)$ -> linear
- $\Omicron(n^2)$ -> quadradic
- $\Omicron(n^3)$ -> cubic
- $\Omicron(2^n)$, $\Omicron(3^n)$, ... , $\Omicron(n^n)$ -> exponentials

We could arrange them as follows:

``` 
 1 < log(n) < sqrt(n) < nlog(n) < n^2 < n^3 < n^k < ... < 2^n < 3^n < ... < n^n
 where k is some constant
```

## Asymptotic Notations Big Oh - Omega - Theta

- $\Omicron$ - big oh - upper bound
- $\Omega$ - big omega - lower bound
- $\Theta$ - big theta - average bound

<br>

**Big Oh:** 
- The function $f(n) = \Omicron(g(n))$ iff there exists +Ve constants c and k such that f(n) <= c * g(n) for all n >= k

- for example $ 2n+3 \leq 3n  \leq n^2 ... \leq n^n $ is true for some constant k. So this function will be $\Omicron(n)$ ... $\Omicron(n^2)$ etc.

<br>

**Big Omega:** 
- The function $f(n) = \Omega(g(n))$ iff there exists +Ve constants c and k such that f(n) >= c * g(n) for all n >= k

- for example $ log(n) \leq \sqrt{n} \leq n \leq 2n+3 $ is true for some constant k. So this function will be $\Omega(n)$, $\Omega(\sqrt{n})$ etc.

<br>

**Big Theta:** 
- The function $f(n) = \Theta(g(n))$ iff there exists +Ve constants c1, c2 and k such that c1 * g(n) >= f(n) >= c2 * g(n) for all n >= k

- for example $ n \leq 2n+3 \leq 3n $ is true for some constant k. So this function will be $\Theta(n)$ etc.

<br>

Note: to find the big-oh expression multiply the lowest term(s) by some expression so that the whole function will add up to the highest term in the overall expression. From there you can start to figure out the expression for big-oh(some times for big-omega also) notation.
- for example if the function is $n^2\log{n} + n$ then multiply it by $n\;\log{n}$
- then you will get an expression $2n^2 \log{n}$

Note: we might not always find an expression for big-theta function, for example $1 \leq n! \leq n^n$ and $1 \leq \log{n!} \leq \log{n^n}$

`Important: remember that any of these notations can be used to define the best, worst and average case time complexity of the algorithm. It is not the case that big-oh is for the worst case and big-omega is for the best case. That will not be correct`


## Properties of Asymptotic Notations

- Will not be affected by multiplication of constant values. Both $5n^2$ and $100n^2$ will have the same asymptotic notation.s

- **`Reflexive:`** f(n) is itself $\Omicron(f(n))$.

- **`Transitive:`** if f(n) is $\Omicron(g(n))$ and g(n) is $\Omicron(h(n))$, then f(n) will be $\Omicron(h(n))$.

- **`Symmetric:`** Only true for theta notation. If f(n) is $\Theta(g(n))$ then g(n) is $\Theta(f(n))$

- **`Transpose Symmetric:`** If f(n) is $\Omicron(g(n))$, then g(n) is $\Omega(f(n))$. Similarly if f(n) is $\Omega(g(n))$, then g(n) is $\Omicron(f(n))$

- **`Big - Theta:`** If f(n) is $\Omicron(g(n))$ and $\Omega(g(n))$, then f(n) is $\Theta(g(n))$.

- **`Sum:`** If f(n) is $\Omicron(g(n))$ and d(n) is $\Omicron(e(n))$, them f(n) + g(n) is $\Omicron(max(g(n), e(n)))$

- **`Product:`** If f(n) is $\Omicron(g(n))$ and d(n) is $\Omicron(e(n))$, them f(n) * g(n) is $\Omicron(g(n) * e(n))$


## comparison of two functions
Here take an example of $n^2$ and $n^3$

- First method directly putting some values and checking the result.

- Second method is to apply log on both sides.(remember that you can apply log multiple time until you get some conclusion). Why are we using logrithms?
    - logrithms bring exponents down as coefficients.
    - products into sums. 
    - handles large numbers more manageably.
    - linearizes exponential growth($y = e^x \rightarrow ln(y) = x$).
    - Additionally, In statistics and machine learning, applying a log helps normalize skewed data, making trends clearer.

| $n^2$       | $n^3$        |
| ---         |  ---         |
| $\log{n^2}$ |  $\log{n^3}$ |
| $2\log{n}$  |  $3\log{n}$  |

- Here $2\log{n} \lt 3\log{n}$, so $ n^2 \lt n^3 $

| $2^n$         | $2^{2n}$              |
| ---           |  ---                  |
| $\log_2{2^n}$ |  $\log_2{(2^{2n})}$   |
| $n$           |  $2n$                 |

- `Note: here even though n and 2n are asymtotically equal, since we got this after applying the logrithm the original expressions will not be asymptotically equanl 2^n is always less than 2^2n since n < 2n.`



**Some useful log formulas:**

- $\log{ab} = \log{a} + \log{b}$

- $\log{\frac{a}{b}} = \log{a} - \log{b}$

- $\log{a^b} =  b\log{a}$

- $a^{\log_c{b}} = b^{\log_c{a}}$

- $a^b = n$ then $b = \log_a{n}$

**Another example:**

| $ n^2 \log{n} $                 |  $ n (\log{n})^{10} $             |
| ---                             |  ---                              |
| $ \log{ (n^2 \log{n}) } $       |  $ \log{ (n (\log{n})^{10}) } $   |
| $ 2\log{n} + \log{(\log{n})} $  |  $ \log{n} + 10 \log{(\log{n})} $ |

- So here since log(n) is a bigger term $ 2\log{n} + \log{(\log{n})} \gt \log{n} + 10 \log{(\log{n})} $

<br>


## Best, Worst and Average case analysis

For example take `linear search` and `binar search` algorithms.

**Linear Search:**

- Best case will be $\Omicron(1)$ or $\Omega(1)$ or $\Theta(1)$. Since all of these functions corresponds to constant time complexity that is finding the element at the first index.

- Worth case will be $\Omicron(n)$. Finding the element at the last index.

- Average case will be $\frac{1+2+3+ \dots + n}{n} = \frac{n+1}{2}$, then 

**Binary Search:**

- Best case: $B(1) = \Omicron(1) = \Omega(1) = \Theta(1)$.
- Worst case: $W(\log_2{n}) = \Omicron(\log_2{n}) = \Omega(\log_2{n}) = \Theta(\log_2{n})$. But remember that if tree is not balanced(if it is skewed), then height of the tree can be n.

<br>

## Disjoint Sets

About dijoint sets & operations, detecting a cycle in a undirected graph, representation of disjoint sets using graphical method and array method. Finally time efficient operations on disjoint sets that are weighted union and collapsing find.

- The disjoint set means two sets that are not having any common elements.

- **Logic:** By using find(membership operation) and union operations on group of sets, we can figure out that whether connecting two vertices by an edge will form a cycle.


Take a following example with vertices u and edges e.

- $u = \{ 1,2,3,4,5,6,7,8 \} $ is called universal set. set of edges are $ e = \{ 1,2,3,4,5,6,7,8,9 \}$ that connects the following pair of vertices $E = \{(1,2), (3,4), (5,6), (7,8), (2,4), (2,5), (1,3), (6,8), (5,7) \}$.

- Now you have to take each edge one by one and remove its vertices from the universal set $u$. At any point of time you will have sets $u, S1, S2, \dots , S_k$ at your hand. You have to follow the following rules recursively. At any point of time if you find two vertices of an edge in the same set that is other than the universal set $u$, then you have found a cycle in the graph.

    1. First take an edge $e_m$.

    2. If its vertices are in the universal set, then remove them from u and form a separate set $S_i$ using those two vertices.

    3. If its vertices are in two different sets $S_i$ and $S_j$, then find the union of these two sets and form a new set $S_k = S_i \cup S_j$.

    4. For some edge $e_m$, if its vertices are in the same set $S_i$(which is not the set $u$), then including that edge in the graph will form a cycle.

    5. Go to step-1 and continue this process untill all the edges are visited.

- Using this approach we can figure out whether there is a cycle in the graph.
- **`Kruskal's Algorithm(Minimum Spanning Tree-MST):`** Using this approach Kruskal's algorithm creates a minimum spanning tree from the graph by always choosing an edge with the minimum cost/weight. `It can do this by simply starting from a minimum weighted edge`.

### Implementation Approaches:

We could implement this algorithm using the following approaches.

- **Tree Method:** each set will be a tree and set some random node as a parent. Whenever you have to union all two trees that corresponds to two vertices $v_1$ and $v_2$, choose one of their parent as the final parent and set the other tree root as the child of that final parent. At any point of time, if two vertices $(v_1, v_2)$ are found in the same tree, then that edge will form a cycle.

- **Array Method:** Here we will use an array to keep track of which vertex $v_i$ is a parent(or equivalently belongs to same set) of another vertex $v_j$. In this algorithm also you will recursively follow the following set of rules.
    1. for vertices $1,2, \dots , n$ initialise with -1 to each index of the array $A$.
    2. Take a edge $e_m$ and its vertices $(v_i, v_j)$.
    3. For vertices $(v_i, v_j)$ their corresponding indeces $i$ and $j$ contains the negative value then those vertices themselves are parent vertices. So choose one of them as parent(either based on weight or at random if weights are equal) and set the index of that parent vertex as the value for the other vertex. Increament the negative value for the parent vertex by the old value of the child vertex. This way the weight of the parent vertex will increase based on the number of children.
    4. If any one or both of the vertices contain the positve value in the array, then those verteces have parent vertex. So recursively search for the root parent vertex. Also update the values at the indeces $i$ and $j$ to the newly found root vertex index, so that next time when we search for the root parent vertex, the computation will be less. 
    5. If the root parent for both the verteces are same, then adding that new edge $e_m$ will form a cycle.
    6. If they have different root parent then follow the same approach as in step-3 and merge those two trees by updating their corresponding values in the array.
    7. Go to step-2 and continue the process untill all the edges are visited.

**Weighted Union:** In step-3 we are unioning two trees based on weight of the root parent vertex of those trees. This is called weighted union.
    
**Collapsing Find:** In step-4 we update the parent indeces of the verteces $(v_i, v_j)$ to the root parent index. This is called collapsing find. This process collapses all descendents of the tree as the direct children of the root node.


## Divide and Conquer

This is a stratergy to solve a problem. Like this there are some other stratergies also like greedy method, dynamic programming, backtracking and branch and bound.

**Definition:** If the problem $P$ is large then divide it into multiple small problems $P_1, P_2, \dots , P_k$. Solve those sub problems individually and find their solutions $S_1, S_2, \dots S_k$. Then combine those solution to get a final solution $S$ for the problem $P$. Here If sub problems are also large then we can apply the same stratergy for each one those sub problems also. This approach can be used recursively. 

- Here the key is that each of the sub problems must be same as the original problem. If the orginal problem is to sort then each of the sub problem also must be sort.

- This way remember that divide and conquer algorithms can direclty make use of the parallel programming.

```
Pseudocode: 

DAC(P){
    s is solution
    if(P is small){
        s = solve p
    }else{
        divide P into P_1,P_2,...,P_k
        apply DAC(P_1),DAC(P_2),...,DAC(P_k)
        s = combine the solutions S_1,S_2,...,S_k
    }
    return s
}
```

Some algorithms that uses divide and conquer stratergy are as follows.
```
1. Binary Search
2. Finding a Maximum and Minimum
3. Merge Sort
4. Quick Sort
5. Strassen's Matrix Multiplication
```

## Recurrence Relation Analysis

### T(n) = T(n-1) + 1

```
func rec_fun(n){        - Assuming this will take T(n) time
    if(n>0){            - 1
        print(n)        - 1
        rec_fun(n-1)    - T(n-1)
    }
}
Total                   = T(n) = T(n-1) + 1
```

Assuming the following from the algorithm.

$$
T(n) = 
\begin{cases}
   1            &\text{if } n = 0 \\
   T(n-1) + 1   &\text{if } n \gt 0
\end{cases}
$$


#### Tree method

```
T(n)
|-- 1
|-- T(n-1)
    |-- 1
    |-- T(n-2)
    |-- .
    |-- .
    |-- .
        |-- 1
        |-- T(1)
            |-- 1
            |-- T(0)
```

Here if the recursion continues like this for n times adding up all the 1's will give us n.
So the time complexity here $\Omicron(n)$.

#### Substitution method

- To simplify and solve this recurrence relation we substitute the value of T(n-1) in T(n) which will be T(n-1) = T(n-2) + 1 using the same formula.

- After substituting T(n-1), then we will get T(n) = T(n-2) + 2. Again substituting the value of T(n-2) will give you T(n) = T(n-3) + 3. 

- Like this if we continue for k times then we will get `T(n) = T(n-k) + k`.

- If this recursion stops at n = 0 which T(0), then n - k = 0 => k = n.

- `T(n) = T(n - n) + n => T(n) = 1 + n = O(n)` This will tell us that time complexity of this function will be $ \Omicron(n) $.

- We can see the derivation of continuous substitution below.

```
T(n) = T(n-1) + 1

By continuous substitution
T(n) => [T(n-2) + 1] + 1 = T(n-2) + 2
T(n) => [T(n-3) + 1 ] + 2 = T(n-3) + 3
.
.
.
T(n) => T(n-k) + k

We know the initial condition that function will stop at n = 0.
So here must be n-k = 0 => k = n.
Substituting this into the final equation we will get the following
T(n) => T(n-n) + n => T(0) + n = 1 + n
This tells us that time complexity will be O(n).
```
---
<br>

### T(n) = T(n-1) + n


```
func rec_fun(n){            - Assuming this will take T(n) time
    if(n>0){                
        for(i=0;i<n;i++){   - n
            print(i)
        }
        rec_fun(n-1)        - T(n-1)
    }
}
Total                       = T(n) = T(n-1) + n
```

Assuming the following from the algorithm.

$$
T(n) = 
\begin{cases}
   1            &\text{if } n = 0 \\
   T(n-1) + n   &\text{if } n \gt 0
\end{cases}
$$


#### Tree method

```
T(n)
|-- n
|-- T(n-1)
    |-- n - 1
    |-- T(n-2)
    |-- .
    |-- .
    |-- .
        |-- 2
        |-- T(1)
            |-- 1
            |-- T(0)
```

Here the recursion continues for n time, then summing up all the terms gives the following result.
1. $ n + (n-1) + (n-2) + \dots + 3 + 2 + 1 $
2. $ \frac{n(n-1)}{2}$
3. $ \Omicron(n^2) $

#### Substitution method

```
T(n) = T(n-1) + n

By continuous substitution
T(n) => [T(n-2) + (n-1)] + n = T(n-2) + (n-1) + n
T(n) => [T(n-3) + (n-2) ] + (n-1) + n = T(n-3) + 3
.
.
.
T(n) => T(n-k) + (n-k) + (n-(k-1)) + (n-(k-2)) + ... + (n-2) + (n-1) + n

We know the initial condition that function will stop at n = 0.
So here must be n-k = 0 => k = n.

Substituting this into the final equation we will get the following
T(n) => T(n-n) + 0 + 1 + 2 + ... + (n-2) + (n-1) + n 
     => T(0) + n(n+1)/2 = 1 + (n^2 + n) / 2

This tells us that time complexity will be O(n^2).
```
---
<br>

### T(n) = T(n-1) + log n


```
func rec_fun(n){                    - Assuming this will take T(n) time
    if(n>0){                
        for(i=0; i< n; i= i * 2){   - log n
            print(i)
        }
        rec_fun(n-1)                - T(n-1)
    }
}
Total                               = T(n) = T(n-1) + log n
```

Assuming the following from the algorithm.

$$
T(n) = 
\begin{cases}
   1            &\text{if } n = 0 \\
   T(n-1) + \log{n}   &\text{if } n \gt 0
\end{cases}
$$


#### Tree method

```
T(n)
|-- log n
|-- T(n-1)
    |-- log n-1
    |-- T(n-2)
    |-- .
    |-- .
    |-- .
        |-- log 2
        |-- T(1)
            |-- log 1
            |-- T(0)
```

Here the recursion continues for n time, then summing up all the terms gives the following result.
1. $ \log{n} + \log{n-1} + \log{n-2} + \dots + \log{3} + \log{2} + \log{1} $
2. $ \log{(n * (n-1) * (n-2) * \dots * 2 * 1)}$
3. $ \log{n!}$ 
4. for n! upper limit will be $n^n$. We could use that here. then n will come before log.
5. $ \Omicron{(n\log{n})}$

#### Substitution method

```
T(n) = T(n-1) + log n

By continuous substitution
T(n) => [T(n-2) + log(n-1)] + log n = T(n-2) + log(n-1) + log n
T(n) => [T(n-3) + log(n-2) ] + log(n-1) + log n = T(n-3) + log(n-2) + log(n-1) + log n
.
.
.
T(n) => T(n-k) + log(n-k) + log(n-(k-1)) + log(n-(k-2)) + ... + log(n-2) + log(n-1) + log n

We know the initial condition that function will stop at n = 0.
So here must be n-k = 0 => k = n.

Substituting this into the final equation we will get the following
T(n) => T(n-n) + log 1 + log 2 + ... + log(n-2) + log(n-1) + log n 
     => T(0) + log(1 * 2 * 3 * ... * n) = 1 + log(n!) = O(n log(n))

This tells us that time complexity will be O(n log(n)).
```
---
<br>


### T(n) = 2T(n-1) + 1

```
func rec_fun(n){                    - Assuming this will take T(n) time
    if(n>0){                
        print(n % 2)                - 1
        rec_fun(n-1)                - T(n-1)
        rec_fun(n-1)                - T(n-1)
    }
}
Total                               = T(n) = 2T(n-1) + 1
```

Assuming the following from the algorithm.

$$
T(n) = 
\begin{cases}
   1            &\text{if } n = 0 \\
   2T(n-1) + 1   &\text{if } n \gt 0
\end{cases}
$$


#### Tree method

```
T(n)
|-- n-1
|-- T(n-1)
    |-- n-2
    |-- T(n-2)
        |-- .
        |-- .
        |-- .
    |-- T(n-2)
        |-- .
        |-- .
        |-- .
            |-- log 2
            |-- T(1)
                |-- log 1
                |-- T(0)
            |-- T(1)
                |-- log 1
                |-- T(0)
|-- T(n-1)
    |-- n-2
    |-- T(n-2)
        |-- .
        |-- .
        |-- .
    |-- T(n-2)
        |-- .
        |-- .
        |-- .
            |-- log 2
            |-- T(1)
                |-- log 1
                |-- T(0)
            |-- T(1)
                |-- log 1
                |-- T(0)
```

Here at each level tree splits into 2 times. For example in first level tree splits into 2 sub trees, In second level there will be four(2^2) sub trees. In the third level there will be 2^3 sub trees.
1. $ 2^1 + 2^2 + 2^3 + \dots + 2^{k-1} + 2^k $
2. This recursion will stop when n-k = 0 where T(0) = 1. So $2^1 + 2^2 + 2^3 + \dots + 2^{n-1} + 2^n$.
3. We know the formula $ a + ar + ar^1 + \dots + ar^{k-1} +  ar^k = \frac{a(r^{k+1} - 1)}{r-1}$.
4. So it will be $2^{n+1} - 1$
2. $ \Omicron{(2^n)}$

#### Substitution method

```
T(n) = 2T(n-1) + 1

By continuous substitution
T(n) => 2[2T(n-2) + 1] + 1 => 2^2 T(n-2) + 2 + 1
T(n) => 2^2[2T(n-3) + 1] + 2 + 1 => 2^3 T(n-3) + 2^2 + 2 + 1
.
.
.
T(n) => 2^k T(n-k) + 2^(k-1) + 2^(k-2) + ... + 2^2 + 2 + 1

We know the initial condition that function will stop at n = 0.
So here must be n-k = 0 => k = n.

Substituting this into the final equation we will get the following
T(n) => 2^n T(0) + 2^(n-1) + 2^(n-2) + ... + 2^2 + 2 + 1
     => 2^(n+1) - 1

This tells us that time complexity will be O(2^n).
```


### T(n) = 2T(n-5) + n by substitution method

```
T(n) = 2T(n-5) + n

By continuous substitution
T(n) => 2[2T(n-5) + n] + n => 2^2 T(n-5) + 2n + n
T(n) => 2^2[2T(n-2*5) + n] + 2n + 1n => 2^3 T(n-10) + (2^2)n + 2n + 1n
.
.
.
T(n) => 2^k T(n-5k) + (2^(k-1))n + (2^(k-2))n + ... + (2^2)n + 2n + 1n

We know the initial condition that function will stop at n = 0.
So here must be n-5k = 0 => k = n/5.

Substituting this into the final equation we will get the following
T(n) => 2^n/5 T(0) + 2^((n/5)-1) + 2^((n/5)-2) + ... + 2^2 + 2 + 1
     => 2^((n/5)+1) - 1

This tells us that time complexity will be O(2^(n/5)).
```

---
<br>

### Masters Theorem for subtracting function

- T(n) = T(n-1) + 1 => O(n)
- T(n) = T(n-1) + n => O(n^2)
- T(n) = T(n-1) + log n => O(n log n)
- T(n) = T(n-1) + n => O(n^3)
- T(n) = T(n-2) + 1 => n/2 => O(n)
- T(n) = T(n-100) + n => n^2 / 100 => O(n^2)
- T(n) = 2T(n-1) + 1 => O(2^n)
- T(n) = 2T(n-1) + n => O(n2^n)
- T(n) = 2T(n-6) + log n => O(log n (2^n/6))
- T(n) = 3T(n-1) + n => O(n3^n)

Generally speaking:

T(n) = aT(n-b) + f(n)
Where a > 0, b > 0 and f(n) = O(n^k) where k >= 0.

- if a = 1 then $\Omicron{(n * f(n))}$

- if a > 1 then $\Omicron{(a^(n/b) * f(n))}$

- if a > 1 then $\Omicron{(f(n))}$

---
<br>

### T(n) = T(n/2) + 1 Dividing functions

```
func rec_fun(n){                    - Assuming this will take T(n) time
    if(n>0){                
        print(i)                    - 1
        rec_fun(n/2)                - T(n/2)
    }
}
Total                               = T(n) = T(n/2) + 1
```

Assuming the following from the algorithm.

$$
T(n) = 
\begin{cases}
   1            &\text{if } n = 1 \\
   T(n/2) + 1   &\text{if } n \gt 1
\end{cases}
$$


#### Tree method

```
T(n)
|-- 1
|-- T(n/2)
    |-- 1
    |-- T(n/2^2)
    |-- .
    |-- .
    |-- .
        |-- 1
        |-- T(n/2^(k-1))
            |-- 1
            |-- T(n/2^k)
```

This recursion will stop when $\frac{n}{2^k} = 1$
1. So $2^k = n$, then $k = \log_2{n}$
2. $\Omicron(log_2{n})$

#### Substitution method

```
T(n) = T(n/2) + 1

By continuous substitution
T(n) => [T(n/2^2) + 1] + 1 = T(n/2^2) + 2
T(n) => [T(n/2^3) + 1 ] + 2 = T(n/2^3) + 3
.
.
.
T(n) => T(n/2^k) + k

We know the initial condition that function will stop at n = 0.
So here must be n / 2^k = 1 => 2^k = n.

Substituting this into the final equation we will get the following
T(n) => T(1) + log n

This tells us that time complexity will be O(log(n)).
```
---
<br>

### T(n) = 2T(n/2) + n Dividing functions

```
func rec_fun(n){                    - Assuming this will take T(n) time
    if(n>0){   
        for(i:=0; i < n; i ++){
            print(i)                - n
        }         
        rec_fun(n/2)                - T(n/2)
        rec_fun(n/2)                - T(n/2)
    }
}
Total                               = T(n) = 2T(n/2) + n
```

Assuming the following from the algorithm.

$$
T(n) = 
\begin{cases}
   1            &\text{if } n = 1 \\
   2T(n/2) + n   &\text{if } n \gt 1
\end{cases}
$$


#### Tree method

```
T(n)
|-- n
|-- T(n/2)
    |-- n/2
    |-- T(n/2^2)
        |-- .
        |-- .
        |-- .
    |-- T(n/2^2)
        |-- .
        |-- .
        |-- .
            |-- n/2^(k-1)
            |-- T(n/2^k)
                |-- ...
                |-- T(1)
            |-- T(n/2^k)
                |-- ...
                |-- T(1)
|-- T(n/2)
    |-- n/2
    |-- T(n/2^2)
        |-- .
        |-- .
        |-- .
    |-- T(n/2^2)
        |-- .
        |-- .
        |-- .
            |-- n/2^(k-1)
            |-- T(n/2^k)
                |-- ...
                |-- T(1)
            |-- T(n/2^k)
                |-- ...
                |-- T(1)
```

This recursion will stop when $\frac{n}{2^k} = 1$. But here catch is in each level the for loop is running for k times. It sums to the following value.
1. $n + \frac{2n}{2} + \frac{2^2n}{2^2} + \frac{2^3n}{2^3} + \dots + \frac{2^k n}{2^k}$
2. There will be total of $\frac{n}{2^k} = 1$ terms. which means $k = \log_2{n}$
2. when you add n for long_2{n} times you will get $n \log_2{n}$
2. $\Omicron(n \log_2{n})$

#### Substitution method

```
T(n) = 2T(n/2) + n

By continuous substitution
T(n) => 2[2T(n/2^2) + n/2] + n = 2^2T(n/2^2) + 2
T(n) => 2^2[2T(n/2^3) + n/2^2] + n + n = 2^3T(n/2^3) + 3n
.
.
.
T(n) => 2^k T(n/2^k) + n + ... + n + n + n  = 2^k T(n/2^k) + kn

We know the initial condition that function will stop at n / 2^k = 1.
So here must be n / 2^k = 1 => 2^k = n => k = log(n)

This tells us that time complexity will be O(n log(n)).
```
---
<br>

### Masters Theorem for dividing function

$T(n) = aT(\frac{n}{b}) + f(n)$

Where a >= 1, b > 1 and $f(n) = \Theta(n^k \log^p{n})$.

- if $\log_b{a} > k$ then $\Omicron{(n^{\log_b{a}})}$

- if $\log_b{a} = k$
    - if p > - 1 then $\Omicron{(n^k \log^{p + 1}{n})}$
    - if p = - 1 then $\Omicron{(n^k \log\log{n})}$
    - if p < - 1 then $\Omicron{(n^k)}$

- if $\log_b{a} < k$
    - if p >= 0 then $\Omicron{(n^k \log^{p}{n})}$
    - if p < 0 then $\Omicron{(n^k)}$

---
<br>

### T(n) = T($\sqrt{n}$) + 1 root function

```
func rec_fun(n){                    - Assuming this will take T(n) time
    if(n>0){                
        print(i)                    - 1
        rec_fun(n^(1/2))            - T(n^(1/2))
    }
}
Total                               - T(n) = T(n^(1/2)) + 1
```

Assuming the following from the algorithm.

$$
T(n) = 
\begin{cases}
   1            &\text{if } n = 2 \\
   T(n^{\frac{1}{2}}) + 1   &\text{if } n \gt 2
\end{cases}
$$

#### Substitution method

- $ T(n) = T(n^{\frac{1}{2}}) + 1 $
By continuous substitution
- $ T(n) => [T(n^{\frac{1}{2^2}}) + 1] + 1 = T(n^{\frac{1}{2^2}}) + 2 $
- $ T(n) => [T(n^{\frac{1}{2^3}}) + 1 ] + 2 = T(n^{\frac{1}{2^3}}) + 3 $
- ...
- $ T(n) => T(n^{\frac{1}{2^k}}) + k $

To solve this problem assume that n is in powers of two that is $n = 2^m$ then $ m = log_2{n}$
- Assume that the function will stop when $2^{\frac{m}{2^k}} = 2$
- $\frac{m}{2^k} = 1$  =>  $ m = 2^k $  =>  $ k = \log_2{m}$  =>  $ k = \log{\log{n}}$
- $\Omicron(\log{\log{n}})$

---
<br>


## Binary Search

