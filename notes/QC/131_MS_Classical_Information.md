
# Classical Information(Multiple systems)

As in a classical single system(also we can think of them as a simple systems), In the multiple systems(Also we can think of this as complex systems) case also we will first see about the classical information and then go onto the quantum information in the next blog.

### What does the multiple systems mean?

As we have discussed in the classical systems the concept of single or multiple systems can be defined as per our needs. Commonly we consider a simple systems like a bit or a qbit as a single system and use the combination them to create more complex systems. We will use ideas from this blog to combine multiple simple systems together to describe more complex systems.

### Why do we need multiple systems?

Our world is made up of complex systems. If we create a single classical system with so many classical states, then we might be able represent these complex systems mathematically. But this idea of just increasing the number of classical states to represent a more complex systems is not a scallable idea. So if we first define a simple classical systems with small number of classical states such as bit, then we can use the ideas from this blog to represent more complex systems.

Intutively the complex systems are the combination of many same or different kind of simple system. How can we mathematically reprsent these multiple systems so that we can process those information mathematically?

> **Note:** \
> * Important: Remember that any particular multiple system can be considered as a single system itself. After that we can use that as a part of more complex systems. \
> * So at the end the terms Single or Mulitple is differtiated by only how we think about a particular system. For example think of this torch light attached to more complex system like motor bike(like an head light). In that case we will think of the torch light as a single system that is part of the more complex system like a motor bike.
> * This is going to be key idea behind how we are going to measure or apply some operations on the multiple systems. We consider multiple systems together as single big system and use the same ideas which we have used in the single systems



In this blog we will see how we can represent the torch light as the combination these two individual systems. Here $\Sigma_1$ represents the on-off state of the torch light and $\Sigma_2$ represents the brightness of the torch light. So we need way of mathematically representing these single systems together.

Practically these individual systems together form a multiple system. In the above case this multiple system is formed by two individual systems $\Sigma_1$ and $\Sigma_2$ of the torch light. But in general the multiple systems can be formed by any number individual systems.

### How do we find classical state set multiple systems?

If there are two are more single systems, then we can find the classical state set of the joint multiple systems by finding the cartesian product of the classical state sets of the single systems.

For example, lets take an torch light example from our previous blogs, Individually we have used two classical systems one for ON/OFF infor and another is battery brightness:
 $$\Sigma_1 = \{ OFF, ON \}$$  
 $$\Sigma_2 = \{ LOW, HIGH \}$$ 

If each of the single system has its own associated classical states set as defined above, then the multiple systems are represented by the cartesian product of classical state set of each of the single systems. We can represent a classical states of a torch light using the cartesian product of these single systems as follows. 

$$\Sigma = \Sigma_1 \times \Sigma_2 = \{ (OFF, LOW), (OFF, HIGH), (ON, LOW), (ON, HIGH)\}$$

If you think that torch ligh has two switches one switch to make the torch light and ON or OFF and another one to change brightness HIGH or LOW, then here (ON, LOW) is one of the possible classical state of the torch light, where torch light is ON and its brightness is set to LOW. 

### What is cartesian product?

If you think more formally the cartesian product takes each element `a` of any set $\Sigma_1$ and pair it with each element `b` of another set $\Sigma_2$ to create single combined set $\Sigma$. We can formally define this as follows,

$$\Sigma_1 \times \Sigma_2 = \{ (a,b) : a \in \Sigma_1 \; and \; b \in \Sigma_2 \}$$

We can generalize this idea to n number of classical systems each associated with finite and non empty classical state sets.

$$\Sigma_1 \times \Sigma_2 \times ... \times \Sigma_n = 
\{ (a_1, a_2,...,a_n) :  a_1 \in \Sigma_1 ,\; a_2  \in \Sigma_2 ...a_n \in \Sigma_n \}$$

### What about the order of elements in the cartesian product set?

When we describe the state of the system as column or row vector the order of the states plays crucial role. If we use different order in different part of our calculation, then we won't get a correct answer. So the order in which the cartesian product set is defined is also an important thing to consider.

* Here we assume that the elements of classical state sets($\Sigma_1$,$\Sigma_2$...$\Sigma _n$) are arranged in particular order(For example alphabetical order). Then when we find a cartesian product of these sets and arrange them using the same ordering logic. The order in which we create a cartesian product doesn't matter as long as we keep the same ordering in all the places wherever we use the cartesian product set. For example the same order must be used when representing a calssical state of a multiple system as a row or column vector.

* We follow the notion of taking first element of first set and pair with each element of second set, then take the second element of the first set and pair with all the elements of the second set and so on. This idea can be generalized for any number of sets by recursively combining always the first two sets. For example we can do that by first combining first two sets as a single set and then combine this new cartesian product set with third set and so on.

### Can we still use vector notation to represent the state of the multiple systems?

We know that we can use the cardesian product to get classical state set of the multiple systems. Then we can use a column vector to represent a classical state of the multiple sytems in a same way as single systems. But here the column vector entries will correspond to the cartesian product set(which we got using the cartesian product of classical state sets of single systems) of the multiple systems.

For example the classical state of the torch light that is ON and with LOW brightness can be represented by the following column vector(we have added labels for each entry of the column vector. These labels corresponds to a classical state of the torch light).

$$ |light\rangle = 
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0\end{pmatrix} 
\begin{matrix} \rightarrow (OFF, LOW) 
\\  \rightarrow (OFF, HIGH) \\ \rightarrow(ON, LOW) \\ \rightarrow(ON, HIGH)\end{matrix}$$

Here the order of entries doesn't matter as long as we use the same order in all the places.

### Representing multiple bits using column vector

More formal example will be Bit. Remember that it has two classical states 0 or 1. Consider two such bits $X_1$ and $X_2$ together represents some information. Here the classical state set $\Sigma_1$ and $\Sigma_2$ corresponds to the bits $X_1$ and $X_2$. 
$$
\Sigma_1 = \{ 0,1 \} \ and \  
\Sigma_2 = \{ 0,1 \}
$$

Then we can get the classical state set of the joint system $(X_1,X_2)$ using the cartesian product of classical state sets of $X_1$ and $X_2$.

$$ \Sigma_1 \times \Sigma_2 = \{(0,0), (0,1), (1,0), (1,1)\} = \{00,01,10,11\}$$

`String:` Here you can notice that instead of using brackets and commas we are just representing each state of the joined system just as a string. This is very common and valid way of defining the classical state of the multiple system. In this case removing brackets and commas doesn't add any ambiguity or confusion. One useful thing to remember is that the formal definition of the string is also defined by the cartesian product of sets with symbols called alphabets(where alphabets is more formal way of saying a set of symbols).

We can generalize this idea for n number of bits. For exmaple classical system $X$ with 10 bits $(X_1,X_2,...,X_{10})$ each with classical state set $\Sigma_1,\Sigma_2,...,\Sigma _{10}$ can be represented by the following cartesian product. Here we directly use the `string` format instead of using `tuple` format to represent each state.(There are total of $2^{10} = 1024$ such possible states of X)

$$\Sigma_1 \times \Sigma_2 \times ... \times \Sigma_{10} = \{0000000000, 0000000001, 0000000010, ..., 1111111111\}$$

Similar to the single systems, we can use the Column vector we can represent the classical state of the two bits in a following way(we have added labels for each entry of the column vector that corresponding classical state of two bit system). Similary we can define the calsssical state vector for any n number of bits also.

$$ |b\rangle = 
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0\end{pmatrix} 
\begin{matrix} \rightarrow 00
\\  \rightarrow 01 \\ \rightarrow 10 \\ \rightarrow 11\end{matrix}$$


### How can we define the probabilistic state of the multiple systems?

We can define the probabilistic state of multiple systems in a same way as the probabilistic state of the single system. Here we will associate some probability value with each classical state of the cartesian product set of the joint system.

As we have seen in previous section, Let $X_1$ and $X_2$ represent two Bits with classical state sets $\Sigma_1$ and $\Sigma_2$. Then the following vector represents a probabilistic state of joint system $(X_1,X_2)$ where the state `00 or (0,0)` has probability 1/2 and the state `11 or (1,1)` has the probabilty 1/2. The states `01` or `10` has the probability 0. (we have added classical state labels for each entry of the probability vector. Each entry corresponds to a probability associated with the labeled classical state).

$$ |p\rangle = 
\begin{pmatrix} \frac{1}{2} \\ 0 \\ 0 \\ \frac{1}{2}\end{pmatrix}
\begin{matrix} \rightarrow 00
\\  \rightarrow 01 \\ \rightarrow 10 \\ \rightarrow 11\end{matrix}
$$

Similar to the single system, The sum of entries of the column vector that corresponds probabilistic state of the multiple system should also be equal to 1 and each entry of the vector should be a possitive real number. Then only we can say that this vector is a probability vector.

In the above example single systems that combined together to form a joint system have specific behaviour. If you see the single systems(bits) individually, then you can see that both the single systems are in same state always. This is an example of correlation between individual systems. This will not be always the case some times the systems will be independent of each other.

## Independence and Correlation

### What do we mean by the independence of single systems?

We have seen that the multiple system is just a combination of single systems. Two systems are said to be independent if learning the classical state of the each of the system doesn't depend on the other one. In other words learning the classical state of the any one of the systems doesn't give any information about the other system.

To understand this first we will the independence between two systems then we can easily generalise that idea for the systems with three or more single systems. Lets assume that the two joint systems $(X_1, X_2)$ are represented by a probabilistic column vector $|\psi\rangle$. Here both $X_1$ and $X_2$ are classical bit with classical state set $\Sigma_1 = \{0,1\}$ and $\Sigma_2 = \{0,1\}$.

Here the current probabilistic state of bits $X_1$ and $X_2$ are represented by the column vectors $|\psi_1\rangle$ and $|\psi_2\rangle$ respectively. We can define these vectors mathematically as follows.

$$
\begin{equation} \tag{1}
\begin{split}
|\psi_1\rangle = \sum_{a \in \Sigma_1} p_a |a\rangle \\

|\psi_2\rangle = \sum_{b \in \Sigma_2} q_b |b\rangle  \\ 

|\psi\rangle = \sum_{(a,b) \in \Sigma_1 \times \Sigma_2} r_{ab} |ab\rangle
\end{split}
\end{equation}
$$

Here $p_a$ and $q_b$ are probability value associated with each classicate state of the bits $X_1$ and $X_2$. The value $r_{ab}$ is the probability associated with each classical state of the joint system $(X_1,X_2)$. 

>Even though already we know this I want to remaind that $|a\rangle$ and $|b\rangle$ are column vectors that represents the classical states of the systems $X_1$ and $X_2$. The column vector $|ab\rangle$ corresponds to the classicate states of the joint system $(X_1, X_2)$.

We say that these two systems $X_1$ and $X_2$ are independent when they are probabilistically independent from each other. Then Correlation between two systems is defined as lack of independence. If two systems are not independent, then they are correlated.

#### What is the probabilistic independence?

Two events are said to be independent if probability outcome of an one event doesn't affect the probability outcome of the other event. 

Suppose $X_1$ and $X_2 are two individual systems. We say that these systems $X_1$ and $X_2$ are probabilistically independent when the probability associated with the system doesn't depend on each other. We can define this formally as follows,

$$ 
\begin{equation} \tag{2}
P((X_1,X_2) = (a, b)) = P(X_1=a)P(X_2=b)
\end{equation}
$$

This equation tells that the probability that the joint system $(X_1,X_2)$ is in a state $(a,b)$ is the multiplication of the probabilities that states of $X_1 = a$ and $X_2 = b$. We can define this for the probability $r_{ab}$ as follows.

$$ r_{ab} = p_a q_b$$

This will be true for each classical state $a \in \Sigma_1$ and $ b \in \Sigma_2$. That means regardless of whatever state the individual systems $X_1$ and $X_2$ are in, The probability associated with the joint systems $(X_1,X_2)$ is always the multiplication of the probability associated with each of the single system. We can define this idea more formally using the tensor product.

### How does the tensor product represents independence?

So to define the independece of the individual systems that make up the multiple systems, we can use the tensor product. If we can write down the classical state of the multiple systems as a tensor product of classical state of the individual systems, then we can say that individual system are independent of each other.

We can take the same definition of probability vectors $|\psi_1\rangle$ and $|\psi_2\rangle$ that corresponds to a individual systems $X_1$ and $X_2$ respectively. The probability vector $|\psi\rangle$ that corresponds to a joint systems $(X_1, X_2)$. Then we can say that $|\psi_1\rangle$ and $|\psi_2\rangle$ independent if and only if the following equation is true.

$$ |\psi\rangle = |\psi_1\rangle \otimes |\psi_2\rangle$$

Here the $|\psi\rangle$ is called the product vector(because it is the product of state vectors of the individual systems). The tensor product is more of a natural way of multiplying a column vector( or row vector) with another column vector(or row vector).(Here remember that the dirac notation `ket` represents the column vector)


> **Notations for tensor product**: The following are the equivalent notation for representing tensor product of two vectors $|a\rangle$ and $|b\rangle$.
> $$|a\rangle \otimes |b\rangle \equiv |a\rangle|b\rangle \equiv |ab\rangle \equiv |a \otimes b\rangle
\equiv |(a,b)\rangle \equiv |a,b\rangle$$
>  Here the most common notations are $|a\rangle \otimes |b\rangle$, $|a\rangle|b\rangle$ and $|ab\rangle$.

The tensor product of two vecotors $|\psi_1\rangle$ and $|\psi_2\rangle$ can be done in a following way. Take each element of first vector and multiply with each element of the second vector.

$$
|\psi\rangle = |\psi_1\rangle \otimes |\psi_2\rangle = 
\begin{pmatrix} a_1 \\ a_2 \\ ... \\ a_n\end{pmatrix} \otimes
\begin{pmatrix}b_1 \\ b_2 \\ ... \\ b_n \end{pmatrix} = 
\begin{pmatrix} a_1b_1 \\ a_1b_2 \\ ... \\a_1b_n \\ a_2b_1 \\ a_2b_2\\ ... \\ a_2b_n \\ ...\\ a_nb_1 \\ ... \\ a_nb_n\end{pmatrix}
$$

> **Bilinearity of tensor product:** Tensor product is bilinear that means it is linear with respect both first and second arugument. The following equations describe this in a better way. Suppose if we have column vectors $|a\rangle$, $|b\rangle$ and $|c\rangle$, then we can define the bilinearity as follows.
>Linear in first argument
>$$(|a\rangle + |b\rangle) \otimes |c\rangle = |a\rangle \otimes |c\rangle + |b\rangle \otimes |c\rangle$$
>$$(k|a\rangle) \otimes |b\rangle = k(|a\rangle \otimes |b\rangle)$$
>Linear in second argument
>$$|a\rangle  \otimes  (|b\rangle + |c\rangle) = |a\rangle \otimes |b\rangle + |a\rangle \otimes |c\rangle$$
>$$|a\rangle \otimes (k|b\rangle) = k(|a\rangle \otimes |b\rangle)$$


Another way to describe the independence is if we can write down the complex number associated with each classical state $|ab\rangle$ of the joint system as the multiplication complex number associated with 

$$ \langle ab|\psi\rangle = \langle a|\psi_1\rangle \langle b|\psi_2\rangle$$

Here note that in the LHS we are multiplying two row vectors(classical state vector) $\langle a|$ and $\langle b|$ using the rules of the tensor product to get a classical state vector of the joint system $(X_1,X_2)$. Then we are multiplying resulting vector $\langle ab|$ with a current state(in `ket` notation) $|\psi\rangle$ of the joint system to get a complex number associated with that state.

Similarly in the RHS also we are multiplying classical state vectors $\langle a|$ and $\langle b|$ with the state vectors $|\psi_1\rangle$ or $|\psi_2\rangle$ respectively to get a complex number associated with respective states.

### Example of Independence using tensor product

Lets take the same example of bits $X_1$ and $X_2$ here also. Suppose we have the probability vector $|\psi\rangle$ that represent the joint system $(X_1,X_2)$. Then in the following derivation we are trying to derive that $|\psi\rangle = |\psi_1\rangle |\psi_2\rangle$


$$
\begin{equation} \tag{Ex-1}

\begin{split}
|\psi\rangle & = \frac{4}{9}|00\rangle + \frac{2}{9}|01\rangle + \frac{2}{9}|10\rangle + \frac{1}{9}|11\rangle 

\\ &\equiv \frac{4}{9}|0\rangle|0\rangle + \frac{2}{9}|0\rangle|1\rangle + \frac{2}{9}|1\rangle|0\rangle + \frac{1}{9}|1\rangle|1\rangle

\\ &= \frac{2}{3}|0\rangle \left( \frac{2}{3} |0\rangle + \frac{1}{3} |1\rangle \right) + \frac{1}{3}|1\rangle \left(\frac{2}{3} |0\rangle + \frac{1}{3} |1\rangle \right) 

\\ &= \left(\frac{2}{3}|0\rangle + \frac{1}{3}|1\rangle \right) \otimes \left(\frac{2}{3} |0\rangle + \frac{1}{3} |1\rangle \right)

\\ &= |\psi_1\rangle \otimes |\psi_2\rangle = |\psi_1\rangle|\psi_2\rangle
\end{split}
\end{equation}
$$

>**Important:** Here learning the classical state of the bit $X_1$ doesn't give any information about the bit $X_2$. This is how we have defined the independence. 
>* Regardless of whatever the classical state the bit $X_1$, the probability associated with the bit $X_2$ is same. The probabilistic state of the $X_2$ is always $\left(\frac{2}{3} |0\rangle + \frac{1}{3} |1\rangle \right)$.


In the above derivation you can see how we can find the probabilities associated with individual systems $X_1$ and $X_2$ in a formal way. we could have factored the term $\frac{4}{9} =\frac{2}{3} \times \frac{2}{3} = \frac{2}{9} \times 2$. But we have done in a specific way to make sure that the sum of probabilities of single system would add upto 1. Note that $\frac{2}{3} +\frac{1}{3} = 1$. (**Note**: Remember that the probability should add upto 1 in any probability vector.)

Also If you multiply the probabilities associated with the classical states $|0\rangle$ of $|\psi_1\rangle$ and $|0\rangle$ of $|\psi_2\rangle$, then you will get the probability associated with the joint classical state $|00\rangle$ as $\frac{2}{3} \times \frac{2}{3} = \frac{4}{9}$. Like this you can cross check each valid combination of individual systems.

If we can write down the probability vector of the joint system as the tensor product of probability vectors associated with each individual systems, then we can find the probability associated with each classical state of the individual system without depending on the other systems.

### Then what does the correlation mean?

We can define the correlation(or dependence) as the lack of independence. If two systems are dependent to each other, then measuring one system will give you some information about the other system.

Lets suppose we have the following probability vector $|\psi\rangle$ that represents some probabilistic state of the joint system $(X_1,X_2)$. We will try to write it as the tensor product of two probability vectors.

$$
\begin{equation} \tag{Ex-2}
\begin{split}
|\psi\rangle & = \equiv \frac{3}{7}|0\rangle|0\rangle + \frac{1}{7}|0\rangle|1\rangle + \frac{2}{7}|1\rangle|0\rangle + \frac{1}{7}|1\rangle|1\rangle

\\ &= |0\rangle \left( \frac{3}{7} |0\rangle + \frac{1}{7}|1\rangle \right) + |1\rangle  \left( \frac{2}{7} |0\rangle +  \frac{1}{7} |1\rangle \right) 
\end{split}
\end{equation}
$$

In the above derivation we can't go any further, that means we can't wirte this probability vector as a tensor product of two individual probability vectors. That means these two bits are correlated.

>If you think about it, then you can see that here learning the calssical state of $X_1$ does give us some information about the classical state of $X_2$. the probability vecotor for $X_2$ is different for two cases where $X_1$ is in the state $|0\rangle$ and in the state $|1\rangle$

Another good example of correlation is the following vector. Here the $|X_1\rangle$ and $|X_2\rangle$ can always be in the same state either $|0\rangle$ or $|1\rangle$.

$$ |\psi\rangle = \frac{1}{2}|00\rangle + \frac{1}{2}|11\rangle$$

Here the probability value $\frac{1}{2}$ has no special importance. It can be any fraction as long as the probability values add upto 1.

### What about the independence of three or more systems?

The idea we have used for two systems can be generalised for three or more systems. Lets assume that we have joint multiple systems $(X_1,X_2,...,X_n)$ with probability vectors $|\psi\rangle$ and individual systems $X_1,X_2,...,X_n$ with probability vectors $|\psi_1\rangle, |\psi_2\rangle, ..., |\psi_n\rangle$. If we can write the probability vector $|\psi\rangle$ as the product of the probability vectors $|\psi_1\rangle, |\psi_2\rangle, ..., |\psi_n\rangle$, then we can say that individual systems are independent. It can be formally defined as follows,

$$
\begin{equation} \tag{3}
|\psi\rangle = |\psi_1\rangle \otimes |\psi_2\rangle \otimes ... \otimes |\psi_n\rangle
\end{equation}
$$

Similar to the two systems case, We can also define a linearity with respect each argument of the three or more systems when all the other arguments are fixed. This is called multilinearity.

If individual systems are indipendent, then we can describe the probability associated with each classical state of joint system in a following way.

$$
\begin{equation} \tag{4}
 \langle a_1 a_2 ... a_n|\psi\rangle = \langle a_1|\psi_1\rangle \langle a_2|\psi_2\rangle...\langle a_n|\psi_n\rangle
 \end{equation}
 $$

 ### How can we calculate the tensor product of three or more vectors?

One way to do this is, we can recursively define the tensor product of n vector. The logic goes like this, to compute the tensor product n vectors, first get the tesnor product of n-1 vectors and multiply it with n'th vector. To compute the tendor product of n-1 vector first get the tesnor product of n-2 vectors and then multiply it with the (n-1)'th vector. This will go on like this until there are just two vectors to multiply. The give below equation is how the first step of this recursive procedure will look like.

$$
\begin{equation} \tag{5}
|\psi\rangle = (|\psi_1\rangle \otimes |\psi_2\rangle \otimes ... \otimes |\psi_{n-1}) \otimes |\psi_n\rangle
\end{equation}
$$


## Measurement of multiple systems

### How can we define the measurement on multiple systems?

If we consider multiple systems together as a single system, then the measurement of multiple systems is similar to the measurement of a single system, the difference is that here we are measuring the classical state of the joint system. The classical states set of the joint system will be represented by cartesian product set. Before measuring the joint systems it will be in some probabilitic state. As soon as we measure it, the system will collapse into some classical state.(we know that the action of measurement itself is an operation applied on the probability vector. We will see more about operations in next section).

$$ |\psi\rangle = \frac{1}{2}|00\rangle + \frac{1}{2}|11\rangle$$

For example if we measure the above vector we will get the result $|00\rangle$ with probability $\frac{1}{2}$ and the result $|11\rangle$ with probability $\frac{1}{2}$. So as soon as we measure it, the state of the system will collapse into one of these possible classical states.

### What if we want to measure just one or subset of the systems(partial measurement)? 

First we will take a two systems as an example, after that we can easily generalise this idea to the case where we measure the subset of the three or more systems. This is because measuring the subset of the multiple systems is similar to measuring just one of the two systems. We can think of subset of systems that we measure as one individual system and all the remaining systems as a second individual system.

Let's take the same example as joint system  $(X_1,X_2)$ that represent two bits. If we only measure the system $X_1$, then the following equation should be true about the probability of $X_1 = a$. Where $X_1$ and $X_2$ are individual systems with classical state sets $\Sigma_1$ and $\Sigma_2$.

$$ \begin{equation}\tag{6}
Pr(X_1=a) = \sum_{b \in \Sigma_2} Pr((X_1,X_2) = (a,b))
\end{equation}
$$

This equation tells that the probablity that the state of the $X_1 = a $ should be equal to the sum of probabilities of the joint system $(X_1,X_2)=(a,b)$ for each $b \in \Sigma_2$. This intutively means the probability of $X_1 = a$ will be true regardless of whatever the classical state the system $X_2$ is in. This particular formula is called the `reduced(or marginal)` probability. In a similar way we can define the case where we just measure the system $X_2$.

### Why does the above equation is true?

The above equation must be true, because if the state of the $X_1$ changes based on whether or not we measure the $X_2$, then it will allow us faster than light communication. For example lets assume that we are measuring the $X_1$ in the Earth and some other person is measuring the $X_2$ from the planet which is 100 light years away from earth which is called E_100.

If someone from planet E_100 want to send information to Earth it will take at least 100 light years in the normal settings. But if the state of the $X_1$ depends on the measurement of the state of the $X_2$, then some one from the Earth can continuously measure the $X_1$. If the person from the Planet E_100 measures the $X_2$, then at that moment the person in the earth will measure different value for $X_1$. This will allow us to send a signal to the earth faster than light. As of now it is not possible based on our understanding about the physics. So the above equation must be true.


### If two systems are correlated, does that mean measurement of one system depends on the other system?

The answer is no. If we just measure $X_1$, then it will give us some information about the state of the $X_2$ when $X_1$ and $X_2$ are correlated and will give no information about the state of $X_2$ when two systems are independent. This has nothing to do with the measurement of the two systems depending on each other. Regardless of whether or not we measure the $X_2$ the measurement of $X_1$ will always give same result and vice versa is also true.

Let assume that two joint systems $(X_1,X_2)$ is in a particular probabilistic state $\phi_1$. The correlation between these two systems just tells us that, if you keep the joint systems in the current state and measure the state of the $X_1$, then we will know some information about the system $X_2$. 

But if you apply some operation on the system $X_1$ individually(In next section we will see that applying operations on individual system of the multiple systems is possible), that won't affect the state of the system $X_2$. The state of the $X_2$ will only change if we apply some operation on that system also. Also after you apply some operation on the system $X_1$, the whole system will change into some new probabilistic state $\phi_2$. This new state $\phi_2$ may or may not be correlated. 


### After measuring the system $X_1$, we might know some information about the $X_2$. How to represent it mathematically?

We said that if we measure the $X_1$ system, then sometimes it will give us some information about the state of the $X_2$. To represent this specific relation between $X_1$ and $X_2$ we will use the following conditional probabiltiy formula.

$$\begin{equation}\tag{7}
Pr(X_2=b | X_1=a) = \frac{Pr((X_1,X_2)=(a,b))}{Pr(X_1=a)}
\end{equation}
$$

The probabilty that $X_2=b$ based on the condition that the measurement that $X_1=a$ is defined by the above conditional probability formula. In the numerator we have the probabilty for the specific case where $(X_1,X_2)=(a,b)$. In the denominator we have the probability of $X_1=a$ and $X_2=c$ for each $c \in \Sigma_2$. When we see the example we will understand that the denominator is for the normalization. Here normalization means, If you sum the above computed probability for each classical state $b \in \Sigma_2$, then we will get the sum 1.

> What if denominator is 0?

The case where $Pr(X_1=a) = 0$ won't be a problem, because in that case we won't check for the probability vector of $X_2$ based on the condition that $X_1=a$. This is due to the reason that the event $X_1=a$ is never going to happen when the probability of that event is 0. 

###  How do we find the updated state vector of the system after the measurement of one or subset of the multiple systems?

In this section we will explore the idea of partial measurement using state vectors and dirac notations. Lets first consider the following probability vector that represents that state of two bits which we have already seen in the `equation-1`.

$$ |\psi\rangle = \sum_{(a,b) \in \Sigma_1 \times \Sigma_2} r_{ab}|ab\rangle$$

If we have measured that the $X_1=a$, then how can we represent the updated probability vector of the system? When two systems are independent then we won't have any information about $X_2$ until we measure it, but when two systems are correlated we will get some information about the system $X_2$ before actually measuring it. To formally represent the change of our knowledge about $X_2$ we need to find two values that correspond to the numerator and denominator of the `equation-7`.

First the numerator corresponds to the probability associated with each state $b \in \Sigma_2$ where we already measured that $X_1=a$. Since we don't know the state of the $X_2$, it will have some probability associated with each classical state $b \in \Sigma_2$. This can be described using the following vector.

$$
\begin{equation} \tag{8}
\phi_a = \sum_{b \in \Sigma_2} r_{ab}|b\rangle
\end{equation}
$$

The entries of the valid probability vector should add upto 1. To make the $|\phi_a\rangle$ probability vector we need to normalise it. To do that we sum over all the probability values of the each entry of the vector $|\phi_a\rangle$ and divide the vector by that sum. the follwoing equation computes that sum.

$$
\begin{equation} \tag{9}
k = \sum_{c \in \Sigma_2}r_{ac}
\end{equation}
$$

Here the notation `c` is used for the sake of using differnet notation. Otherwise this value is equal to the sum of all the $r_{ab}$ values in the vector $|\phi_a\rangle$. Now we can define the new vector that reflects our knowledge about the system $X_2$ after measuring the state of $X_1=a$.

$$
\begin{equation} \tag{10}
|\pi_a\rangle = \frac{|\phi\rangle}{k} = 
\frac{\sum_{b \in \Sigma_2} r_{ab}|b\rangle}
{\sum_{c \in \Sigma_2}r_{ac}}
\end{equation}
$$

Using the above definitions we can say that the new state of the joint system $(X_1,X_2)$ will be the tensor product $|a\rangle \otimes |\pi_a\rangle$. Here the value of $X_1$ is $|a\rangle$ which we got from the measurement and the state of $X_2$ is $|\pi_a\rangle$.

### How can we compute the probability values associated with just first system of the joint systems $(X_1,X_2)$?

We have seen that the reduced or marginal probability in the `equation-6`. How can we represent the reduced or marginal state just one(or proper subset) of the system. To understand this we can drop all the states associated to the $X_2$ in the $|\psi\rangle$(from `equation-1`) and simplify it. Now we will get the marginal state of $X_1$. This can be formally defined as follows,

$$ 
\begin{equation} \tag{11}
\sum_{a \in \Sigma_1} \left(\sum_{b \in \Sigma_2} r_{ab} \right) |a\rangle
\end{equation}
$$

For example take a vector from the `Ex-1`

$$
\begin{split}
|\psi\rangle &= \frac{4}{9}|0\rangle|0\rangle + \frac{2}{9}|0\rangle|1\rangle + \frac{2}{9}|1\rangle|0\rangle + \frac{1}{9}|1\rangle|1\rangle \\

&= |0\rangle \left(   \frac{4}{9}|0\rangle + \frac{2}{9}|1\rangle \right) + |1\rangle \left( \frac{2}{9}|0\rangle + \frac{1}{9}|1\rangle  \right) \\
\end{split}
$$

Now here just drop the states that corresponds to the system $X_2$ and sum only their probability coefficients.(**This may not be the valid mathematical way of doing this but this approach will give the vector that is represented by the** `equation-11`).

$$
\begin{equation} \tag{Ex-3}
   marginal \; state \; of \; X_1 = \frac{6}{9}|0\rangle + \frac{3}{9}|1\rangle
\end{equation}
$$

### Example of partial measurement

Assume that the probabilistic state of the joint system $(X_1,X_2)$ is represented by the following probability vector. $X_1$ is the bit with the classical state set $\Sigma_1$ and $X_2$ is the system that represent four suits of cards in the deck of cards with calssical state set $\Sigma_2$. (Here $X_1$ and $X_2$ are not independent systems).

$$\Sigma_1=\{0,1\} \;\; \Sigma_2=\{C,D,H,S\}$$

$$where \;\; C- Clubs, D-Diamonds, H-Hearts, S-Spades$$

$$
\begin{split}
|\psi\rangle & = 
\equiv \frac{3}{15}|0\rangle|C\rangle + 
\frac{4}{15}|0\rangle|D\rangle + 
\frac{2}{15}|0\rangle|H\rangle  + 
\frac{5}{15}|1\rangle|C\rangle + 
\frac{1}{15}|1\rangle|S\rangle

\\ &= 
|0\rangle \left( \frac{3}{15} |C\rangle + \frac{4}{15}|D\rangle  + \frac{2}{15}|H\rangle \right) + 
|1\rangle  \left( \frac{5}{15} |C\rangle +  \frac{1}{15} |S\rangle \right) 
\end{split}
$$

Based on the `equation-8` and `equation-9` we can get the probability that the $X_1 = 0$ by summing over all the probability values of the system $X_2$ when the state of the $X_1$ is $|0\rangle$. That is

$$Pr(X_1 = 0)  = \frac{3}{15} + \frac{4}{15} + \frac{2}{15} = \frac{9}{15}$$

Lets assume that we measured the state of $X_1$ as $|0\rangle$. Then the probability vector of the $X_2$ can be computed using the `equation-10`. In that case the probability sum in the denominator is what we calculated above and vector in the numerator is the term that is right after the state $|0\rangle$ in the second step of the above derivation after grouping the terms. so the $|\pi_0\rangle$ is written as follows.

$$
\begin{equation} \tag{Ex-4}
|\pi_0| = \frac{
    \left( \frac{3}{15} |C\rangle + \frac{4}{15}|D\rangle  + \frac{2}{15}|H\rangle \right)
}{\frac{9}{15}}
=
\left( \frac{3}{9} |C\rangle + \frac{4}{9}|D\rangle  + \frac{2}{9}|H\rangle \right)
\end{equation}
$$

Similary the probability that the $X_1 = 1$ and the probability vector that represents the state of $X_2$ after measuring $X_1 = 1$ as follows.

$$
Pr(X_1 = 1)  = \frac{5}{15} + \frac{1}{15} = \frac{6}{15}  
$$

$$
\begin{equation} \tag{Ex-4}
|\pi_0| = \frac{
    \left( \frac{5}{15} |C\rangle +  \frac{1}{15} |S\rangle \right)
}{\frac{3}{7}}
=
\left( \frac{5}{6} |C\rangle +  \frac{1}{6} |S\rangle \right)
\end{equation}
$$

**Note: In the above equations I am not simplyfying any of the fraction values**(e.g $
\frac{3}{15} = \frac{1}{5}$), **This is to make it easy for verifying the probability sum.**


### What about partial measurement of independent multiple systems?

In an example `Ex-4` the two systems we discussed are not independent. So when we measured the system $X_1$ it gave us some information about the state of the system $X_2$ before actually measuring the system $X_2$. 

When two systems are independent then measuring one of systems doesn't provide any information about the second system before the actual measurement of the second system.

Lets take a joint system $(X_1,X_2)$ in `Ex-1`. In that example you can see that the probability associated with the system $X_2$ doesn't change after measuring the system $X_1$ and vice versa is also true. This is exactly why we call them independent systems.

## Operations on multiple systems

### Can we still use stochastic matrix?

If we think about the multiple systems combined together as a single system, then the operations on multiple systems can also be defined using stochastic matrix. Here the rows and columns of the stochastic matrix corresponds to the entries of the classical state set of the joint system. Remember that we can get the calssical state set of the joint system using the cartesian product of the classical state sets of the individual systems.

Lets take usual example of two bits joint system $(X_1, X_2)$. The rows and columns of the stochastic matrix for this joint system will corresponds to a cartesian product set $\Sigma_1 \times \Sigma_2$.

### What about the deterministic operation on multiple systems?

Deterministic operation is an operation on multiple system for which the input and output corresponds to one of the classical state of the joint system. There won't be any uncertainty about the output. We will alway get exactly one of the classical states as the output. 

> First We will look into a specific example of controlled NOT operation where if $X_1 = 1$ then flip the bit $X_2$, otherwise do nothing.

The controlled-NOT means, there will be one control bit and if the control bit is 1, then we will apply NOT operation on the other bit. The following stochastic matrix represents this operation. We have seen about the stochastic matrix in the blog about the single system classical information.(Even though the given below matrix represents deterministic operation, we can call it stochastic because it satisfies the conditions for being a stochastic matrix)

$$
\begin{equation}\tag{Ex-5}
\begin{split}

&\Rightarrow
|00\rangle\langle00| + 
|01\rangle\langle01| + 
|10\rangle\langle11| + 
|11\rangle\langle10| \\
&= 
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 
\end{pmatrix}

\end{split}
\end{equation}
$$

The above stochastic matrix represents the controlled NOT operation on the system $(X_1,X_2)$. Here $X_1$ is the control bit. The control bit decides whether or not particular operation should be applied on the target bit and $X_2$ is the target bit on which the actual operation is applied.

In the LHS you can see that we have represented the stochastic matrix using the dirac notations. Each entry in the LHS corresponds to output-input relationship. In each term the first vector(column vector) corresponds to a output and second vector(row vector) corresponds to a input. If you do the normal matrix multiplication, then you will get the matrix on the RHS.

Similar way we can define the case where $X_2$ is controll bit and $X_1$ is the target bit. The following matrix represents this operation.

$$
\begin{equation}\tag{Ex-6}
\begin{split}

&\Rightarrow
|00\rangle\langle00| + 
|11\rangle\langle01| + 
|10\rangle\langle10| + 
|01\rangle\langle11| \\
&= 
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 
\end{pmatrix}

\end{split}
\end{equation}
$$

Another way to think about deterministic operation is by thinking about what each row does to the input vector. If input column vector is $|00\rangle$, then the output should be the same vector. This means if first entry of the input is 1, then first entry of the output also should be 1. The first row of the matrix does exactly the same. Similarly the second row represents the fact that if the input is $|01\rangle$, then the output should be $|11\rangle$. 

### What is a probabilistic operation on multiple systems?

The probabilistic operation is applied on the probability vector and gives another probability vector as an ouput. There will be some uncertainty about the output. To describe this uncertainty about the output, we will associate some probability to each possible output state. Note that the stochastic matrices are mathematical representation of probabilistic operation and deterministic operations can be thought of as special case of probabilistic operation, where we know the output with cetainty. 

> For example if two bits $X_1$ and $X_2$ are not same, then half of the time set the value of $X_1$ to $X_2$ and another half of the time set the value of $X_2$ to $X_1$.

The following stochastic matrix represents this operation.

$$
\begin{equation}\tag{Ex-7}
\begin{split}

&\Rightarrow 
|00\rangle\langle00| + 
\left( 
\frac{1}{2}|00\rangle\langle01| + 
\frac{1}{2}|11\rangle\langle10| 
\right) + 
\left( 
\frac{1}{2}|11\rangle\langle01| + 
\frac{1}{2}|00\rangle\langle10| 
\right) + 
|11\rangle\langle11|
 \\
&= 
\frac{1}{2}
\begin{pmatrix}
1 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 1 & 1
\end{pmatrix} +
\frac{1}{2}
\begin{pmatrix}
1 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & 1 & 0 & 1 
\end{pmatrix} \\
&=
\begin{pmatrix}
1 & \frac{1}{2} & \frac{1}{2} & 0 \\
0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 \\
0 & \frac{1}{2} & \frac{1}{2} & 1 
\end{pmatrix}

\end{split}
\end{equation}
$$
(remember that in the first equation the row vector corresponds to input and the column vector corresponds to output)

In the avove example you can see that we can think of this operation in two ways. One way is in terms of state vectors and dirac notation similar to the example `Ex-6`, another way is in terms of sum of two deterministic operation each associated with some probability.

Similar operations can be defined for any number of systems. We will use dirac notation to explain the following example.

> Consider a octal(base-8) number system where numbers are only 0-7. The operation is whenever some input is given we have to add 1 to that number and give the result again in the octal number system. 

Remember that when we add 7+1=8 will exceed our limit. So we have to use modular arithmetic to find a octal nubmer that is within our limit. In this case the result will be ((7+1) mod 8) = 0. 

$$
\begin{equation}\tag{Ex-7}
\begin{split}

&\Rightarrow 
\sum_{k=0}^{7} |binary \; encoding\; of \;((k+1) \;mod \;8)\rangle
\langle binary \; encoding\; of \; k| \\
&= 
|001\rangle\langle000| +
|010\rangle\langle001| +
|011\rangle\langle010| +
|100\rangle\langle011| +
|101\rangle\langle100| +
|110\rangle\langle101| +
|111\rangle\langle110| +
|000\rangle\langle111| \\
&= 
\begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \\
1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 \\
\end{pmatrix} 
\end{split}
\end{equation}
$$

Here also the dirac notation and the matrix representation works in the same way as we discussed previously.

## Independent Operations

### What if we want to apply operation only on single or proper subset of the multiple systems?

So when there are multiple systems, we have defined the independence of the individual systems that make the multiple systems using the tensor product. In a similar way we can define the independence of the operation on the multiple systems using tensor product. To understand this we have to first understand the tensor product of matrices.

### How can find the tensor product of matrices? 

Lets take an usual example of multiple systems with two bits $X_1$ and $X_2$ with classical state set $\Sigma_1$ and $\Sigma_2$ respectively. We know from previous sections that the operations on individual systems are represented by stochastic matrix. The following definitions of matrices $M_1$ and $M_2$ represent the operations on the individual systems $X_1$ and $X_2$ in a generic way. 


$$
\begin{equation}\tag{12}
M_1 = \sum_{a,b \in \Sigma_1} \alpha_{ab}|a\rangle\langle b| \;\;\;
M_2 = \sum_{c,d \in \Sigma_1} \beta_{cd}|c\rangle\langle d|
\end{equation}
$$

In the above definitions $\langle b|$ and $\langle d|$ are input vectors and $|a\rangle$ and $|c\rangle$ are their corresponding output vectors. We have defined the operation as sum of output-input vector multiplication for each possible input from the the classical state set. 


>**Important:** \
> In the above definitions we are defining the input as row vector such as $\langle b|$ and output as column vector such as $|a\rangle$. This is only for the purpose of computing the matices. In the normal case while applying the operations on the probability vectors, both the input and output are going to be column vector represented by the `ket` notation.

### Why do we need $\alpha_{ab}$ and $\beta_{cd}$?

The $\alpha_{ab}$(similar way we can explain the $\beta_{cd}$) is a real numbers that represent the probability of the input $\langle b|$ giving a particular output $|a\rangle$. For each such input the sum of probabilities should add upto 1. The good example is `Ex-7` where half of the time we set the value $X_1$ to $X_2$ and another half of the time $X_2$ to $X_1$.

Now the operation on the joint system $(X_1,X_2)$ is represented by the following matrix.

$$
\begin{equation}\tag{13}
\begin{split}
M &= M_1 \otimes M_2 \\

&= \sum_{a,b \in \Sigma_1} \sum_{c,d \in \Sigma_2} \alpha_{ab} \beta_{cd} 
|ac\rangle\langle bd| \\

&= \sum_{ac, bd \in \Sigma_1 \times \Sigma_2} \alpha_{ab} \beta_{cd} 
|ac\rangle\langle bd| \\

\end{split}
\end{equation}
$$

Let assume that $M_1$ and $M_2$ are operation applied on the individual systems. The tensor product of these matrices represents the combined operation on the joint system. In the last step of the above derivation we can see that the tensor product describes the output-input relationship for each input $\langle bd|$ of the joint system. We can think about this in a different way as the follows.

$$
\begin{equation}\tag{14}
\langle ac| M_1 \otimes M_2 |bd\rangle = 
\langle a| M_1 |b\rangle 
\langle c| M_2 |d\rangle
\end{equation}
$$

for every choice of $a,b \in \Sigma_1$ and $c,d \in \Sigma_2$

Here note that $(M_1 \otimes M_2)|bd\rangle = |ac\rangle$. So in the LHS the value $\langle ac||ac\rangle $ is going to be some real number which will be equal to the real number that we will get when we evaluate the RHS.

Because of the way we defined the tensor product the following equation is true for any valid operations $M_1$ and $M_2$ on individual systems $X_1$ and $X_2$. Here $|\psi_1\rangle$ and $|\psi_2\rangle$ are probability vectors that corresponds to systems $X_1$ and $X_2$ respectively.

$$
\begin{equation}\tag{15}
(M_1 \otimes M_2) (|\psi_1\rangle \otimes |\psi_2\rangle) = 
(M_1 |\psi_1\rangle) \otimes 
(M_2 |\psi_2\rangle)
\end{equation}
$$

The tensor product of two matrices are defined in the following way.


$$
\begin{equation}\tag{Ex-8}
\begin{split}

&\Rightarrow \begin{pmatrix}
a_{11} & \cdots & a_{1m} \\
\vdots & \ddots & \vdots \\
a_{m1} & \cdots & a_{mm}
\end{pmatrix}
\otimes
\begin{pmatrix}
b_{11} & \cdots & b_{1k} \\
\vdots & \ddots & \vdots \\
b_{k1} & \cdots & b_{kk}
\end{pmatrix} \\ \\

&=
\begin{pmatrix}
a_{11}b_{11} & \cdots & a_{11}b_{1k} & & a_{1m}b_{11} & \cdots & a_{1m}b_{1k}\\

\vdots & \ddots & \vdots & \cdots & \vdots & \ddots & \vdots\\

a_{11}b_{k1} & \cdots & a_{11}b_{kk} & & a_{1m}b_{k1} & \cdots & a_{1m}b_{kk} \\

& \vdots & & \ddots & & \vdots & \\

 a_{m1}b_{11} & \cdots & a_{m1}b_{1k} & & a_{mm}b_{11} & \cdots & a_{mm}b_{1k}\\

\vdots & \ddots & \vdots & \cdots & \vdots & \ddots & \vdots\\

a_{m1}b_{k1} & \cdots & a_{m1}b_{kk} & & a_{mm}b_{k1} & \cdots & a_{mm}b_{kk} \\
\end{pmatrix}

\end{split}
\end{equation}
$$

In a similar way as above we can define the tensor product of three or more matrices. For three or more systems, the equations `equation-16` and `equation-17` are equivalent to the equations in the `equation-14` and `equation-15`.

$$
\begin{equation}\tag{16}
\langle a_1 a_2 \cdots a_n| M_1 \otimes M_2 \otimes \cdots \otimes M_n |b_1 b_2 \cdots b_n\rangle
= \langle a_1| M_1 |b_1\rangle 
  \langle a_2| M_2 |b_2\rangle \cdots 
  \langle a_n| M_n |b_n\rangle
\end{equation}
$$

Suppose there is a joint system $(X_1,X_2,\cdots,X_n)$. the vector $|b_1 b_2 \cdots b_n\rangle$ is a input vector and $\langle a_1 a_2 \cdots a_n|$ is an output vector. In this case the LHS and RHS is going to evaluate to the same real number.

$$
\begin{equation}\tag{17}
(M_1 \otimes 
M_2 \otimes 
\cdots \otimes
M_n)

(|\psi_1\rangle \otimes 
|\psi_2\rangle \otimes 
\cdots \otimes
|\psi_n\rangle) = 

(M_1 |\psi_1\rangle) \otimes 
(M_2 |\psi_2\rangle) \otimes
\cdots \otimes
(M_n |\psi_n\rangle)
\end{equation}
$$

Here the state vectors $|\psi_1\rangle,|\psi_2\rangle, \cdots , |\psi_n\rangle$ and matrix operations $M_1,M_2, \cdots , M_n$ corresponds to the systems $X_1,X_2, \cdots X_n$ respectively.

>Note: \
>The tensor product of matrices is said to be multiplicative because of the follwing equation. 
> $$\begin{equation}\tag{18} (M_1 \otimes M_2 \otimes \cdots \otimes M_k)(N_1 \otimes N_2 \otimes \cdots \otimes N_k) = (M_1 N_1) \otimes (M_2 N_2) \otimes \cdots \otimes (M_k N_k) \end{equation}$$
> Here $M_1,M_2,\cdots,M_k$ and $N_1,N_2,\cdots,N_k$ are any valid matrices as long as matrix multiplication $(M_i N_i)$ makes sense for $1 \leq i \leq k$.

### Examples of Independent operations

Lets take an usual example of two bits $X_1$ and $X_2$ with calssical state sets $\Sigma_1$ and $\Sigma_2$ and state vectors $|\psi_1\rangle$ and $|\psi_2\rangle$. If we apply the operations $M_1$ and $M_2$ on state vectors $|\psi_1\rangle$ and $|\psi_2\rangle$ independently then the joint operation on the joint system's state  $|\psi_1\rangle \otimes |\psi_2\rangle$ is represented by the tensor product $M_1 \otimes M_2$.

> Consider a particualar operation where, If $X_1=1$, then we flip the bit $X_1$ half of the times, otherwise do nothing. We call this operation as $M_1$
>
>Suppose if we apply the operation $M_1$ on $|\psi_1\rangle$ and operation X(or NOT operation) on the $|\psi_2\rangle$ independently, How can we represent the joint operation on the joint system?

The joint operation is represented by the following matrix.
$$
\begin{equation}\tag{Ex-9}
\begin{split}

M_1 \otimes X &= 

\begin{pmatrix}
1 & \frac{1}{2} \\ 
0 & \frac{1}{2} 
\end{pmatrix}
\otimes
\begin{pmatrix}
0 & 1 \\ 
1 & 0 
\end{pmatrix} \\\\

&=
\begin{pmatrix}
0 &  1 & 0 &  \frac{1}{2}  \\ 
1 &  0 & \frac{1}{2}  &  0 \\
0 &  0 & 0 &  \frac{1}{2}  \\
0 &  0 & \frac{1}{2}  &  0
\end{pmatrix} 

\end{split}
\end{equation}
$$

### How can apply some operation only on proper subset of the systems and do nothing on remaining systems?

> Apply X (or NOT) operation on $X_1$ and do nothing for $X_2$

We commonly apply some operation M on one system(or proper subset of systems) and do nothing to the remaining systems. Doing nothing can be represented by the identity matrix. So the above operation can be represented by the following matrix.

$$
\begin{equation}\tag{Ex-10}
\begin{split}

X \otimes I &= 

\begin{pmatrix}
0 & 1 \\ 
1 & 0 
\end{pmatrix} 
\otimes
\begin{pmatrix}
1 & 0 \\ 
0 & 1
\end{pmatrix}\\ \\

&=
\begin{pmatrix}
0 & 0 & 1 & 0 \\ 
0 & 0 & 0 & 1 \\
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0
\end{pmatrix} 

\end{split}
\end{equation}
$$

### Thinking in terms of matrix row and column indeces

> Sometime thinking about operation in terms of pattern in the matrix is useful. Here first row of the matrix tell us that for what input vector we will get an output vector that corresponds to the first entry of the state vector. So the row index corresponds to the index of the output state in the state vector and column index corresponds to the index of the input state of the state vector.
>
> If you consider the first row of the above matrix, the column index 3 tells that the input state will be the state that corresponds to the index 3 of the state vector. The row index 1 tells that output will be the state that correspons to the index 1 of the state vector.
>
> This way of thinking might not be always useful but sometime it will give some intution about the operation that the matrices represent.