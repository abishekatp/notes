
# Classical Information(Multiple systems)

* As in a classical single system, In the multiple systems case also we will first see about the classical information and then go onto the quantum information in the next blog.


## What does the multiple systems mean?

* We have seen previously that the single system can represent some information using its classical states. For example we have seen torch light example with the classical states $\Sigma$ = {OFF, ON} and more formal single system was a Bit with classical states $\Sigma$ = {0, 1}.

* These single systems should have a finite non empty set of classical states. This means any particular classical system of this kind can only represent finite amount information. And also If you think about our world, it is made up of many complex systems. How can we mathematically reprsent these complex systems? so that we can process those information using devices like computers.

* For example, in the blog about single system and specifically in the torch light example, Individually we have used classical systems with the following classical state sets:
 $$\Sigma _1 = \{ OFF, ON \}$$  
 $$\Sigma _2 = \{ LOW, HIGH \}$$ 

* In this blog we will see how we can represent the torch light as the combination these two individual systems. Here $\Sigma _1$ represents the on-off state of the torch light and $\Sigma _2$ represents the brightness of the torch light. So we need way of mathematically representing these single systems together.

* Practically these individual systems together represents a complex system torch light. In the above case this complex system is formed by two individual systems $\Sigma _1$ and $\Sigma _2$. But in general the complex or multiple systems can be formed by any number individual systems.

* So the multiple system is a combination of single systems together representing the complex system. Here multiple single systems comes together to represent the complex information about the complext systems.

> Remember that any particular complex system can be considered as a single system itself. Later which can be part of more complex system. So at the end the terms Single or Mulitple is differtiated by only how do we think about a particular system. For example think of this torch light attached to more complex system like motor bike(like an head light). Now we can think of the torch light as a single system that is part of the more complex system like motor bike.


## How do we represent multiple systems mathematically?

* So we have said that multiple system is formed by two or more individual systems. If each individual system has its own associated classical states, then the multiple system is represented by a cartesian product of classical state sets of these individual systems.

* For example In our torch light example we had two individual systems with classical state sets $\Sigma _1$ and $\Sigma _2$. We can represent a classical states of a torch light using the cartesian product of these individual system as follows. 

$$\Sigma = \Sigma _1 \times \Sigma _2 = \{ (OFF, LOW), (OFF, HIGH), (ON, LOW), (ON, HIGH)\}$$

* If you think that torch ligh has two switches one switch to make the torch light and ON or OFF and another one to make brightness HIGH or LOW, then here (ON, LOW) is one of the possible classical state of the torch light, where torch light is ON and its brightness is set to LOW. 

#### Cartesian Product

* If you think more formally the cartesian product takes each element `a` of any set $\Sigma _1$ and pair it with each element `b` of another set $\Sigma _2$ to create single combined set $\Sigma$. We can formally define this as follows,

$$\Sigma_1 \times \Sigma_2 = \{ (a,b) : a \in \Sigma_1 \; and \; b \in \Sigma_2 \}$$

* We can generalize this idea to n number of classical systems each associated with finite non empty classical state sets as follows.

$$\Sigma_1 \times \Sigma_2 \times ... \times \Sigma_n = 
\{ (a_1, a_2,...,a_n) :  a_1 \in \Sigma_1 ,\; a_2  \in \Sigma_2 ...a_n \in \Sigma_n \}$$

> **Important: The Order of elements of the set** 
> * Here we assume that the elements of classical state sets($\Sigma _1$,$\Sigma _2$...$\Sigma _n$) are ordered in particular way(For example alphabetical order). Then when we find a cartesian product of these sets using the same order as the base. Whatever order we create a cartesian product set doesn't matter as long as we keep the same ordering in all the places we use them. For example the same order must be used when representing a calssical state of a multiple system as a row or column vector.
> * We follow the notion of taking first element of first set and pair with each element of second set, then take the second element of the first set and pair with all the elements of the second set and so on. this idea can be generalized for any number of sets. For example we can do that by first combining first two sets as a single set and then combine thise new combined set with third set and so on(This can be recursively defined).

* Now we know that we can use the cardesian product to get classical state set of the multiple systems. We used column vector to represent a state of the single system similarly here also we will use a column vector to represent a classical state of the multiple sytem. 

* For example the classical state of the torch light that is ON and with LOW brightness can be represented by the following column vector(we have added labels for each entry of the column vector that corresponding classical state of the torch light).

$$ |light\rangle = 
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0\end{pmatrix} 
\begin{matrix} \rightarrow (OFF, LOW) 
\\  \rightarrow (OFF, HIGH) \\ \rightarrow(ON, LOW) \\ \rightarrow(ON, HIGH)\end{matrix}$$

* Here each entry corresponds to one of the classical state of the torch light. Here the order of entries doesn't matter as long as we use the same order in all the places.

#### Bit

* More formal example will be Bit. Remember that it has two classical states 0 or 1. Consider two such Bits $X_1$ and $X_2$ together represents some information.
$$
\Sigma _1 = \{ 0,1\} \; and \; 
\Sigma _2 = \{ 0,1 \}
$$

* Then we can get the classical state set of the joint system $(X_1,X_2)$ using the cartesian product of classical state sets of $X_1$ and $X_2$. The cartesian product of these two sets can be represented as follows,

$$ \Sigma _1 \times \Sigma _2 = \{(0,0), (0,1), (1,0), (1,1)\} = \{00,01,10,11\}$$

* `String:` Here you can notice that instead of using brackets and commas we are just representing each state of the joined system as just a string. This is very common and valid way of defining the classical state of the multiple system. In this case removing brackets and commas doesn't add any ambiguity or confusion. One useful thing to remember is that the formal definition of the string is also defined by the cartesian product of sets with symbols called alphabets.

* We can generalize this idea for any n number of Bits. For exmaple classical system $X$ with 10 bits $(X_1,X_2,...,X_{10})$ each with classical state set $\Sigma _1,\Sigma _2,...,\Sigma _{10}$ can be represented by the following cartesian product. Here we directly use the `string` format instead of using `tuple` format to represent each state.(There are total of $2^{10} = 1024$ such possible states of X)

$$\Sigma _1 \times \Sigma _2 \times ... \times \Sigma _{10} = \{0000000000, 0000000001, 0000000010, ..., 1111111111\}$$

* Using the Column vector we can represent the classical state of the two bits in a following way(we have added labels for each entry of the column vector that corresponding classical state of two bit system). Similary we can define the calsssical state vector for any n number of bits also.

$$ |b\rangle = 
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0\end{pmatrix} 
\begin{matrix} \rightarrow 00
\\  \rightarrow 01 \\ \rightarrow 10 \\ \rightarrow 11\end{matrix}$$



## How do we reprsent the probabilistic state of the classical system?

* Similar to the classical state of the multiple system we also represent probabilistic state of the multiple system using the column vector. Here each eantry of the column vector is the probability associated with the classical state that corresponds to that entry. **Here remember that by the classical state we mean the combined classical state of the multiple systems.**

* For example the following vector represents a state of two bits $(X_1,X_2)$ as `00 or (0,0)` with the probability 1/2 and `11 or (1,1)` with the probability 1/2. All the other states has the probability 0. (we have added classical states as a label for each entry of the probability vector. Each entry corresponds to a probability associated with the labeled classical state).

$$ |p\rangle = 
\begin{pmatrix} \frac{1}{2} \\ 0 \\ 0 \\ \frac{1}{2}\end{pmatrix}
\begin{matrix} \rightarrow 00
\\  \rightarrow 01 \\ \rightarrow 10 \\ \rightarrow 11\end{matrix}
$$

* In the case of multiple system also the sum of values in the each entry of the column vector should add upto 1. Then only we can say that the vector is a probability vector.

* The above given vector is an example of correlated probabilistic state where two bits always have the same state. We will see more about this when we discuss about the correlation and independence of multiple systems. 


## What do we mean by Independence and Correlation of classical systems?

* We have seen that the multiple system is just a combination of classical systems. This directly implies that the independence of the classical systems: It asks whether we can represent the multiple system as a 




### What is Tensor Product?