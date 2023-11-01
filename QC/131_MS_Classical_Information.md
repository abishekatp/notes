
# Classical Information(Multiple systems)

* As in a classical single system, In the multiple systems case also we will first see about the classical information and then go onto the quantum information in the next blog.


## What does the multiple systems mean?

* We have seen previously that the single system can represent some information using its classical states. For example we have seen torch light example with the classical states $\Sigma$ = {OFF, ON} and more formal single system was a Bit with classical states $\Sigma$ = {0, 1}.

* Remember that these single systems have a finite non empty set of classical states. So this means any particular classical system of this kind can only represent finite amount information. If you think about our world, it is made up of many complex systems(in our case it is called multiple systems). Intutively the complex systems are the combination of many same or different kind of single system. How can we mathematically reprsent these complex systems? so that we can process those information mathematically.

* For example, in the blog about single system and specifically in the torch light example, Individually we have used classical systems of torch light with the following classical state sets:
 $$\Sigma _1 = \{ OFF, ON \}$$  
 $$\Sigma _2 = \{ LOW, HIGH \}$$ 

* In this blog we will see how we can represent the torch light as the combination these two individual systems. Here $\Sigma _1$ represents the on-off state of the torch light and $\Sigma _2$ represents the brightness of the torch light. So we need way of mathematically representing these single systems together.

* Practically these individual systems together form a multiple system. In the above case this multiple system is formed by two individual systems $\Sigma _1$ and $\Sigma _2$ of the torch light. But in general the multiple systems can be formed by any number individual systems.

* So the multiple system is a combination of single systems together representing the complex system. Here multiple single systems comes together to represent the complex information about the complex systems.

> Remember that any particular multiple system can be considered as a single system itself. After that we can use that as a part of more complex systems. So at the end the terms Single or Mulitple is differtiated by only how do we think about a particular system. For example think of this torch light attached to more complex system like motor bike(like an head light). Now we can think of the torch light as a single system that is part of the more complex system like motor bike.


## How do we represent classical state multiple systems mathematically?

* So we have said that multiple system is formed by two or more individual systems. If each individual system has its own associated classical states, then the multiple system is represented by a cartesian product of classical state sets of these individual systems.

* For example In our torch light example we had two individual systems with classical state sets $\Sigma _1$ and $\Sigma _2$. We can represent a classical states of a torch light using the cartesian product of these individual system as follows. 

$$\Sigma = \Sigma _1 \times \Sigma _2 = \{ (OFF, LOW), (OFF, HIGH), (ON, LOW), (ON, HIGH)\}$$

* If you think that torch ligh has two switches one switch to make the torch light and ON or OFF and another one to change brightness HIGH or LOW, then here (ON, LOW) is one of the possible classical state of the torch light, where torch light is ON and its brightness is set to LOW. 

#### Cartesian Product to find the joined state set

* If you think more formally the cartesian product takes each element `a` of any set $\Sigma _1$ and pair it with each element `b` of another set $\Sigma _2$ to create single combined set $\Sigma$. We can formally define this as follows,

$$\Sigma_1 \times \Sigma_2 = \{ (a,b) : a \in \Sigma_1 \; and \; b \in \Sigma_2 \}$$

* We can generalize this idea to n number of classical systems each associated with finite non empty classical state sets.

$$\Sigma_1 \times \Sigma_2 \times ... \times \Sigma_n = 
\{ (a_1, a_2,...,a_n) :  a_1 \in \Sigma_1 ,\; a_2  \in \Sigma_2 ...a_n \in \Sigma_n \}$$

> **Important: The Order of elements of the cartesian product set** 
> * Here we assume that the elements of classical state sets($\Sigma _1$,$\Sigma _2$...$\Sigma _n$) are arranges in particular order(For example alphabetical order). Then when we find a cartesian product of these sets arrange them using the same ordering logic. The order in which we create a cartesian product doesn't matter as long as we keep the same ordering in all the places we use the cartesian product set. For example the same order must be used when representing a calssical state of a multiple system as a row or column vector.
> * We follow the notion of taking first element of first set and pair with each element of second set, then take the second element of the first set and pair with all the elements of the second set and so on. this idea can be generalized for any number of sets. For example we can do that by first combining first two sets as a single set and then combine thise new combined set with third set and so on(This can be recursively defined).

* Now we know that we can use the cardesian product to get classical state set of the multiple systems. We have used column vector to represent a state of the single system similarly here also we are going to use a column vector to represent a classical state of the multiple sytem. But here the column vector entries will be corresponding to the cartesian product set of the individual systems.

* For example the classical state of the torch light that is ON and with LOW brightness can be represented by the following column vector(we have added labels for each entry of the column vector. These labels corresponds to a classical state of the torch light).

$$ |light\rangle = 
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0\end{pmatrix} 
\begin{matrix} \rightarrow (OFF, LOW) 
\\  \rightarrow (OFF, HIGH) \\ \rightarrow(ON, LOW) \\ \rightarrow(ON, HIGH)\end{matrix}$$

* Here the order of entries doesn't matter as long as we use the same order in all the places.

### How can we represent the multiple Bits together?

* More formal example will be Bit. Remember that it has two classical states 0 or 1. Consider two such Bits $X_1$ and $X_2$ together represents some information. Here the classical state set $\Sigma_1$ and $\Sigma_2$ corresponds to the classical systems $X_1$ and $X_2$. 
$$
\Sigma _1 = \{ 0,1\} \; and \; 
\Sigma _2 = \{ 0,1 \}
$$

* Then we can get the classical state set of the multiple systems $(X_1,X_2)$ using the cartesian product of classical state sets of $X_1$ and $X_2$. The cartesian product of these two sets can be represented as follows,

$$ \Sigma _1 \times \Sigma _2 = \{(0,0), (0,1), (1,0), (1,1)\} = \{00,01,10,11\}$$

* `String:` Here you can notice that instead of using brackets and commas we are just representing each state of the joined system as just a string. This is very common and valid way of defining the classical state of the multiple system. In this case removing brackets and commas doesn't add any ambiguity or confusion. One useful thing to remember is that the formal definition of the string is also defined by the cartesian product of sets with symbols called alphabets.

* We can generalize this idea for any n number of Bits. For exmaple classical system $X$ with 10 bits $(X_1,X_2,...,X_{10})$ each with classical state set $\Sigma _1,\Sigma _2,...,\Sigma _{10}$ can be represented by the following cartesian product. Here we directly use the `string` format instead of using `tuple` format to represent each state.(There are total of $2^{10} = 1024$ such possible states of X)

$$\Sigma _1 \times \Sigma _2 \times ... \times \Sigma _{10} = \{0000000000, 0000000001, 0000000010, ..., 1111111111\}$$

* Similar to the single systems, we can use the Column vector we can represent the classical state of the two bits in a following way(we have added labels for each entry of the column vector that corresponding classical state of two bit system). Similary we can define the calsssical state vector for any n number of bits also.

$$ |b\rangle = 
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0\end{pmatrix} 
\begin{matrix} \rightarrow 00
\\  \rightarrow 01 \\ \rightarrow 10 \\ \rightarrow 11\end{matrix}$$



## How do we reprsent the probabilistic state of the multiple systems?

* Similar to the classical state of the multiple system we also represent probabilistic state of the multiple system using the column vector. Here each eantry of the column vector is the probability associated with the classical state that corresponds to that entry. **Here remember that by the classical state we mean the joined classical state of multiple systems.**

* For example the following vector represents a probabilistic state of joint system $(X_1,X_2)$ as `00 or (0,0)` with the probability 1/2 and `11 or (1,1)` with the probability 1/2. All the other states has the probability 0. (we have added classical state labels for each entry of the probability vector. Each entry corresponds to a probability associated with the labeled classical state).

$$ |p\rangle = 
\begin{pmatrix} \frac{1}{2} \\ 0 \\ 0 \\ \frac{1}{2}\end{pmatrix}
\begin{matrix} \rightarrow 00
\\  \rightarrow 01 \\ \rightarrow 10 \\ \rightarrow 11\end{matrix}
$$

* Similar to the single system, The sum of entries of the column vector that corresponds probabilistic state of the multiple system should also be equal to one. Then only we can say that the vector is a probability vector.

* The above given vector is an example of correlated probabilistic state where two bits always have the same state. We will see more about correlation when we discuss about the correlation and independence of multiple systems. 


## What do we mean by Independence and Correlation of multiple systems?

* We have seen that the multiple system is just a combination of single systems. If single systems $X_1, X_2, ... X_n$ together form a multiple system $(X_1, X_2,...,X_n)$, then the independence of these single system is about whether we can define the probability associated with the classical states of each of the single systems without depending on each other. 

### Independence between two single systems

* First we will learn about the independence between two single systems $X_1, X_2$ which together forms a joint systems $(X_1, X_2)$. Then we will move on to the independence of more than two systems case. We can define the independence between two system formally as follows,

$$$$



* We will take the following probabilistic state as an example to explain this.

$$|\psi\rangle = $$



### What is Tensor Product?