# Quantum Information(Multiple Systems)

In the previous blog we have seen about the classical information of the multiple systems. In this blog we will see about the quantum information of the multiple systems. The ideas are going to be very similar to the probabilistic part of the classical information of the multiple systems. When you think of multiple quantum systems as a single system similar to how we thought about multiple calssical systems, then the quantum state of multiple quantum systems can be represented by a unit vector. This unit vector is same as the one which we have used to represent the single quantum system but larger. Remember that unit vector is a vector with Euclidean norm equal to 1.

## How to represent quantum state of multiple systems?

So when we think about the multiple systems together as a single system then quantum state is represented by a unit vector similar to single systems. But now the entries of the unit vector correspond to the `cartesian product` of the classical state sets of individual systems. For example consider two qbits $X_1$ and $X_2$ with the classical state sets $\Sigma_1$ and $\Sigma_2$. Then the classical state set of the joint system $(X_1, X_2)$ will be $\Sigma_1 \times \Sigma_2$.

$$
\begin{equation}\tag{1}
\begin{split}
& \Sigma_1=\{0,1\}  \;\;\; \Sigma_2=\{0,1\} \\
& \Sigma_1 \times \Sigma_2 = \{ 00, 01, 10, 11 \} \\
\end{split}
\end{equation}
$$

The following are the examples of quantum state vectors represented using the dirac notation.

$$
\begin{equation}\tag{Ex-1}
\begin{split}
&|\psi\rangle = 
\frac{2}{\sqrt{8}}|00\rangle +
\frac{1}{\sqrt{8}}|01\rangle +
\sqrt{\frac{2}{8}}|10\rangle +
\frac{1}{\sqrt{8}}|11\rangle \\

&|\psi\rangle = 
\frac{3}{5}|00\rangle +
\frac{4}{5}|11\rangle \\

&|\psi\rangle = 
\frac{1}{\sqrt{2}}|00\rangle +
\frac{1}{\sqrt{2}}|11\rangle \\

&|\psi\rangle = |11\rangle

\end{split}
\end{equation}
$$

All the above vectors are valid quantum state vectors with Euclidean norm equal to 1. Note that we use square root($\sqrt{}$) notation repeatedly to just make examples simpler to verify the Euclidean norm. There are multiple ways we can reprsent the same qunautm state vector using dirac notation. All the given below notation are valid and equivalent. We will use one of them based on the situation.

$$
\begin{equation}\tag{Ex-2}
\begin{split}

|\psi\rangle &= 
\frac{1}{\sqrt{2}}|00\rangle +
\frac{1}{\sqrt{2}}|11\rangle \\

&\equiv 
\frac{1}{\sqrt{2}}|0\rangle|0\rangle +
\frac{1}{\sqrt{2}}|1\rangle|1\rangle \\

&\equiv 
\frac{1}{\sqrt{2}}|0\rangle \otimes |0\rangle +
\frac{1}{\sqrt{2}}|1\rangle \otimes |1\rangle \\

&\equiv 
\frac{1}{\sqrt{2}}|0\rangle_{X_1} |0\rangle_{X_2} +
\frac{1}{\sqrt{2}}|1\rangle_{X_1} \otimes |1\rangle_{X_2} \\

\end{split}
\end{equation}
$$

Sometimes the last equation you see above is used to declar the order of the tensor product clearly. We will face such situations in the measurement of quantum multiple systems topic. Another equivalent way of defining quantum state vector is using a vector notation as given below.

$$ 
\begin{equation}\tag{Ex-2}
|\psi\rangle =
\begin{pmatrix}
\frac{1}{\sqrt{2}} \\ 0 \\ 0 \\ \frac{1}{\sqrt{2}}
\end{pmatrix}
\end{equation}
$$

## How do we represent the independence of of the multiple systems?

Independence of the multiple quantum systems is same as independence of the multiple classical systems. If we can write the quantum state vector of the multiple system as a tensor product of quantum state vectors of the individual systems, then we can say that the individual systems are independent. We call this a product state, so when we can write a quantum state vector in a product state then we can say that each individual systems of the multiple systems are independent.

For example if $|\psi_1\rangle$ is a quantum state vector of the $X_1$ and $|\psi_2\rangle$ is a quantum state vector of the $X_2$, then the tensor product $|\psi_1\rangle \otimes |\psi_2\rangle$ will be the quantum state vector of the joint system $(X_1,X_2)$. Here $|\psi_1\rangle \otimes |\psi_2\rangle$,  $|\psi_1\rangle |\psi_2\rangle$ and $|\psi_1 \otimes \psi_2\rangle$ are the equivalent notations. This idea is same as how we represented classical state of the multiple classical systems. The only difference is here we are using quantum state vectors instead of classical state vectors.

The result we get from the tensor product is still a valid quantum state vector because the result will also have a Euclidean norm equal to 1.

$$
\begin{equation}\tag{2}
\begin{split}
|| |\psi_1\rangle \otimes |\psi_2\rangle ||
&= \sqrt{
    \sum_{a,b \in \Sigma_1 \times \Sigma_2} 
    | \langle ab|\psi_1 \otimes \psi_2 \rangle |^2
}\\

&= \sqrt{
    \sum_{a \in \Sigma_1} 
    | \langle a|\psi_1\rangle |^2
    \sum_{b \in \Sigma_2} 
    | \langle b|\psi_2\rangle |^2
}\\

&= || |\psi_1\rangle || \; || |\psi_2\rangle ||
\end{split}
\end{equation}
$$

So here if $|| |\psi_1\rangle || = 1$ and $|| |\psi_2\rangle || = 1$ then the $|| |\psi_1\rangle \otimes |\psi_2\rangle || = 1$. So if the vectors that represent individual systems are valid then tensor product of vectors is also a valid quantum state. Here note that when we sum over all possible $a,b \in \Sigma_1 \times \Sigma_2$ then for each such pair of a,b this $| \langle ab|\psi_1 \otimes \psi_2 \rangle |$ will give the absolute value of the complex number that is associated with the classical state $|ab\rangle$.

We can generalize this idea easily for three or more systems. Suppose the quantum state vectors $|\psi_1\rangle, |\psi_2\rangle, \cdots ,|\psi_n\rangle$ correspond to the quantum systems $X_1,X_2, \cdots ,X_n$ then the quantum state vector $|\psi\rangle$ represents the quantum state of the joint system $(X_1,X_2,\cdots,X_n)$.

$$ 
\begin{equation}\tag{3}
|\psi\rangle =|\psi_1\rangle \otimes |\psi_2\rangle \otimes \cdots \otimes |\psi_n\rangle
\end{equation}
$$

and Euclidean norm will be as follows.

$$ 
|| |\psi\rangle || =
|| |\psi_1\rangle || \;\; || |\psi_2\rangle || \cdots || |\psi_n\rangle || = 1^n = 1
$$

### What is an entanglement of multiple quantum systems?

We can't always write a quantum state vector of a multiple systems as a product of quantum state vectors of the individual system(as a product state). When such a scenario happens we say that quantum systems are entangled or correlated. Entanglement is important feature of the quantum systems. We will see that It is more complicated concept, when we learn about the more general description of the quantum information using the density matrix formulation. But in the quantum state vector description of the quantum information the entanglement is equivalent to the correlation.

For example if we want to show that the quantum state vectors $|\psi_1\rangle$ and $|psi_2\rangle$ that corresponds to systems $X_1$ and $X_2$ in the example `Ex-2` are independent, then you have to show that $|\psi\rangle$ as a tensor product of two quantum state vectors $|\psi_1\rangle$ and $|\psi_2\rangle$. The following equation formulizes this condition.

$$
\begin{equation}\tag{Ex-3}
|\psi_1\rangle \otimes |\psi_2\rangle = 
\frac{1}{\sqrt{2}}|00\rangle +
\frac{1}{\sqrt{2}}|11\rangle \\
\end{equation}
$$

Since the term $|01\rangle$ is 0 in this equation this means the following equation must be true.

$$
\langle 01|\psi\rangle =
\langle 01|\psi_1 \otimes \psi_2\rangle =
\langle 0|\psi_1\rangle \langle 1|\psi_2\rangle = 0
$$

This means that either $\langle 0|\psi_1\rangle = 0$ or $\langle 1|\psi_2\rangle = 0$ or both are zero. But This will contradict the fact that the following two equations are true.

$$
\langle 00|\psi\rangle =
\langle 00|\psi_1 \otimes \psi_2\rangle =
\langle 0|\psi_1\rangle \langle 0|\psi_2\rangle = 0 \\
and \\
\langle 11|\psi\rangle =
\langle 11|\psi_1 \otimes \psi_2\rangle =
\langle 1|\psi_1\rangle \langle 1|\psi_2\rangle = 0 
$$

So this means that the above vector in `Ex-3` can't be written as product state. So they are entangled or correlated.

#### Example of independent quantum state vector.

Suppose consider the following quantum state vector.

$$
\begin{equation}\tag{Ex-4}
\begin{split}
|\psi\rangle &= 
\frac{4}{5 \sqrt{2}}|00\rangle + 
\frac{4}{5 \sqrt{2}}|01\rangle + 
\frac{3}{5 \sqrt{2}}|10\rangle + 
\frac{3}{5 \sqrt{2}}|11\rangle \\

&=  \frac{4}{5}|0\rangle 
\left( 
    \frac{1}{\sqrt{2}}|0\rangle + 
    \frac{1}{\sqrt{2}}|1\rangle
\right) + 
    \frac{3}{5}|1\rangle 
\left( 
    \frac{1}{\sqrt{2}}|0\rangle + 
    \frac{1}{\sqrt{2}}|1\rangle
\right) \\

&= \left( 
    \frac{4}{5}|0\rangle + 
    \frac{3}{5}|1\rangle
\right)
\otimes
\left( 
    \frac{1}{\sqrt{2}}|0\rangle + 
    \frac{1}{\sqrt{2}}|1\rangle
\right) \\

&= |\psi_1\rangle \otimes |\psi_2\rangle

\end{split}
\end{equation}
$$

Here $|\psi_1\rangle$ and $|\psi_2\rangle$ are independent quantum state vectors.

### Some more commonly used quantum state vectors that are not independent.

The given below are some of the commonly used quantum state vectors that are in the entangled state.

#### Bell States

These are some important two qbit quantum state vectors that are in entangeled states called Bell states named after the physicist Jhon Stewart Bell. For the same reason as example `Ex-3`, Bell states are entangled states.

$$
\begin{equation}\tag{Ex-5}
\begin{split}
|\phi^+\rangle &= 
\frac{1}{\sqrt{2}}|00\rangle + 
\frac{1}{\sqrt{2}}|11\rangle \\

|\phi^-\rangle &= 
\frac{1}{\sqrt{2}}|00\rangle -
\frac{1}{\sqrt{2}}|11\rangle \\

|\psi^+\rangle &= 
\frac{1}{\sqrt{2}}|01\rangle + 
\frac{1}{\sqrt{2}}|10\rangle \\

|\psi^-\rangle &= 
\frac{1}{\sqrt{2}}|01\rangle -
\frac{1}{\sqrt{2}}|10\rangle \\

\end{split}
\end{equation}
$$

Together these four vectors are called `Bell basis`. Similar to the `standard basis vectors` we can represent any vector of dimension 2 as a linear combination of Bell basis vectors. For example see the given below equation.

$$|11\rangle = 
\frac{1}{\sqrt{2}}|\phi^+\rangle -
\frac{1}{\sqrt{2}}|\phi^-\rangle
$$

#### GHZ and W states

The GHZ state is a vector that represents a three qbit state $(X_1,X_2,X_3)$. It is named in honor of Daniel Greenberger, Michael Horne, and Anton Zeilinger, who first studied some of its properties.

$$
\begin{equation}\tag{Ex-6}
|GHZ\rangle = 
\frac{1}{\sqrt{2}}|000\rangle +
\frac{1}{\sqrt{2}}|111\rangle 
\end{equation}
$$

The following is the so called W state:

$$
\begin{equation}\tag{Ex-7}
|GHZ\rangle = 
\frac{1}{\sqrt{3}}|001\rangle +
\frac{1}{\sqrt{3}}|010\rangle +
\frac{1}{\sqrt{3}}|100\rangle 
\end{equation}
$$

Both these states are entangled state which we will further explore on the partial measurement section.

#### Addition examples of multiple quantum systems

So far we have seen quantum multiple systems that is made up of same kind of individual systems. It is possible to have different kind of individual systems in the multiple systems. 

Suppose consider a system $X_1$ which is qbit and systems $X_2$ and $X_3$ which represents the four suits of the standard deck of the cards. Here classical state set of the qbit is $\Sigma_1$ and the classical state set of $X_2$ and $X_3$ is $\Sigma_2$.

$$\Sigma_2 = {C, D, H, S}$$
where C - Clubs, D- Diamonds, H-Hearts, S-Spades.

$$
|\psi\rangle = 
\frac{1}{2}|0\rangle |D\rangle |H\rangle +
\frac{1}{2}|0\rangle |D\rangle |S\rangle +
\frac{1}{\sqrt{2}}|1\rangle |C\rangle |H\rangle
$$

Consider a multiple systems $(X_1,X_2,X_3)$, where systems $X_1$, $X_2$ and $X_3$ have classical state set $\Sigma = \{0,1,2\}$. We call this system with three classical states as `trits` just like `bits`. In quantum world it is `qtrits`.

$$
|\psi\rangle = 
\frac{1}{\sqrt{3}}|0\rangle |1\rangle |1\rangle +
\frac{1}{\sqrt{3}}|0\rangle |2\rangle |0\rangle +
\frac{1}{\sqrt{3}}|1\rangle |0\rangle |2\rangle
$$

Generally a system with the classical state $\Sigma = \{0,1,2,...,d-1\}$ is called `qdits` for arbitrary value of d.


## What is the measurement of quantum multiple systems?