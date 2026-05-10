# Quantum Information(Multiple Systems)

In the previous blog we have learnt about the classical information of multiple systems. In this blog we will learn about the quantum information of multiple systems. The ideas are going to be the same as we discussed in the probabilistic part of the classical multiple systems. When you think of multiple quantum systems as a single system similar to how we thought about multiple calssical systems, then the quantum state of joint quantum system can be represented by a unit vector. This unit vector is same as the one which we have used to represent a single quantum system but larger. Remember that a unit vector is a vector with Euclidean norm equal to 1.

## How to represent quantum state of multiple systems?

So If we think about multiple systems together as a single system, then the quantum state will be represented by a unit vector that is very similar to the quantum single system. But now the entries of the unit vector correspond to the `cartesian product` of the classical state sets of individual systems. For example consider two qubits $X_1$ and $X_2$ with the classical state sets $\Sigma_1$ and $\Sigma_2$. Then the classical state set of the joint system $(X_1, X_2)$ will be $\Sigma_1 \times \Sigma_2$.

```math
\begin{equation}\tag{1}
\begin{split}
& \Sigma_1=\{0,1\}  \;\;\; \Sigma_2=\{0,1\} \\
& \Sigma_1 \times \Sigma_2 = \{ 00, 01, 10, 11 \} \\
\end{split}
\end{equation}
```

The given below examples are quantum state vectors represented using the dirac notation.

```math
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
```

All of the above vectors are valid quantum state vectors with Euclidean norm equal to 1. Note that we use the square root($\sqrt{}$) notation explicitly to make the process of verifying the Euclidean norm simpler. There are multiple ways that we could use to reprsent the same qunautm state vector using dirac notation. All the given below notation are valid and equivalent. We will use one of these notations based on our need.

```math
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
```

Sometimes the last equation you see above is used to declar the order of the tensor product clearly. We will face such situations in the measurement of quantum multiple systems topic. Another equivalent way of defining quantum state vector is using a vector notation as given below.

```math
\begin{equation}\tag{Ex-2}
\begin{split}
|\psi\rangle =
\begin{pmatrix}
\frac{1}{\sqrt{2}} \\ 0 \\ 0 \\ \frac{1}{\sqrt{2}}
\end{pmatrix}
\end{split}
\end{equation}
```

## How do we represent the independence of the quantum multiple systems or joint sytem?

Independence of the joint quantum system is same as the independence of the joint classical system. If we can write the quantum state vector of the joint system as a tensor product of quantum state vectors of the individual systems, then we will say that those individual systems are independent of each other. This is called a product state.

For example if $|\psi_1\rangle$ is a quantum state vector of the $X_1$ and $|\psi_2\rangle$ is a quantum state vector of the $X_2$, then the tensor product $|\psi_1\rangle \otimes |\psi_2\rangle$ will be the quantum state vector of the joint system $(X_1,X_2)$. Here $|\psi_1\rangle \otimes |\psi_2\rangle$,  $|\psi_1\rangle |\psi_2\rangle$ and $|\psi_1 \otimes \psi_2\rangle$ are equivalent notations. The idea is same as the classical state of the joint classical system. The only difference here is that we are using a quantum state vector instead of a classical state vector.

The result we get from the tensor product is still a valid quantum state vector because the result will also have a Euclidean norm equal to 1.

```math
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
```

So here if $|| |\psi_1\rangle || = 1$ and $|| |\psi_2\rangle || = 1$ then the $|| |\psi_1\rangle \otimes |\psi_2\rangle || = 1$. So if vectors that represent individual systems are valid qauntum state vectors then tensor product of vectors is also going to be a valid quantum state vector. Here we are summing over the probability value for each possible $a,b \in \Sigma_1 \times \Sigma_2$. Remembering that for each such pair of a,b this $| \langle ab|\psi_1 \otimes \psi_2 \rangle |$ will give the absolute value of the complex number that is associated with the classical state $|ab\rangle$.

We could generalize this idea easily for three or more systems. Suppose quantum state vectors $|\psi_1\rangle, |\psi_2\rangle, \cdots ,|\psi_n\rangle$ correspond to quantum systems $X_1,X_2, \cdots ,X_n$ respectively, then the quantum state vector $|\psi\rangle$ will represent the quantum state of the joint system $(X_1,X_2,\cdots,X_n)$.

```math
\begin{equation}\tag{3}
\begin{split}
|\psi\rangle =|\psi_1\rangle \otimes |\psi_2\rangle \otimes \cdots \otimes |\psi_n\rangle
\end{split}
\end{equation}
```

and Euclidean norm will be as follows.

```math
|| |\psi\rangle || =
|| |\psi_1\rangle || \;\; || |\psi_2\rangle || \cdots || |\psi_n\rangle || = 1^n = 1
```

### What is an entanglement of the join quantum system?

We can't always write a quantum state vector of multiple systems as a product of quantum state vectors of the individual systems(as a product state). When such a scenario happens we would say that quantum systems are entangled or correlated. Entanglement is important feature of quantum systems. We will see that it is a more complicated concept when we learn about the more general description of the quantum information using the density matrix formulation. But in the quantum state vector description of the quantum information, the entanglement is equivalent to the correlation(specifically non classical correlation).

> ***Note:*** Alternatively quantum entanglement can be defined as the non-classical correlation. So the classical correlation and quantum correlation are not the same. The quantum entanglement has its own properties which we couldn't find in the classical probabilistic systems. The quantum system differs in a way that if you apply some operation to one of the entangled systems, then the probability outcome of the other system(that is in entanglement) will also change as long as the operation doesn't destroy the entanglement itself. We will discuss about this further in the end of this blog and in future blogs. 

For example if we want to show that the quantum state vectors $|\psi_1\rangle$ and $|psi_2\rangle$ that corresponds to systems $X_1$ and $X_2$ in the example `Ex-2` are independent, then you have to show that $|\psi\rangle$ as a tensor product of two quantum state vectors $|\psi_1\rangle$ and $|\psi_2\rangle$. The following equation formalizes this condition.

```math
\begin{equation}\tag{Ex-3}
\begin{split}
|\psi_1\rangle \otimes |\psi_2\rangle = 
\frac{1}{\sqrt{2}}|00\rangle +
\frac{1}{\sqrt{2}}|11\rangle \\
\end{split}
\end{equation}
```

The term $|01\rangle$ is 0 in this equation. That means the following equation must be true.

```math
\langle 01|\psi\rangle =
\langle 01|\psi_1 \otimes \psi_2\rangle =
\langle 0|\psi_1\rangle \langle 1|\psi_2\rangle = 0
```

This means that either $\langle 0|\psi_1\rangle = 0$ or $\langle 1|\psi_2\rangle = 0$ or both are zero. But This will contradict the fact that the following two equations are true.

```math
\langle 00|\psi\rangle =
\langle 00|\psi_1 \otimes \psi_2\rangle =
\langle 0|\psi_1\rangle \langle 0|\psi_2\rangle = \frac{1}{2} \\
and \\
\langle 11|\psi\rangle =
\langle 11|\psi_1 \otimes \psi_2\rangle =
\langle 1|\psi_1\rangle \langle 1|\psi_2\rangle = \frac{1}{2}
```

If $\langle 0|\psi_1\rangle = 0$, then it will contradict the first equation. If $\langle 1|\psi_2\rangle = 0$, then it will contradict the second equation. So this means that the above vector in `Ex-3` can't be written as product state. So they are entangled or correlated.

#### Examples of independent quantum state vectors.

Suppose consider the following quantum state vector.

```math
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
```

Here $|\psi_1\rangle$ and $|\psi_2\rangle$ are independent quantum state vectors.

### Some more commonly used quantum state vectors that are correlated or entangled.

The given below are some of the commonly used quantum state vectors that are in the entangled state.

#### Bell States

Bell states are two qubit quantum state vectors that are in the entangeled states named after the physicist Jhon Stewart Bell. For the same reason as the example `Ex-3`, Bell states are entangled states.

```math
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
```

These four vectors are called `Bell basis vectors`. Similar to the `standard basis vectors` we could represent any vector of dimension 2 as a linear combination of these vectors. For example see the given below equation.

```math
|11\rangle = 
\frac{1}{\sqrt{2}}|\phi^+\rangle -
\frac{1}{\sqrt{2}}|\phi^-\rangle
```

#### GHZ and W states

The GHZ state is a vector that represents a three qubit state $(X_1,X_2,X_3)$. It is named in honor of Daniel Greenberger, Michael Horne, and Anton Zeilinger, who first studied some of its properties.

```math
\begin{equation}\tag{Ex-6}
\begin{split}
|GHZ\rangle = 
\frac{1}{\sqrt{2}}|000\rangle +
\frac{1}{\sqrt{2}}|111\rangle 
\end{split}
\end{equation}
```

The following is the so called W state:

```math
\begin{equation}\tag{Ex-7}
\begin{split}
|GHZ\rangle = 
\frac{1}{\sqrt{3}}|001\rangle +
\frac{1}{\sqrt{3}}|010\rangle +
\frac{1}{\sqrt{3}}|100\rangle 
\end{split}
\end{equation}
```

Both these states are entangled state which we will further explore on the partial measurement section.

#### Additional examples of quantum multiple systems

So far we have seen quantum multiple systems that are made up of same kind of individual systems. It is possible to have different kind of individual systems in the joint system. 

Suppose consider the system $X_1$ which is a qubit and systems $X_2$ and $X_3$ which will represent the four suits of the standard deck of the cards. Here classical state set of the qubit is $\Sigma_1$ and the classical state set of $X_2$ and $X_3$ is $\Sigma_2$.

```math
\Sigma_2 = {C, D, H, S}
```
where C - Clubs, D- Diamonds, H-Hearts, S-Spades.

```math
|\psi\rangle = 
\frac{1}{2}|0\rangle |D\rangle |H\rangle +
\frac{1}{2}|0\rangle |D\rangle |S\rangle +
\frac{1}{\sqrt{2}}|1\rangle |C\rangle |H\rangle
```

Next consider the joint system $(X_1,X_2,X_3)$, where systems $X_1$, $X_2$ and $X_3$ are having the classical state set $\Sigma = \{0,1,2\}$. We call this system with three classical states as `trits` just like `bits`. In quantum world it is `qtrits`.

```math
|\psi\rangle = 
\frac{1}{\sqrt{3}}|0\rangle |1\rangle |1\rangle +
\frac{1}{\sqrt{3}}|0\rangle |2\rangle |0\rangle +
\frac{1}{\sqrt{3}}|1\rangle |0\rangle |2\rangle
```

Generally a system with the classical state $\Sigma = \{0,1,2,...,d-1\}$ is called `qdits` for arbitrary value of d.


## What is the measurement of quantum multiple systems or the joint quantum system?

Standard basis measurement of quantum multiple systems is same as measuring a single quantum system. Suppose if particular quantum system is represented by a quantum state vector $|\psi\rangle$ and classical state set $\Sigma$, then the standard basis measurement for each classical state $a \in \Sigma$ is obtained with the probability equal to $| \langle a|\psi\rangle |^2$.

Suppose assume that the quantum systems $X_1,X_2,...,X_n$ are having the classical state set $\Sigma_1,\Sigma_2,...,\Sigma_n$ respectively. If the joint system $(X_1,X_2,...,X_n)$ is represented by a quantum state vector $|\psi\rangle$ and classical state set $\Sigma = \Sigma_1 \times \Sigma_2 \times \cdots \times \Sigma_n$, then the standard basis measurement for each classical state $(a_1,a_2,\cdots,a_n) \in \Sigma$ will be obtained with the probability equal to $|\langle a_1,a_2,\cdots,a_n|\psi\rangle|^2$

For example, suppose systems $X_1$ and $X_2$ are jointly in the state $|\psi\rangle$.

```math
|\psi\rangle = \frac{3}{5} |00\rangle - i\frac{4}{5} |11\rangle
```

If we measure the quantum system that is in the above state, then the systems $(X_1,X_2)$ will be in the state $(0,0)$ with the probability $\frac{9}{25}$ and in the state $(1,1)$ with the probability $\frac{16}{25}$.


### How do we express the partial measurement of quantum multiple systems?

We could define the partial measurement of multiple quantum systems similar to classical multiple systems. Lets take an example of two qubits $X_1$ and $X_2$ with the classical state set $\Sigma_1$ and $\Sigma_2$ respectively. The joint system $(X_1,X_2)$ will be represented by a quantum state vector $|\psi\rangle$ using the Dirac notation.

```math
\begin{equation}\tag{4}
\begin{split}
|\psi\rangle = \sum_{a,b \in \Sigma_1 \times \Sigma_2} 
\alpha_{ab} |ab\rangle
\end{split}
\end{equation}
```

where $\{\alpha_{ab}: (a,b) \in \Sigma_1 \times \Sigma_2 \}$ is collection of complex numbers satisfying the condition that the sum of absolute value of those complex numbers should be equal to 1(Remember that this condition is equivalent to saying that the Euclidean norm is 1).

```math
\begin{equation}\tag{5}
\begin{split}
\sum_{a,b \in \Sigma_1 \times \Sigma_2} |\alpha_{ab}|^2 = 1
\end{split}
\end{equation}
```

As we already know that if both $X_1$ and $X_2$ are measured, then the probability that we will get the state (a,b) as outcome could be calculated by multiplying the classical state(`bra` notation) $\langle ab|$ and state vector(`ket` notation) $|\psi\rangle$.

```math
\begin{equation}\tag{6}
\begin{split}
Pr((X_1,X_2)=(a,b))=|\langle ab|\psi\rangle|^2 = |\alpha_{ab}|^2
\end{split}
\end{equation}
```

Suppose if we are only measuring the system $X_1$, then the probability outcome of `a` is computed by the following summation. This is the marginal(or reduced) probability of a joint system.

```math
\begin{equation}\tag{7}
\begin{split}
Pr(X_1=a) = \sum_{b \in \Sigma_2} |\alpha_{ab}|^2
\end{split}
\end{equation}
```

After measuring the quantum system $X_1$, it will collapse into one of the possible classical states $|a\rangle \in \Sigma_1$. If individual systems are not independent, then we know that the measurement of one(or proper subset) of the systems will change our knowledge about the other(or remaining) systems. So the quantum state vector of a joint system should reflect this change. This idea can be represented by conditional probability similar to the probabilistic settings.

Now we define the $|\psi\rangle$ in the `equation-4` in a slightly different format, so that we could use that definition to understand the conditional probability.


```math
\begin{equation}\tag{8}
\begin{split}
|\psi\rangle &= \sum_{a \in \Sigma_1} |a\rangle \otimes |\phi_a\rangle \\

|\phi_a\rangle &=\sum_{b \in \Sigma_2} \alpha_{ab} |b\rangle
\end{split}
\end{equation}
```


Then the probability that $X_1=a$ that is defined in the `equation-7` can be equivalently defined using the Euclidean norm of the quantum state vector $|\phi_{ab}\rangle$ for any $a \in \Sigma_1$.

```math
Pr(X_1=a) = || |\phi_a\rangle ||^2
```

Now suppose that we have measured $X_1=a$, then the state of the system $X_2$ will be represented by the following vector.

```math
\begin{equation}\tag{8}
\begin{split}
|a\rangle \otimes 
\frac{|\phi_a\rangle}{|| |\phi_a\rangle||}
\end{split}
\end{equation}
```

Here the resulting vector $|a\rangle \otimes |\phi_a\rangle$ will represent the quantum state of the system $X_2$ on condition that we have measured the state of the system $X_1 = a$ for any $a \in \Sigma_1$. The denominator term $|| |\phi_a\rangle ||$ is to make the Euclidean norm of the resulting vector to be equal to 1(This process is called normalization). This will make the resulting vecor a valid quantum state vector. Remember that in the probablistic setting we divided the vector by the sum of probabilities of that vector to do the normalization.

### Examples of partial measurement

Lets take an usual example of a joint system with two qubits $(X_1,X_2)$ which is represented by the following quantum state vector $|\psi\rangle$.

```math
\begin{equation}\tag{Ex-8}
\begin{split}
|\psi\rangle &= 
\frac{1}{\sqrt{2}}|00\rangle -
i\frac{1}{\sqrt{6}}|01\rangle +
\frac{1}{\sqrt{6}}|10\rangle +
i\frac{1}{\sqrt{6}}|11\rangle \\

&=|0\rangle \otimes \left(
\frac{1}{\sqrt{2}}|0\rangle -
i\frac{1}{\sqrt{6}}|1\rangle
\right) +
|1\rangle \left(
\frac{1}{\sqrt{6}}|0\rangle +
i\frac{1}{\sqrt{6}}|1\rangle
\right) \\

\end{split}
\end{equation}
```

The probability of an outcome $X_1 = 0$ can defined by the following Euclidean norm,

```math
Pr(X_1=0) = 
\left|\left| \frac{1}{\sqrt{2}}|0\rangle -
i\frac{1}{\sqrt{6}}|1\rangle \right|\right|^2 
= \frac{1}{2} + \frac{1}{6} 
= \frac{2}{3}
```

> **Note**: \
>Here note that the Euclidean norm of the vector is the square root of the sum of square of the the absolute value of each entry of the vector. To cancel out this square root we have to raise to the power 2 in the above equation. Here each entry of the vector is the complex number. Remember that the absolute value of the complex number is calculated using the formula $|a+bi| = \sqrt{a^2 + b^2}$

After measuring the $X_1=0$, the state of the whole system $|\psi\rangle$ collapses into a following vector.

```math
|0\rangle \otimes \left(
\frac{
\frac{1}{\sqrt{2}}|0\rangle -
i\frac{1}{\sqrt{6}}|1\rangle}
{\sqrt{\frac{2}{3}}}
\right)

=|0\rangle \otimes \left(
\frac{\sqrt{3}}{2}|0\rangle -
i\frac{1}{2}|1\rangle
\right)
```

If you try to verify the Euclidean norm of the above vector, then you will get the value $\frac{3}{4} +\frac{1}{4} = 1$. This is a useful check for the correctness of our calculation. This ensures that the resulting vector is a valid quantum state vector.

The probability of an outcome $X_1=1$ will be as follows,

```math
Pr(X_1 = 1) = 
\left|\left| \frac{1}{\sqrt{6}}|0\rangle +
i\frac{1}{\sqrt{6}}|1\rangle \right|\right|^2 
= \frac{1}{6} + \frac{1}{6} 
= \frac{1}{3}
```

Here also the sum of $Pr(X_1=0) +Pr(X_1=1) = 1$ is again a useful check.
As we have done previously, as soon as we get the measurement outcome $X_1 = 1$, the state of the whole system will collapse into the measured outcome. When $X_1 = 1$, the state of the system $X_2$ will be defined as follows.

```math
|1\rangle \otimes \left(
\frac{
\frac{1}{\sqrt{6}}|0\rangle +
i\frac{1}{\sqrt{6}}|1\rangle}
{\sqrt{\frac{1}{3}}}
\right)

=|0\rangle \otimes \left(
\frac{1}{\sqrt{2}}|0\rangle +
i\frac{1}{\sqrt{2}}|1\rangle
\right)
```

In a similar way we could define the case where only the system $X_2$ is measured and the $X_1$ is not measured.

### What about reduced quantum state of any one system?

This example shows the limitation of the simplified definition of the quantum information that we have been learning so far. In the probabilistic settings we have defined the reduced(or marginal) state of just one of the two systems(or the proper subset of the three or more systems). But the simplified definition of the quantum information using quantum state vectors doesn't give us a way to define the same for the quantum settings.

Suppose the probabilistic state of the two systems $(X_1,X_2)$ is represented by the following probability vector.

```math
|\phi\rangle = \sum_{a,b \in \Sigma_1 \times \Sigma_2}
r_{ab}|ab\rangle
```

Then the reduced or marginal state of $X_1$ is

```math
\sum_{a,b \in \Sigma_1 \times \Sigma_2} 
r_{ab}|a\rangle
```

But if we have a quantum state of the two systems $X_1,X_2$ is represented by the following quantum state vector.

```math
|\psi\rangle = \sum_{a,b \in \Sigma_1 \times \Sigma_2}
\alpha_{ab}|ab\rangle
```

Then the following equation won't make any sense

```math
\sum_{a,b \in \Sigma_1 \times \Sigma_2} 
\alpha_{ab}|a\rangle
```

The above vector doesn't always make sense because the resulting vecot won't always be a valid quantum state vector. The problem with the above equation is that in the probabilistic settings we have defined the probability of $X_1$ as $r_{ab}$ for each classical state $a \in \Sigma_1$ using the following sum formula,

```math
r_a = \sum_{b \in \Sigma_2} r_{ab}
```

If we try to construct a similar formula for the quantum state, then we will get something like below.

```math
\alpha_a = \sum_{b \in \Sigma_2} \alpha_{ab}
```

The above formula won't always give us a valid quantum state vector due to two reasons, First one is that $\alpha_{ab}$ is a complex number and the second is that we have defined the probability outcome of a quantum state vector using absolute values of those complex numbers. So directly adding up the complex numbers won't always give the correct probability for the state $X_1 = a$ for any $a \in \Sigma_1$. You can check this out with the `Ex-8`.

> **Note**: sum of absolute values squared of complex numbers is not equal to the absolute values square of the sum of complex numbers. For example suppose if $c_1$ and $c_2$ are two complex numbers, then $|c_1|^2 + |c_2|^2 \neq |c_1 + c_2|^2$. So we can't simply add the terms that contains $|a\rangle$ to get the complex number that corresponds to the state $|a\rangle$ of the system $X_1$, that will give us a wrong result.

The another way we may try is the following.

```math
\alpha_a = \sum_{b \in \Sigma_2} |\alpha_{ab}|^2
```

We may try adding up absolute values of $\alpha_{ab}$. In fact this will give correct probability values for each state $a \in \Sigma_1$. But when we calculate absolute values we may loose some information about the system that was represented by the complex numbers(because of calculating absolute values). We will see that the more general description of quantum information will solve these kind of problems.

### Partial measurement of three or more systems

Measuring the proper subset of three or more systems is very similar to measuring just one of the two systems. In this case we will consider the subset of systems that are being measured as a single combined system and all the reamaing systems as the second system.

Assume that we have five systems $(X_1,X_2,X_3,X_4,X_5)$ together representing some information. The first two systems $X_1$ and $X_2$ are having a classical state set $\Sigma_1$ and all the remaining systems are having a classical state set $\Sigma_2$. The quantum state of the joint system is represented by the state vector $|\psi\rangle$.

```math
\begin{equation}\tag{Ex-9}
\begin{split}
& \Sigma_1 = \{0,1\} \\
& \Sigma_2 = \{C, D, H, S\} \\
& where \; C-Clubs \; D-Diamonds \; H-Hearts \; S-Spades \\\\

&|\psi\rangle = 
\frac{1}{\sqrt{5}}|0\rangle |1\rangle |H\rangle |D\rangle |S\rangle +
\frac{1}{\sqrt{5}}|1\rangle  |1\rangle |C\rangle |D\rangle |C\rangle +
\frac{1}{\sqrt{5}}|0\rangle |1\rangle |H\rangle |H\rangle |D\rangle +
\frac{1}{\sqrt{5}}|1\rangle |0\rangle |D\rangle |D\rangle |S\rangle +
\frac{1}{\sqrt{5}}|1\rangle |0\rangle |C\rangle |D\rangle |S\rangle
\end{split}
\end{equation}
```

So now assume that we are going to measure the first and third system in the joint systems $(X_1,X_2,X_3,X_4,X_5)$. So we will consider systems $X_1$ and $X_3$ together as the first system and all the remaining systems as the second system. We are going to group the similar states of the first system as we have done in the classical systems case. But since the system $X_2$ which is part of the second system but it is in the middle of $X_1$ and $X_3$. So we need a way of reordering these systems but still keep track of the initial order of them. For that purpose only we have labeled each vector with labels $1,2,3,4,5$ for the systems $(X_1,X_2,X_3,X_4,X_5)$ respectively. We will see soon that why we are doing this. So the equivalent vector for $|\psi\rangle$ with labels is as follows.

```math
|\psi\rangle = 
\frac{1}{\sqrt{5}}|0\rangle_1 |1\rangle_2 |H\rangle_3 |D\rangle_4 |S\rangle_5 +
\frac{1}{\sqrt{5}}|1\rangle_1 |1\rangle_2 |C\rangle_3 |D\rangle_4 |C\rangle_5 +
\frac{1}{\sqrt{5}}|0\rangle_1 |1\rangle_2 |H\rangle_3 |H\rangle_4 |D\rangle_5 +
\frac{1}{\sqrt{5}}|1\rangle_1 |0\rangle_2 |D\rangle_3 |D\rangle_4 |S\rangle_5 +
\frac{1}{\sqrt{5}}|1\rangle_1 |0\rangle_2 |C\rangle_3 |D\rangle_4 |S\rangle_5
```

So now we will group them into two groups based on our measurement.

```math
\begin{split}

|\psi\rangle &= 
\frac{1}{\sqrt{5}}|0\rangle_1 |H\rangle_3 |1\rangle_2 |D\rangle_4 |S\rangle_5 +
\frac{1}{\sqrt{5}}|0\rangle_1 |H\rangle_3 |1\rangle_2 |H\rangle_4 |D\rangle_5 +
\frac{1}{\sqrt{5}}|1\rangle_1 |C\rangle_3 |1\rangle_2 |D\rangle_4 |C\rangle_5 +
\frac{1}{\sqrt{5}}|1\rangle_1 |C\rangle_3 |0\rangle_2 |D\rangle_4 |S\rangle_5 +
\frac{1}{\sqrt{5}}|1\rangle_1 |D\rangle_3 |0\rangle_2 |D\rangle_4 |S\rangle_5 \\

&= |0\rangle_1 |H\rangle_3 

\left(
    \frac{1}{\sqrt{5}} |1\rangle_2 |D\rangle_4 |S\rangle_5 +
    \frac{1}{\sqrt{5}}|1\rangle_2 |H\rangle_4 |D\rangle_5
\right) + 

|1\rangle_1 |C\rangle_3
\left(
\frac{1}{\sqrt{5}} |1\rangle_2 |D\rangle_4 |C\rangle_5 +
\frac{1}{\sqrt{5}} |0\rangle_2 |D\rangle_4 |S\rangle_5 
\right) +

|1\rangle_1 |D\rangle_3 \left(
\frac{1}{\sqrt{5}}|0\rangle_2 |D\rangle_4 |S\rangle_5
\right)

\end{split}
```

Now we will just take one part of the system and compute the probability outcome of the systems($X_1$ and $X_3$) and state vector for $(X_1,X_2,X_3,X_4,X_5)$ after the measurement. Then you can easily do the similar computation for the other two parts of the above equation.

The probability that we will obtain the result $X_1 = 0$ and $X_3 = H$ is as follows.

```math
\left|\left| 
    \left(
    \frac{1}{\sqrt{5}} |1\rangle_2 |D\rangle_4 |S\rangle_5 +
    \frac{1}{\sqrt{5}}|1\rangle_2 |H\rangle_4 |D\rangle_5
\right) \right|\right|^2 
= \frac{1}{5} + \frac{1}{5} = \frac{2}{5}
```

The state of the systems $(X_1,X_2,X_3,X_4,X_5)$ after the measurement that $(X_1,X_3) = (0,H)$ is as follows. Remember that denominator will be the Euclidean norm not the square of Euclidean norm.

```math
\Rightarrow |0\rangle_1 |H\rangle_3 \otimes
\frac{
     \left(
    \frac{1}{\sqrt{5}} |1\rangle_2 |D\rangle_4 |S\rangle_5 +
    \frac{1}{\sqrt{5}}|1\rangle_2 |H\rangle_4 |D\rangle_5
\right)}
{\sqrt{\frac{2}{5}}} \\

= \frac{1}{\sqrt{2}} |0\rangle_1 |1\rangle_2 |H\rangle_3 |D\rangle_4 |S\rangle_5 +
\frac{1}{\sqrt{2}} |0\rangle_1 |1\rangle_2 |H\rangle_3 |H\rangle_4 |D\rangle_5
```

Similary we can do for the other two parts.

#### Why do we need to keep the order of the vectors?

This is kind of important thing to note. If you have read previous blogs, then you might already know that the order of the cartesian product and tensor product doesn't matter as long as we keep the same order in all the places. Because of this reason we have used the subscript labels for the vectors in the dirac notation above.

Initially we defined the order of the systems as $(X_1,X_2,X_3,X_4,X_5)$. So all the cartesian products and tensor products should follow the same ordering. When we group the terms of the vector that are being measured we change the order of the vectors for the sake of simplicity. This change in order doesn't mean we can change order of the tensor product there. The order of the tensor product should be same as the order of the systems in $(X_1,X_2,X_3,X_4,X_5)$. To keep track of this information we use the labels here. 

These labels $1,2,3,4,5$(This can be any labels doesn't always need to be numbers) corresponds to the systems $(X_1,X_2,X_3,X_4,X_5)$ respectively. So even though we wrote down like this $|0\rangle_1 |H\rangle_3 |1\rangle_2 |D\rangle_4 |S\rangle_5$, Here the implicit order of the tensor product is as follows $|0\rangle_1 |1\rangle_2 |H\rangle_3 |D\rangle_4 |S\rangle_5$.


### How does the measurement of entangled quantum systems work?

The entanglement property tells us that when we measure just one part of the entangled systems the whole system collapse into that particular measurement outcome. This is because of the correlation between two entangled systems. Two entangled system will always tend to be in the same state as long as the entanglement is not destroyed.

It seems like that the measurement outcome of one of the entangled systems is depending on the measurement of the other system. So we may think that this property could be used for faster than light communication. But that is not fully correct understanding. 

The measurement outcome of both entangled systems will always depend on the intrinsic quantum state of the entangled system. When we measure one of the entangled systems it will just change our knowledge about the system. After measurement the whole system collapses into the measured outcome(that is not because of the measurement but rather due to the probabilities associated with the entangled quantum state).

For example think about the $|\phi_+\rangle = \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle)$ Bell state. In this entangled state both qubits will be in the $|00\rangle$ state with probability $\frac{1}{2}$ and in the state $|11\rangle$ with the probability $\frac{1}{2}$. If you take one hundred $|\phi_+\rangle$ states and measure each one of them, then you will get an outcome $|00\rangle$ for half of the times and $|11\rangle$ for other half of the times in a random order. 

Again take one hundred $|phi_+\rangle$ states and only measure the first(or second) qubit of the $|\phi_+\rangle$ state for one hundred times, then also you will get similar outcome in a different random order. So the outcome only depends on the probability values associated with the actual quantum state rather than the action of measurement.

The above experiment will give us same outcomes regardless of the distance between two qubits. By only measuring the one qubit we will know the state of the other qubit regardless of the measurement of the other qubit. This only changes our knowledger about the other system. The action of measurement of one qubit does not have any control over the actual measurement outcome.

> ***Important***: Currently there are no known unitary operation U which can applied on just one of the two entangled qubits to give the guaranteed outcome(either give the output 0 or 1 with one hundred percent outcome probability) without destroying the entanglement itself(if entanglement is destroyed then the operation will only affect one of the entangled system). If we can find such a unitary operation U(that can do the above mentioned action without destroying the entanglement), then we could use that unitary operation U to send some message to a user in a far away location with speed faster than light can travel. This phenomenon I have explainded at the end of this blog.
> Even if we could find a unitary operation U that maximises the probability outcome to more than ninety-nine percent, then we can send message faster than light with high probability of correctness of the message.

> ***Two way communication:*** Even with a unitary operation U that we discussed above sending a message(one way non-acknowledged communication) seems easier than the real time two way communications because of the following property of the quantum systems.
> As soon as we measure the quantum system, the whole system will collapse into the measured outcome. After that any number of measurements will result in the same outcome. So if the receiver measured the entangled state before applying the unitary operation U, then the whole entangled system will collapse into the measured outcome.

> ***Because of these reasons currently there are no fater than light communication possible using the quantum entanglement property.***



## What is unitary operation on quantum multiple systems?

The unitary operations on quantum multiple systems bring the ideas from both unitary operation on the quantum single system and probabilistic operations on the classical single system. When we think about the multiple systems as a single combined system then the unitary operations are defined by unitary matrices similar to the quantum single sytem. But here the row and column indeces of the unitary matrix will correspond to the cartesian product set of the classical state sets of the individual systems.

Lets take an example of two qubits $(X_1,X_2)$ where $X_1$ and $X_2$ each has the classical state set $\Sigma=\{0,1\}$. Then the following matrix applies Hadamard operation on the each individual bit of the two qubits system.

```math
\begin{equation}\tag{Ex-10}
\begin{split}

H = 
\begin{pmatrix} 
\frac{1}{2} & \frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\\\
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\\\
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} & -\frac{1}{2} \\\\
\frac{1}{2} & -\frac{1}{2} & -\frac{1}{2} & \frac{1}{2}
\end{pmatrix}

\end{split}
\end{equation}
```

This can be obtained using the formula for tensor product of two matrices specified in `Ex-8` in the [131_MS_Classical_Information](./131_MS_Classical_Information.md) blog. You can check that for this matrix $H H^\dagger  = H^\dagger H = I$, where I is identity matrix.

If you apply this operation on the state vector $|01\rangle$ you will get the following result. This is a usuall matrix multiplication operation.

```math
H|01\rangle 
= H \begin{pmatrix}
0 \\ 1 \\ 0 \\ 0
\end{pmatrix}

=\begin{pmatrix}
\frac{1}{2} \\\\ -\frac{1}{2} \\\\ \frac{1}{2} \\\\ -\frac{1}{2}
\end{pmatrix}

= \frac{1}{2}|00\rangle -
\frac{1}{2}|01\rangle +
\frac{1}{2}|10\rangle -
\frac{1}{2}|11\rangle
= |+\rangle|-\rangle
```

We have got the result as expected. Here note that we are representing the result in the vector form and also in dirac notation. Remember that specifying full matrices and vectors won't always be possible. So sometimes we use dirac notations to simplify things. But while using dirac notation we may loose some patterns of the operations, which we might have figured out if we have used the full matrix format. So both these approaches has its own pros and cons.

#### Another example of unitary operation(This is specifically called reversible operation)?

If an operation is both deterministic and unitary then it is called reversible operations. When we apply deterministic operation to some classical state it will always give the result as another calssical state. We have seen one such example in `Ex-7` in the [131_MS_Classical_Information](./131_MS_Classical_Information.md) blog. The reversed operation of the particular unitary matrix is computed by the `conjugate transpose` of the unitary matrix that represents the original operation.

```math
U = \sum_{k=0}^{7} |binary \; encoding\; of \;((k+1) \;mod \;8)\rangle
\langle binary \; encoding\; of \; k| \\
```

The above operation is deterministic. If you give the input number from 0 to 7 in the binary form, then this operation will add 1 to that number and find the (mod 8) of that new number. The conjugate transpose of the U is as follows.

```math
\begin{equation}\tag{Ex-11}
\begin{split}

U^\dagger = \sum_{k=0}^{7}
| binary \; encoding\; of \; k\rangle
\langle binary \; encoding\; of \;((k+1) \;mod \;8)| \\

= \sum_{k=0}^{7} |binary \; encoding\; of \;((k-1) \;mod \;8)\rangle
\langle binary \; encoding\; of \; k|

\end{split}
\end{equation}
```

This opearation does the reverse or inverse of the operation done by the U. Note that conjugate transpose of $(|k+1\rangle \langle k|)^{\dagger} = |k\rangle \langle k+1|$.


### How do we represent independent operations?

If unitary operations are applied individually on each one of the multiple systems, then the operation on the joint system will be described by the tensor product of the unitary matrices that represent the individual operation. If you can think about it this is analogous to what we have done for the classical multiple systems.

Suppose If $U_1,U_2,\cdots,U_n$ are unitary matrices that describe unitary operations on the individual systems $X_1,X_2,\cdots,X_n$ respectively, then the tensor product $U_1 \otimes U_2 \otimes \cdots \otimes U_n$ will describe the joint operation on the joint system $(X_1,X_2,\cdots,X_n)$. The fact that the tensor product of unitary matrices is again a unitary matrix can be proved as follows,

```math
\begin{equation}\tag{9}
\begin{split}
&\Rightarrow (U_1 \otimes U_2 \otimes \cdots \otimes U_n)(U_1 \otimes U_2 \otimes \cdots \otimes U_n)^\dagger \\

&= (U_1 \otimes U_2 \otimes \cdots \otimes U_n)(U_1^\dagger \otimes U_2^\dagger \otimes \cdots \otimes U_n^\dagger) \\

&= (U_1 U_1^\dagger) \otimes (U_2 U_2^\dagger) \otimes \cdots \otimes (U_n U_n^\dagger) \\

&= I_1 \otimes I_2 \otimes \cdots \otimes I_n \\

&= I

\end{split} 
\end{equation}
```


> **The mixed-product property**: the property of the tensor product that is used here is: $(A \otimes B) (C \otimes D) = AC \otimes BD$.

In the second step we have used the fact that computing tensor product of matrices and then conjugate transposing it is equal to first conjugate transposing each of the matrices then finding the tensor product. In the third step we have used the fact that tensor product of matrices is multiplicative(The mixed-product property). Since all the $U_i$ for $1 \leq i \leq n$ are unitary matrices we got the Identity matrices as a result. Then the tensor product of these idenetity matrices is going to be a identity matrix that corresponds to the joint system $(X_1,X_2,\cdots,X_n)$.

#### Doing nothing on one system

There might be situations where we want apply some operation on just one(or proper subset) of the systems and do nothing for other(or remaining) systems. We have already learnt about this concepte in the probabilistic operation. Here also it is going to be the same idea. Doing nothin on the other(or remaining) systems is equivalent to applying the identity operation. We already know that the identity operation is represented by the idenetity matrix $I_X$ with row and column indeces corresponding to the classical state set of the system X.

For example take an example of two qubits $(X_1,X_2)$ and we want to apply an Hadamard operation to the $X_1$ and do nothing to the $X_2$. This operation will be described by the following unitary matrix.

```math
\begin{equation}\tag{Ex-12}
\begin{split}

H \otimes I_{X_2} &=
\begin{pmatrix}
\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\
\frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}}
\end{pmatrix} \otimes
\begin{pmatrix}
1 & 0 \\ 0 & 1
\end{pmatrix}\\

&= \begin{pmatrix}
\frac{1}{\sqrt{2}} & 0 & \frac{1}{\sqrt{2}} & 0 \\
0 & \frac{1}{\sqrt{2}} & 0 & \frac{1}{\sqrt{2}} \\
\frac{1}{\sqrt{2}} & 0 & -\frac{1}{\sqrt{2}} & 0 \\
0 & \frac{1}{\sqrt{2}} & 0 & -\frac{1}{\sqrt{2}}
\end{pmatrix}

\end{split}
\end{equation}
```

Similarly we could find a unitary matrix for the case where we apply hadamard operation to the system $X_2$ and do nothing to the $X_1$. This unitary operation could be described by the unitary matrix $I_{X_1} \otimes H$.



### Examples of the non independent operations

In the previous section we have learnt the concept of independent operations. But not all the operations on the joint system could be represented by the tensor product of the unitary matrices, just like the fact that not all the quantum state vectors are product vectors. 

For example consider a swap or controlled unitary operations. In thse situations the nature of the operation itself is not for individual systems. Swap operation will always need two or more systems then only we can swap classical states of two systems(or two subset of the systems). Similary in the case of controlled unitary operation we always need one(or subset of systems) as control system and remaining systems as target system. We will see some of these examples below.

### The swap operation 

Lets take two quantum systems $X_1$ and $X_2$ with the classical state set $\Sigma$. Note that having the same classical state set is necessary because we are doing the swap operation. Then the swap operation on the joint system $(X_1,X_2)$ will inter change the contents of the two systems. We call this operation as SWAP. Then the swap operation for any two calssical states $a,b \in \Sigma$ will be defined as follows

```math
SWAP \; |a\rangle|b\rangle  = |b\rangle|a\rangle
```

We could compute the unitary matrix for the swap operation using the following equation.

```math
SWAP = \sum_{c,d \in \Sigma}|c\rangle \langle d| \otimes |d\rangle \langle c|
```

We are going to derive this using the mixed-product property of the tensor product. Suppose for the input $\langle d|  \otimes \langle c|$ the output is $\langle c| \otimes \langle d|$, then based on the properties of the tensor product we can derive the following equation.

```math
\begin{split}

&=\sum_{c,d \in \Sigma} (|c\rangle \otimes |d\rangle ) (\langle d| \otimes \langle c|) \\

&= \sum_{c,d \in \Sigma} |c\rangle \langle d| \otimes |d\rangle \langle c| \\

\end{split}
```

or we can think of the above equation as we are defining the input vs ouput combination for each of the individual systems separately and then after that we are finding tensor product of those two matrices. For each pair $c,d \in \Sigma$, for the first system if $\langle d|$ is the input, then the $|c\rangle$ will be the output. But at the same time for the second system $\langle c|$ should be the input and the $|d\rangle$ should be the output.


>**Important:** \
> In the above definitions we are defining an input as row vector such as $\langle d|$ and output as a column vector such as $|c\rangle$. This is only for the purpose of computing the unitary matices. But usually when we apply unitary operation to a column vector it gives another column vector as an output.

The swap operation the joint system of two qubits $(X_1,X_2)$ will be defined as follows.

```math
\begin{equation}\tag{Ex-13}
\begin{split}
SWAP = \begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
\end{split}
\end{equation}
```

### The controlled Unitary operation

Lets take an example that X is a qubit and Y is an arbitrary quantum system. We have some unitary operation that is described by the unitary matrix U. What we call a controlled unitary operation is that if X=0 then do nothing to Y and if X=1 then apply the unitary operation U to Y. The unitary matrix for this can be computed as follows. Here $I_Y$ is the identity matrix that corresponds to the system Y.

```math
CU = |0\rangle \langle 0| \otimes I_Y + |1\rangle \langle 1| \otimes U
```

Suppose we want to apply the controlled pauli X operation(It is also known as NOT operation or $\sigma_x$ operation). We have seen this pauli-X operation in `Ex-4` in the [101_SS_Quantum_Information](./101_SS_Quantum_Information.md).

```math
\begin{equation}\tag{Ex-14}
\begin{split}

CX &= |0\rangle \langle 0| \otimes I_Y + |1\rangle \langle 1| \otimes X \\
&= 
\begin{pmatrix} 1 \\ 0 \end{pmatrix} 
\begin{pmatrix} 1 & 0 \end{pmatrix} \otimes 
\begin{pmatrix} 1 & 0 \\ 0 & 1\end{pmatrix} + 
\begin{pmatrix} 0 \\ 1 \end{pmatrix} 
\begin{pmatrix} 0 & 1 \end{pmatrix} \otimes 
\begin{pmatrix} 0 & 1 \\ 1 & 0\end{pmatrix} \\

&=\begin{pmatrix} 
1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 \\ 0 & 0 & 1 & 0
\end{pmatrix}

\end{split}
\end{equation}
```

Another example is a contolled pauli-Z(It is also known as phase flip or $\sigma_z$ operation) operation.

```math
\begin{equation}\tag{Ex-15}
\begin{split}

CZ &= |0\rangle \langle 0| \otimes I_Y + |1\rangle \langle 1| \otimes \begin{pmatrix}
1 & 0 \\ 0 & -1
\end{pmatrix} \\

&=\begin{pmatrix} 
1 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 \\ 0 & 0 & 0 & -1
\end{pmatrix}

\end{split}
\end{equation}
```


#### Fredkin operation or Fredkin gate

Now consider a three qubit system $(X_1,X_2,X_3)$. The first system $X_1$ is a controll bit and it controls the swap operation on the remaining two systems $X_2$ and $X_3$. This operation is called Fredkin operation(or Fredkin gate) named after the Edward Fredkin. Here $I_{X_2}$ and $I_{X_3}$ are identity matrices that correspond to systems $X_2$ and $X_3$. Here the SWAP is a matrix from the example `Ex-13`.

```math
CSWAP |0cb\rangle = |0cb\rangle \\
CSWAP |1cb\rangle = |1bc\rangle
```

```math
\begin{equation}\tag{Ex-16}
\begin{split}

CSWAP &= |0\rangle \langle 0|  \otimes (I_{X_2} \otimes I_{X_3}) + |1\rangle \langle 1| \otimes SWAP
\\
&= \begin{pmatrix}
1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 & 0 & 0 & 1 & 0 \\
0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\ 0 & 0 & 0 & 0 & 0 & 0 & 0 & 1
\end{pmatrix}

\end{split}
\end{equation}
```

Here try to visualize how this matrix operation will act on a particular quantum state vector to to get a better understanding.


#### Toffoli operation or Toffoli gate

Now we will see about the controlled-controlled NOT operation( or CCX operation). It is called Toffoli operation (or Toffoli gate) named after Tommaso Toffoli. Suppose if we have same three qubit system $(X_1,X_2,X_3)$ as in the previous example, then first two qubits $X_1$ and $X_2$ are controll bits and the controlled NOT operation will be applied on the third qubit $X_3$. 

```math
\begin{equation}\tag{Ex-17}
\begin{split}

CSWAP &= (|00\rangle \langle 00| + |01\rangle \langle 01| +  |10\rangle \langle 10|)  \otimes I_{X_3} + |11\rangle \langle 11| \otimes X \\
&= \begin{pmatrix}
1 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\ 0 & 1 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 & 0 & 0 & 0 & 0 \\ 0 & 0 & 0 & 1 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 & 0 & 0 & 0 \\ 0 & 0 & 0 & 0 & 0 & 1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 1 \\ 0 & 0 & 0 & 0 & 0 & 0 & 1 & 0
\end{pmatrix}

\end{split}
\end{equation}
```




## Thought process with Entanglement
This is only a thought experiement. The below mentioned idea won't work untill we find a unitary operation U such that if we apply the unitary operation U on just one part of the entangled systems, then that will affect the probability outcome of the whole entangled system without destroying the entanglement.

### Presumption:

- Alice and Bob each have one hundred qubits that are entangled together. These entangled qubits are of the same kind which we take as $\phi_+ \rangle$. 

- Bob is going to travel to Planet X which is one hundred light years away from the Earth. Bob will travel at the speed of light so it will take hundred light years for him to reach that Planet X. As soon as Bob reaches Planet X he would like to know the status of the wellness of the Earth at the time of ninety-nine light years.

- If Alice sends the status of the Earth at the 99th light year to Bob using the classical communication, then it will take another 100 light years to reach Bob.

- But we know that Bob and Alice each share 100 entangled qubits of type $\phi_+ \rangle$. Can we use these entangled qubits to send a message to Bob with high certainty? We will explore this idea further.

- Just for the sake of this experiement assume that there exists a unitary operation U such that if we apply the unitary operation U on just one part of the entangled systems, then that will change the probability outcome of the whole entangled system without destroying the entanglement.


### if such unitary operation U exists, then the possible solution to send a message with high probability:

- Be noted that communication between Bob and Alice is going to be neither two way nor real time communication. Alice is just going to send a message to Bob about the status of the Earth.

- Before Bob starts his journey Alice and Bob agrees that if the Earth is good on the ninety-ninth light year, then Alice will apply a unitary operation U on her one hundred qubits such that this operation will maximize the probability of getting an outcome $|1\rangle$ to 99.99 percent. Bob will measure these qubits anytime after the 99th light year to know the status of the Earth.

- If Bob measures and gets an outcome $|1\rangle$ for 99 percent of his measurements, then he can decide with high probability that the Earth is good on the 99th light year.

- Even If Bob measures his qubits one year after(the time interval would have been pre agreed before the journey) Alice’s operation, we can say that it only took one year to send this message. But in classical communication it would have taken minimum of 100 light years to send this message.
