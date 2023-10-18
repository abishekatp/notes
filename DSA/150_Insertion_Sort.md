### Insertion sort

Insertion sort is one of the algorithms used for sorting a sequence of elements. We are going to specifically look into the algorithm that sorts the sequence of numbers in an ascending(increasing) order. These numbers can be associated with an object as a key. Then we can sort the list of objects based on their keys using the same algorithm.

The problem:- Input is a sequence of numbers &lt;a1, a2, a3,…,a(n)>. The output will be &lt;a’1, a’2, a’3,…,a’(n)> where a’1 &lt;= a’2&lt;= a’3 &lt;= … &lt;= a’(n).


#### Pseudocode:

Insertion sort(A,n):



1. for i = 2 to n:
2.     key = A[i]
3.     j = i-1
4.     while j > 0 and A[j] > key:
5.         A[j+1] = A[j]
6.         j = j - 1
7.     A[j+1] = key


#### Explanation:

* This logic is simple here A is the array of elements which needs to be sorted. n is the length of the array A.
* Stage 1: First we start from the second element of the array and assume that all the elements from 0 to i-1 are already in sorted order(it is true because for i=2 there is only one element before that).
* Stage 3-5: This inner while loop will find the correct position for the element A[i] and insert it in that position.
* Then the inner while loop will start from j= i-1. If A[j] is bigger than the key then shift that element one position to the right.  
* To understand this step it is crucial to understand that all the elements from 0 to i-1 are already in sorted order.
* Stage 6: Note that we decrement the value of j at each iteration of this while loop. The loop will end either when A[j] &lt;= key or j = 0.
* Stage 7: after completing the while loop we might have shifted all the elements from a particular index  j through i-1(only if those values are bigger than A[i]) to the position j+1 through i. For the position A[j] we insert the value of the key. So is the name insertion sort. For each iteration of the for loop in Stage 2 we insert the value A[i] in its correct position in the sub array A[1:i].


#### Correctness

We will prove the correctness of this algorithm using mathematical induction.

**Basis:**

The base condition is that all the elements in the sub array 1 to i-1 are in sorted order for i =2. This is obvious because in this case there is only one element in the sub array which must be in sorted order.

**Inductive hypothesis:**

We assume that for some iteration i the sub array 1 through i-1 is in sorted order. We have to prove that the sub array 1 through i is sorted for iteration i+1.

**Induction:**

* To prove this we have to understand what is happening inside one iteration of the for loop at stage 1. 
* After the i’th iteration, based on the inductive hypothesis all the elements in the sub array A[1:i] are in sorted order.
* The i+1 iteration will have key = A[i+1]. It will check for all the elements from j =i through 1, whether A[j] > key. If yes then shift the element A[j] to one position to the right. At the end of the i+1 iteration put the key in the place where the last element is shifted from.
* So this i+1 iteration will make sure that the element at i+1 position is correctly placed such that the sub array A[1 : i+1] is in sorted order.
* Hence after n-1 iterations the whole array will be in sorted order. So our algorithm is correct.
