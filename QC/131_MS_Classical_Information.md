
# Classical Information(Multiple systems)

* As in a classical single system, In the multiple systems case also we will first see about the classical information and then go onto the quantum information in the next blog.


## What does the multiple systems mean?

* We have seen previously that the single system can represent some information using its classical states. For example we have seen torch light example with the classical states $\Sigma$ = {OFF, ON} and more formal single system was a Bit with classical states $\Sigma$ = {0, 1}.

* Remember that these single systems have a finite non empty set of classical states. So this means any particular classical system of this kind can only represent finite amount information. If you think about our world, it is made up of many complex systems(in our case it is called multiple systems). Intutively the complex systems are the combination of many same or different kind of single system. How can we mathematically reprsent these complex systems? so that we can process those information mathematically.

* For example, in the blog about single system and specifically in the torch light example, Individually we have used classical systems of torch light with the following classical state sets:
 $$\Sigma_1 = \{ OFF, ON \}$$  
 $$\Sigma_2 = \{ LOW, HIGH \}$$ 

* In this blog we will see how we can represent the torch light as the combination these two individual systems. Here $\Sigma_1$ represents the on-off state of the torch light and $\Sigma_2$ represents the brightness of the torch light. So we need way of mathematically representing these single systems together.

* Practically these individual systems together form a multiple system. In the above case this multiple system is formed by two individual systems $\Sigma_1$ and $\Sigma_2$ of the torch light. But in general the multiple systems can be formed by any number individual systems.

* So the multiple system is a combination of single systems together representing the complex system. Here multiple single systems comes together to represent the complex information about the complex systems.

> Remember that any particular multiple system can be considered as a single system itself. After that we can use that as a part of more complex systems. So at the end the terms Single or Mulitple is differtiated by only how do we think about a particular system. For example think of this torch light attached to more complex system like motor bike(like an head light). Now we can think of the torch light as a single system that is part of the more complex system like motor bike.


## How do we find classical state set multiple systems?

* So we have said that multiple system is formed by two or more individual systems. If each individual system has its own associated classical states, then the multiple system is represented by a cartesian product of classical state sets of these individual systems.

* For example In our torch light example we had two individual systems with classical state sets $\Sigma_1$ and $\Sigma_2$. We can represent a classical states of a torch light using the cartesian product of these individual system as follows. 

$$\Sigma = \Sigma_1 \times \Sigma_2 = \{ (OFF, LOW), (OFF, HIGH), (ON, LOW), (ON, HIGH)\}$$

* If you think that torch ligh has two switches one switch to make the torch light and ON or OFF and another one to change brightness HIGH or LOW, then here (ON, LOW) is one of the possible classical state of the torch light, where torch light is ON and its brightness is set to LOW. 

#### Cartesian Product to find the joined state set

* If you think more formally the cartesian product takes each element `a` of any set $\Sigma_1$ and pair it with each element `b` of another set $\Sigma_2$ to create single combined set $\Sigma$. We can formally define this as follows,

$$\Sigma_1 \times \Sigma_2 = \{ (a,b) : a \in \Sigma_1 \; and \; b \in \Sigma_2 \}$$

* We can generalize this idea to n number of classical systems each associated with finite non empty classical state sets.

$$\Sigma_1 \times \Sigma_2 \times ... \times \Sigma_n = 
\{ (a_1, a_2,...,a_n) :  a_1 \in \Sigma_1 ,\; a_2  \in \Sigma_2 ...a_n \in \Sigma_n \}$$

> **Important: The Order of elements of the cartesian product set** 
> * Here we assume that the elements of classical state sets($\Sigma_1$,$\Sigma_2$...$\Sigma _n$) are arranges in particular order(For example alphabetical order). Then when we find a cartesian product of these sets arrange them using the same ordering logic. The order in which we create a cartesian product doesn't matter as long as we keep the same ordering in all the places we use the cartesian product set. For example the same order must be used when representing a calssical state of a multiple system as a row or column vector.
> * We follow the notion of taking first element of first set and pair with each element of second set, then take the second element of the first set and pair with all the elements of the second set and so on. this idea can be generalized for any number of sets. For example we can do that by first combining first two sets as a single set and then combine thise new combined set with third set and so on(This can be recursively defined).

## How can we represent the state of the multiple systems mathematically?

* Now we know that we can use the cardesian product to get classical state set of the multiple systems. Then how can we reporesent the state of the joined system mathematically? Its simple we are going to use same idea as single system, We are going to use a column vector to represent a classical state of the multiple sytems. But here the column vector entries will be corresponding to the cartesian product set of the individual systems.

* For example the classical state of the torch light that is ON and with LOW brightness can be represented by the following column vector(we have added labels for each entry of the column vector. These labels corresponds to a classical state of the torch light).

$$ |light\rangle = 
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0\end{pmatrix} 
\begin{matrix} \rightarrow (OFF, LOW) 
\\  \rightarrow (OFF, HIGH) \\ \rightarrow(ON, LOW) \\ \rightarrow(ON, HIGH)\end{matrix}$$

* Here the order of entries doesn't matter as long as we use the same order in all the places.

### Representing multiple Bits using column vector

* More formal example will be Bit. Remember that it has two classical states 0 or 1. Consider two such Bits $X_1$ and $X_2$ together represents some information. Here the classical state set $\Sigma_1$ and $\Sigma_2$ corresponds to the classical systems $X_1$ and $X_2$. 
$$
\Sigma_1 = \{ 0,1\} \; and \; 
\Sigma_2 = \{ 0,1 \}
$$

* Then we can get the classical state set of the multiple systems $(X_1,X_2)$ using the cartesian product of classical state sets of $X_1$ and $X_2$. The cartesian product of these two sets can be represented as follows,

$$ \Sigma_1 \times \Sigma_2 = \{(0,0), (0,1), (1,0), (1,1)\} = \{00,01,10,11\}$$

* `String:` Here you can notice that instead of using brackets and commas we are just representing each state of the joined system as just a string. This is very common and valid way of defining the classical state of the multiple system. In this case removing brackets and commas doesn't add any ambiguity or confusion. One useful thing to remember is that the formal definition of the string is also defined by the cartesian product of sets with symbols called alphabets.

* We can generalize this idea for any n number of Bits. For exmaple classical system $X$ with 10 bits $(X_1,X_2,...,X_{10})$ each with classical state set $\Sigma_1,\Sigma_2,...,\Sigma _{10}$ can be represented by the following cartesian product. Here we directly use the `string` format instead of using `tuple` format to represent each state.(There are total of $2^{10} = 1024$ such possible states of X)

$$\Sigma_1 \times \Sigma_2 \times ... \times \Sigma_{10} = \{0000000000, 0000000001, 0000000010, ..., 1111111111\}$$

* Similar to the single systems, we can use the Column vector we can represent the classical state of the two bits in a following way(we have added labels for each entry of the column vector that corresponding classical state of two bit system). Similary we can define the calsssical state vector for any n number of bits also.

$$ |b\rangle = 
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0\end{pmatrix} 
\begin{matrix} \rightarrow 00
\\  \rightarrow 01 \\ \rightarrow 10 \\ \rightarrow 11\end{matrix}$$



## What is the probabilistic state of the multiple systems?

* Similar to single system being in probabilistic state the multiple systems also can be in the probabilistic states. Until we learn the classical state of the multiple systems we associate some probability values for each of the classical state of the multiple system. This is called the probabilistic state of the multiple systems.

* Similar to the classical state of the multiple system we also represent probabilistic state of the multiple system using the column vector. Here the only difference is that each entry of the column vector is the probability associated with the classical states of the multiple system. **Here remember that by the classical state we mean the joined classical state of multiple systems(which we can find using the cartesian product of the classical states sets of the individual systems).**

* As we have seen in previous section, Let $X_1$ and $X_2$ represent two Bits with classical state sets $\Sigma_1$ and $\Sigma_2$. Then the following vector represents a probabilistic state of joint system $(X_1,X_2)$ as `00 or (0,0)` with the probability 1/2 and `11 or (1,1)` with the probability 1/2. All the other states has the probability 0. (we have added classical state labels for each entry of the probability vector. Each entry corresponds to a probability associated with the labeled classical state).

$$ |p\rangle = 
\begin{pmatrix} \frac{1}{2} \\ 0 \\ 0 \\ \frac{1}{2}\end{pmatrix}
\begin{matrix} \rightarrow 00
\\  \rightarrow 01 \\ \rightarrow 10 \\ \rightarrow 11\end{matrix}
$$

* Similar to the single system, The sum of entries of the column vector that corresponds probabilistic state of the multiple system should also be equal to 1. Then only we can say that this vector is a probability vector.

* The above given vector is an example of correlated probabilistic state where two bits always have the same state. We will see more about correlation when we discuss about the correlation and independence of multiple systems. 


## What do we mean by Independence and Correlation of multiple systems?

* We have seen that the multiple system is just a combination of single systems. Two systems are said to be independent if learning the classical state of the each of the system doesn't depen on the other one. First we will the independence between two systems then we can easily generalise that idea for the mulitple systems with more than two individual systems.

### Independence between two single systems

* First we will define the multiple systems $(X_1, X_2)$ represented by a probabilistic column vector $|\psi\rangle$. Here both $X_1$ and $X_2$ are classical systems that represent a Bit with classical state set $\Sigma_1 = \{0,1\}$ and $\Sigma_2 = \{0,1\}$ as we discussed in the previous section.

* Here the current probabilistic state of Bits $X_1$ and $X_2$ are represented by the column vectors $|\psi_1\rangle$ and $|\psi_2\rangle$ respectively. We can define these vectors mathematically as follows.

$$|\psi_1\rangle = \sum_{a \in \Sigma_1} p_a |a\rangle$$

$$|\psi_2\rangle = \sum_{b \in \Sigma_2} q_b |b\rangle$$

$$|\psi\rangle = \sum_{(a,b) \in \Sigma_1 \times \Sigma_2} r_{ab} |ab\rangle$$

* Here $p_a$ and $q_b$ are probability value associated with each classicate state of the Bits $X_1$ and $X_2$. The probability value $r_{ab}$ is the probability associated with each classical state of the joint system $(X_1,X_2)$. 

* Even though we already know this I want to remaind that $|a\rangle$ and $|b\rangle$ are column vectors that represents the classical states of the systems $X_1$ and $X_2$. The column vector $|ab\rangle$ is the column vector that corresponds to the classicate state of the joint system $(X_1, X_2)$.

* We say that these two systems $X_1$ and $X_2$ are independent when they are probabilistically independent from each other.

#### What is the probabilistic independence?

* We take the same systems $X_1$ and $X_2 to explain this idea. We say that the systems $X_1$ and $X_2$ are probabilistically independent when the probability associated with individual system doesn't depend on each other. We can define this formally as follows,

$$ P((X_1,X_2) = (a, b)) = P(X_1=a)P(X_2=b)$$

* This equation tells that the probability that the joint system $(X_1,X_2)$ is in a state $(a,b)$ is the multiplication of the probabilities that states of $X_1 = a$ and $X_2 = b$.

* Now we can apply the column vectors we have defined to this formula to get this formal definition in terms of Dirac notation.

### What is Tensor Product?