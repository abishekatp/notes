
# Classical Information(Multiple systems)

* As in a classical single system, In the multiple systems case also we will first see about the classical information and then go onto the quantum information in the next blog.


## What does the multiple systems mean?

* We have seen previously that the single system can represent some information using its classical states. For example we have seen torch light example with the classical states $\Sigma$ = {OFF, ON} and more formal single system was a Bit with classical states $\Sigma$ = {0, 1}.

* Remember that the single system have a finite non empty set of classical states. So this means any particular classical system of this kind can only represent finite amount information. If you think about our world, it is made up of many complex systems(in our case it is called multiple systems). Intutively the complex systems are the combination of many same or different kind of single system. How can we mathematically reprsent these multiple systems? so that we can process those information mathematically.

* For example, in the blog about single system and specifically in the torch light example, Individually we have used classical systems of torch light with the following classical state sets:
 $$\Sigma_1 = \{ OFF, ON \}$$  
 $$\Sigma_2 = \{ LOW, HIGH \}$$ 

* In this blog we will see how we can represent the torch light as the combination these two individual systems. Here $\Sigma_1$ represents the on-off state of the torch light and $\Sigma_2$ represents the brightness of the torch light. So we need way of mathematically representing these single systems together.

* Practically these individual systems together form a multiple system. In the above case this multiple system is formed by two individual systems $\Sigma_1$ and $\Sigma_2$ of the torch light. But in general the multiple systems can be formed by any number individual systems.

* So the multiple system is a combination of single systems together representing the complex system. Here multiple single systems comes together to represent the complex information about the complex systems.

> Remember that any particular multiple system can be considered as a single system itself. After that we can use that as a part of more complex systems. So at the end the terms Single or Mulitple is differtiated by only how do we think about a particular system. For example think of this torch light attached to more complex system like motor bike(like an head light). Now we can think of the torch light as a single system that is part of the more complex system like motor bike.


## How do we find classical state set multiple systems?

* So we have said that multiple systems is formed by two or more single system. If each of the single system has its own associated classical states set, then the multiple systems are represented by the cartesian product of classical state set of each of the single systems.

* For example In our torch light example we had two single systems with classical state sets $\Sigma_1$ and $\Sigma_2$. We can represent a classical states of a torch light using the cartesian product of these single systems as follows. 

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

* Now we know that we can use the cardesian product to get classical state set of the multiple systems. Then how can we represent the state of the joined system mathematically? Its simple, we are going to use same idea as a single system, We are going to use a column vector to represent a classical state of the multiple sytems. But here the column vector entries will correspond to the classical state set(which we got using the cartesian product) of the multiple systems.

* For example the classical state of the torch light that is ON and with LOW brightness can be represented by the following column vector(we have added labels for each entry of the column vector. These labels corresponds to a classical state of the torch light).

$$ |light\rangle = 
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0\end{pmatrix} 
\begin{matrix} \rightarrow (OFF, LOW) 
\\  \rightarrow (OFF, HIGH) \\ \rightarrow(ON, LOW) \\ \rightarrow(ON, HIGH)\end{matrix}$$

* Here the order of entries doesn't matter as long as we use the same order in all the places.

### Representing multiple Bits using column vector

* More formal example will be Bit. Remember that it has two classical states 0 or 1. Consider two such bits $X_1$ and $X_2$ together represents some information. Here the classical state set $\Sigma_1$ and $\Sigma_2$ corresponds to the bits $X_1$ and $X_2$. 
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

* We have seen that the multiple system is just a combination of single systems. Two systems are said to be independent if learning the classical state of the each of the system doesn't depend on the other one. In other words learning the classical state of the any one system doesn't give any information about the other system.
* First we will the independence between two systems then we can easily generalise that idea for the mulitple systems with more than two individual systems.

### Independence between two single systems

* First we will define the multiple systems $(X_1, X_2)$ represented by a probabilistic column vector $|\psi\rangle$. Here both $X_1$ and $X_2$ are classical bit with classical state set $\Sigma_1 = \{0,1\}$ and $\Sigma_2 = \{0,1\}$ as we discussed in the previously.

* Here the current probabilistic state of Bits $X_1$ and $X_2$ are represented by the column vectors $|\psi_1\rangle$ and $|\psi_2\rangle$ respectively. We can define these vectors mathematically as follows.

$$|\psi_1\rangle = \sum_{a \in \Sigma_1} p_a |a\rangle$$

$$|\psi_2\rangle = \sum_{b \in \Sigma_2} q_b |b\rangle$$

$$|\psi\rangle = \sum_{(a,b) \in \Sigma_1 \times \Sigma_2} r_{ab} |ab\rangle$$

* Here $p_a$ and $q_b$ are probability value associated with each classicate state of the Bits $X_1$ and $X_2$. The probability value $r_{ab}$ is the probability associated with each classical state of the joint system $(X_1,X_2)$. 

* Even though already we know this I want to remaind that $|a\rangle$ and $|b\rangle$ are column vectors that represents the classical states of the systems $X_1$ and $X_2$. The column vector $|ab\rangle$ corresponds to the classicate state of the joint system $(X_1, X_2)$.

* We say that these two systems $X_1$ and $X_2$ are independent when they are probabilistically independent from each other. Then Correlation between two systems is defined as lack of independence. If two systems are not independent, then they are correlated.

#### What is the probabilistic independence?

* Two events are said to be independent if probability outcome of an one event doesn't affect the probability outcome of the other event. 

* We take the same systems $X_1$ and $X_2 to explain this idea. We say that the systems $X_1$ and $X_2$ are probabilistically independent when the probability associated with the system doesn't depend on each other. We can define this formally as follows,

$$ P((X_1,X_2) = (a, b)) = P(X_1=a)P(X_2=b)$$

* This equation tells that the probability that the joint system $(X_1,X_2)$ is in a state $(a,b)$ is the multiplication of the probabilities that states of $X_1 = a$ and $X_2 = b$. We can define this for the probability $r_{ab}$ as follows.
$$ r_{ab} = p_a q_b$$

* This will be true for each classical state $a \in \Sigma_1$ and $ b \in \Sigma_2$. That means regardless of whatever state the single system $X_1$ and $X_2$ are in the probability associated with the multiple systems $(X_1,X_2)$ is always the multiplication of the probability associated with each of the single system. We can define this idea more formally using the tensor product.

### How does tensor product represents independence?

* So to define the independece of the single systems that make up the multiple systems can be done using the Dirac notation and tensor product. If we can write down the classical state of the multiple systems as a tensor produc of classical state of each of the single system then we can say that each of these single system as independent systems.

* We can take the same definition of probability vectors $|\psi_1\rangle$ and $|\psi_2\rangle$ that corresponds to a single systems $X_1$ and $X_2$ respectively. The probability vector $|\psi\rangle$ that corresponds to a multiple systems $(X_1, X_2)$. Then we say that $|\psi_1\rangle$ and $|\psi_2\rangle$ independent if we show the following.

$$ |\psi\rangle = |\psi_1\rangle \otimes |\psi_2\rangle$$

* Here the $|\psi\rangle$ is called the product vector. Here remember that the dirac notation `ket` represents column vector. So the tensor product is more of a natural way of multiplying a column vector( or row vector) with another column vector(or row vector). 


> **Notations for tensor product**: The following are the equivalent notation for representing tensor product of two vectors $|a\rangle$ and $|b\rangle$.
> $$|a\rangle \otimes |b\rangle \equiv |a\rangle|b\rangle \equiv |ab\rangle \equiv |a \otimes b\rangle
\equiv |(a,b)\rangle \equiv |a,b\rangle$$
>  Here the most common notations are $|a\rangle \otimes |b\rangle$, $|a\rangle|b\rangle$ and $|ab\rangle$.

* The tensor product of two vecotors $|\psi_1\rangle$ and $|\psi_2\rangle$ can be done in a following way.


$$
|\psi_1\rangle \otimes |\psi_2\rangle = 
\begin{pmatrix} a_1 \\ a_2 \\ ... \\ a_n\end{pmatrix} \otimes
\begin{pmatrix}b_1 \\ b_2 \\ ... \\ b_n \end{pmatrix} = 
\begin{pmatrix} a_1b_1 \\ a_1b_2 \\ ... \\a_1b_n \\ a_2b_1 \\ a_2b_2\\ ... \\ a_2b_n \\ ...\\ a_nb_1 \\ ... \\ a_nb_n\end{pmatrix}
$$

> **Bilinearity of tensor product:** Tensor product is bilinear that means it is linear with respect both first and second arugument. The following equations describe this better. Suppose if we have column vectors $|a\rangle$, $|b\rangle$ and $|c\rangle$, then we can define the bilinearity as follows.
>Linear in first argument
>$$(|a\rangle + |b\rangle) \otimes |c\rangle = |a\rangle \otimes |c\rangle + |b\rangle \otimes |c\rangle$$
>$$(k|a\rangle) \otimes |b\rangle = k(|a\rangle \otimes |b\rangle)$$
>Linear in second argument
>$$|a\rangle  \otimes  (|b\rangle + |c\rangle) = |a\rangle \otimes |b\rangle + |a\rangle \otimes |c\rangle$$
>$$|a\rangle \otimes (k|b\rangle) = k(|a\rangle \otimes |b\rangle)$$


* Another way to define the probability vector $|\psi\rangle$ is by defining individual elements of the vector separately for each $a \in \Sigma_1$ and $b \in \Sigma_2$.

$$ \langle ab|\psi\rangle = \langle a|\psi_1\rangle \langle b|\psi_2\rangle$$

* Here note that in the LHS we are multiply two row vector(using a `bra` notation) $\langle a|$ and $\langle b|$ to get a classical state vector for the joint system $(X_1,X_2)$. Then we are multiplying resulting vector with a current state(in `ket` notation) $|\psi\rangle$ to get a real number result. The resulting real number will be the probability associated with the classical state $|ab\rangle$. 

* Similarly in the RHS also we are multiplying row vector $\langle a|$ or $\langle b|$ with the column vector $|\psi_1\rangle$ or $|\psi_2\rangle$ respectively to get a probaility values.


#### Example of Independence

* So we use the bits $X_1$ and $X_2$ here also. Suppose we have the probability vector $|\psi\rangle$ that represent the multiple systems $(X_1,X_2)$. Then in the following derivation we are trying to derive that $|\psi\rangle = |\psi_1\rangle |\psi_2\rangle$

$$
\begin{split}
|\psi\rangle & = \frac{4}{9}|00\rangle + \frac{2}{9}|01\rangle + \frac{2}{9}|10\rangle + \frac{1}{9}|11\rangle 

\\ &\equiv \frac{4}{9}|0\rangle|0\rangle + \frac{2}{9}|0\rangle|1\rangle + \frac{2}{9}|1\rangle|0\rangle + \frac{1}{9}|1\rangle|1\rangle

\\ &= \frac{2}{3}|0\rangle \left( \frac{2}{3} |0\rangle + \frac{1}{3} |1\rangle \right) + \frac{1}{3}|1\rangle \left(\frac{2}{3} |0\rangle + \frac{1}{3} |1\rangle \right) 

\\ &= \left(\frac{2}{3}|0\rangle + \frac{1}{3}|1\rangle \right) \otimes \left(\frac{2}{3} |0\rangle + \frac{1}{3} |1\rangle \right)

\\ &= |\psi_1\rangle \otimes |\psi_2\rangle = |\psi_1\rangle|\psi_2\rangle
\end{split}
$$

>**Important:** Here learning the classical state of the bit $X_1$ doesn't give any information about the bit $X_2$. This is how we defined the independence. 
>* Regardless of whatever the classical state the bit $X_1$, the probability associated with the bit $X_2$ is same. The probabilistic state of the $X_2$ is always $\left(\frac{2}{3} |0\rangle + \frac{1}{3} |1\rangle \right)$.



* In the above derivation you can see how we can find the probabilities associated with single systems $X_1$ and $X_2$ in a formal way. we could have factored the term $\frac{4}{9} =\frac{2}{3} \times \frac{2}{3} = \frac{2}{9} \times 2$. But we have done in a specific way to make sure that the sum of probabilities of single system should add upto 1. Note that $\frac{2}{2} +\frac{1}{3} = 1$. (**Note**: Remember that the probability should add upto 1 in any probability vector.)

* Also If you multiply the probabilities associated with $|0\rangle$ and $|0\rangle$ then you will the the probability for the $|00\rangle$. (e.g. $\frac{2}{3} \times \frac{2}{3} = \frac{4}{9}$)


#### Example of Correlation

* Suppose we have the following probability vector $|\psi\rangle$ that represents some probabilistic state of $(X_1,X_2)$. We will try to write it as the product of two probability vectors.

$$
\begin{split}
|\psi\rangle & = \equiv \frac{3}{7}|0\rangle|0\rangle + \frac{1}{7}|0\rangle|1\rangle + \frac{2}{7}|1\rangle|0\rangle + \frac{1}{7}|1\rangle|1\rangle

\\ &= |0\rangle \left( \frac{3}{7} |0\rangle + \frac{1}{7}|1\rangle \right) + |1\rangle  \left( \frac{2}{7} |0\rangle +  \frac{1}{7} |1\rangle \right) 
\end{split}
$$

* Here we can't go any further so we can't wirte this probability vector as a tensor product of two individual probability vectors. That means these two bits are correlated.

>Another way of thinking about this is, Here learning the calssical state of $X_1$ does give us some information about the classical state of $X_2$. the probability vecotor for $X_2$ is differs, when $X_1$ is in classical state $|0\rangle$ and in the state $|1\rangle$

* Another good example of correlation is the following vector. Here the $|X_1\rangle$ and $|X_2\rangle$ can always be in the same state either $|0\rangle$ or $|1\rangle$.

$$ |\psi\rangle = \frac{1}{2}|00\rangle + \frac{1}{2}|11\rangle$$

* Here the probability value 1/2 has no special importance. It can be any fraction as long as the probability values add upto 1.


### Independence of three or more systems

Independence of three or more systems can be define similar to the independence between two systems. If the multiple system $(X_1,X_2,...,X_n)$ is represented by probability vectors $|\psi\rangle$ and single systems $X_1,X_2,...,X_n$ are individually represented by the probability vectors $|\psi_1\rangle, |\psi_2\rangle, ..., |\psi_n\rangle$, then we say these single systems are independent when we can write the $|\psi\rangle$ as the product of the probability vectors $|\psi_1\rangle, |\psi_2\rangle, ..., |\psi_n\rangle$. It is formally defined as follows,

$$|\psi\rangle = |\psi_1\rangle \otimes |\psi_2\rangle \otimes ... \otimes |\psi_n\rangle$$

*  Similar to the two systems we can also define a linearity with respect each argument of the three or more systems when all the other arguments are fixed. This is called multilinearity.

* In the same way we defined the probability vector $|\psi\rangle$ in alternate way in two systems case, Here also we can do that for each $a_1 \in \Sigma_1$, $a_2 \in \Sigma_2$,...,$a_n \in \Sigma_n$ in the following way,

$$ \langle a_1 a_2 ... a_n|\psi\rangle = \langle a_1|\psi_1\rangle \langle a_2|\psi_2\rangle...\langle a_n|\psi_n\rangle$$

* One more thing to note is we can recursively define the tensor product of n vector. The logic goes like this to compute the tensor product n vectors, first get the tesnor product of n-1 vectors and multiply it with n'th vector. To compute the tendor product of n-1 vector first get the tesnor product of n-2 vectors and then multiply it with the (n-2)'th vector. This will go on like this until there are just two vectors to multiply. The initial state of this recursive product is given below.

$$|\psi\rangle = (|\psi_1\rangle \otimes |\psi_2\rangle \otimes ... \otimes |\psi_{n-1}) \otimes |\psi_n\rangle$$


## What does the measurement mean in the multiple systems settings?

* It is similar to the measurement of a single system but here we measure the classical state of the joint system. We have said that we can consider a multiple system as a single system. If we think in that way, then before measuring the joint system, it will be in some probabilitic state. As soon as we measure it, we will know the classical state of the joint system.(In a way the action of measurement is also an operation applied on the probability vector. We will see difference between )

$$ |\psi\rangle = \frac{1}{2}|00\rangle + \frac{1}{2}|11\rangle$$

* For example when we measure the above vector we will get the classical state $|00\rangle$ with probability $\frac{1}{2}$ and classical state $|11\rangle$ with probability $\frac{1}{2}$. So as soon as we measure it we will get one of these states as result.

### Partial Measurement

* What if we just measure the subset of the multiple systems? measuring the subset of the multiple systems is similar to measuring just one of the two systems. We can think of subset of systems that we measure as a single system and all the remaining systems as another single system. So we will first see the two system case, then generalise that idea to more than two systems.