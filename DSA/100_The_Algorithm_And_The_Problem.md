### Algorithm and Problem:

**What is a computational Problem?**

The computational problem is a problem statement which clearly defines the relationship between the input and output of a problem in a general way. This problem statement will be described towards finding an algorithm that can solve that problem**.**


* Depending on how the problem statement is defined, the solution for that problem may greatly depend on it. As we all know, clearly understanding the problem statement is half way through the solution.

The problem statement should describe the following things:


* What is the nature and structure of the input?
* What should be the output and relationship between the input and output? The clearer the relationship is, the easier the problem is solved.

Example: we can take a simple problem of sorting. This problem statement should clearly define the kind of data(numbers or text or …), order of the data(ascending or descending or …), whether there is some computational bound to the problem and any other properties that reduce the ambiguity of the problem. Input can be a sequence of elements like &lt;4, 55, 2, 5, 66, 12>. Output will be a sequence of elements in a desired order.

**What is an Algorithm?**

Algorithm is a well defined computational procedure(defined as a sequence of well defined steps) which has the following properties.

* It has a value or set of values as an input. 
* It has a value or set of values as output.
* Each step of the procedure is well defined.
* It completes its computation after computing for a finite number of steps.

**When should we say an algorithm is correct?**

* An algorithm is correct when it correctly maps the relationship between the input and output of a problem statement and produces an output in a finite amount of time.

Example: For example if you take a sorting problem there are more than one solution for this problem. The algorithm will take a sequence of elements as input and output the sequence of elements in a desired order specified by a problem statement. The algorithm will be correct when it outputs the sequence in a correct order for any valid input. Insertion sort, bubble sort, Merge sort and quicksort are some of the commonly used sorting algorithms.

**What is the complexity of a problem and its algorithm?**

* Based on the nature of the problem it will need some computational resources to solve the problem algorithmically. The two main resources we may consider are time and space(memory).
* Complexity is most generally defined for algorithms. Based on which complexity class problems belong to we can categorise them into different classes.
* The complexity of an algorithm is generally defined as a function that maps some property of an input(like length or number of elements in a set, number of nodes and edges in the graph or something else) to  the amount of time or space needed by that particular algorithm.
* The complexity of an algorithm greatly impacts the practicality of an algorithm. Since we only have finite amounts of computational resources we always need an efficient algorithm that can solve the problem. We will see more about this complexity in future topics. 

Example:

* If you compare an insertion sort and merge sort with respect to their time complexity(number of steps required to produce an output), the former one requires f1(n) = (c1 n^2) later one requires f2(n) = (c2 n lg(n)).
* Here c1 and c2 are some constants that depend on the implementation of these algorithms but they don’t depend on the input. The variable n is the one that depends on the input. Her lg(n) is the log2(n) which is log with base 2.
* Even if c2 is much bigger than c1 the merge sort will always be efficient for very large input sizes(for example 100 million elements in the list). This number is very practical. When you store some time series data it will be much bigger than this even for data that is collected in a single day(like share market data). We analyse the complexity of algorithms to understand these kinds of behaviour.
* For some resource constraint applications we even consider the amount of memory(space) used by an algorithm. For example insertion sort can be done in-place with constant memory usage whereas merge sort will need memory that linearly depends on the input = (c1 n).

**What is a probabilistic algorithm?**

In case if some problems don't have an efficient solution or if the solution is not practically implementable then we may opt for an efficient solution which doesn’t always give a correct output.


* The probabilistic algorithms will give a correct output with the high probability and be allowed to give the wrong answer with very low probability.
* These probabilistic algorithms might use some random choice or probabilistic decision in their description. The famous example of probabilistic algorithms is a probabilistic algorithm for primality testing which we will see in the future.

**What is an online algorithm?**

* Usually an input will be predefined before running an algorithm. This is not always the case for every algorithm. Some algorithms will get a continuous stream of input from some data source. These algorithms are called online algorithms.
* For example The YouTube algorithm to process and upload the video might have to handle a continuous stream of data either while the user is uploading video or live streaming video.

**Where do we use algorithms?**

* In the modern world we use algorithms everywhere in our day to day life. It is obviously in our computers, televisions, refrigerators, cars, hospitals and many more places. 
* Computers use them in a general way, the most basic television uses them for control, cars use them for navigation and various other safety mechanisms and hospitals use them to automatically monitor the patient. 
* If you think about it, AI is also all about efficient algorithms that can learn from the data(machine learning and deep learning algorithms). But these algorithms work in a probabilistic way. Input and output depends on different application areas where these algorithms are used.
* Data science uses algorithms to efficiently process the data and extract useful information from them. Data visualisation uses algorithms to efficiently draw various charts from the data.
* Algorithms are used to find efficient routes in maps such as google maps. Used to find an efficient path to transfer some data from one location to some other location on the network.
* Used in rockets and satellites for navigation, data transmission and for controlling many dynamic parts of the whole system. This list will go on forever. So when we describe some of the important algorithms we will also see their applications.