# Quantum Information(Multiple Systems)

In the previous blog we have learnt about the classical information of multiple systems. In this blog we will learn about the quantum information of multiple systems. The ideas are going to be the same as we discussed in the probabilistic part of the classical multiple systems. When you think of multiple quantum systems as a single system similar to how we thought about multiple calssical systems, then the quantum state of joint quantum system can be represented by a unit vector. This unit vector is same as the one which we have used to represent a single quantum system but larger. Remember that a unit vector is a vector with Euclidean norm equal to 1.

## How to represent quantum state of multiple systems?

So If we think about multiple systems together as a single system, then the quantum state will be represented by a unit vector that is very similar to the quantum single system. But now the entries of the unit vector correspond to the `cartesian product` of the classical state sets of individual systems. For example consider two qbits $X_1$ and $X_2$ with the classical state sets $\Sigma_1$ and $\Sigma_2$. Then the classical state set of the joint system $(X_1, X_2)$ will be $\Sigma_1 \times \Sigma_2$.

$$
\begin{equation}\tag{1}
\begin{split}
& \Sigma_1=\{0,1\}  \;\;\; \Sigma_2=\{0,1\} \\
& \Sigma_1 \times \Sigma_2 = \{ 00, 01, 10, 11 \} \\
\end{split}
\end{equation}
$$

The given below examples are quantum state vectors represented using the dirac notation.

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

All of the above vectors are valid quantum state vectors with Euclidean norm equal to 1. Note that we use the square root($\sqrt{}$) notation explicitly to make the process of verifying the Euclidean norm simpler. There are multiple ways that we could use to reprsent the same qunautm state vector using dirac notation. All the given below notation are valid and equivalent. We will use one of these notations based on our need.

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

## How do we represent the independence of the quantum multiple systems or joint sytem?

Independence of the joint quantum system is same as the independence of the joint classical system. If we can write the quantum state vector of the joint system as a tensor product of quantum state vectors of the individual systems, then we will say that those individual systems are independent of each other. This is called a product state.

For example if $|\psi_1\rangle$ is a quantum state vector of the $X_1$ and $|\psi_2\rangle$ is a quantum state vector of the $X_2$, then the tensor product $|\psi_1\rangle \otimes |\psi_2\rangle$ will be the quantum state vector of the joint system $(X_1,X_2)$. Here $|\psi_1\rangle \otimes |\psi_2\rangle$,  $|\psi_1\rangle |\psi_2\rangle$ and $|\psi_1 \otimes \psi_2\rangle$ are equivalent notations. The idea is same as the classical state of the joint classical system. The only difference here is that we are using a quantum state vector instead of a classical state vector.

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

So here if $|| |\psi_1\rangle || = 1$ and $|| |\psi_2\rangle || = 1$ then the $|| |\psi_1\rangle \otimes |\psi_2\rangle || = 1$. So if vectors that represent individual systems are valid qauntum state vectors then tensor product of vectors is also going to be a valid quantum state vector. Here we are summing over the probability value for each possible $a,b \in \Sigma_1 \times \Sigma_2$. Remembering that for each such pair of a,b this $| \langle ab|\psi_1 \otimes \psi_2 \rangle |$ will give the absolute value of the complex number that is associated with the classical state $|ab\rangle$.

We could generalize this idea easily for three or more systems. Suppose quantum state vectors $|\psi_1\rangle, |\psi_2\rangle, \cdots ,|\psi_n\rangle$ correspond to quantum systems $X_1,X_2, \cdots ,X_n$ respectively, then the quantum state vector $|\psi\rangle$ will represent the quantum state of the joint system $(X_1,X_2,\cdots,X_n)$.

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

### What is an entanglement of the join quantum system?

We can't always write a quantum state vector of multiple systems as a product of quantum state vectors of the individual systems(as a product state). When such a scenario happens we would say that quantum systems are entangled or correlated. Entanglement is important feature of quantum systems. We will see that it is a more complicated concept when we learn about the more general description of the quantum information using the density matrix formulation. But in the quantum state vector description of the quantum information, the entanglement is equivalent to the correlation.

> Note: Alternatively quantum entanglement can be defined as the non-classical correlation. So the classical correlation and quantum correlation are not the same. The quantum entanglement has its own properties which we couldn't find in the classical probabilistic systems. The quantum system differs in a way that if you apply some operation to one of the entangled systems, then the probability outcome of the other system(that is in entanglement) will also change as long as the operation doesn't destroy the entanglement itself. We will discuss about this further in the end of this blog and in future blogs. 

For example if we want to show that the quantum state vectors $|\psi_1\rangle$ and $|psi_2\rangle$ that corresponds to systems $X_1$ and $X_2$ in the example `Ex-2` are independent, then you have to show that $|\psi\rangle$ as a tensor product of two quantum state vectors $|\psi_1\rangle$ and $|\psi_2\rangle$. The following equation formalizes this condition.

$$
\begin{equation}\tag{Ex-3}
|\psi_1\rangle \otimes |\psi_2\rangle = 
\frac{1}{\sqrt{2}}|00\rangle +
\frac{1}{\sqrt{2}}|11\rangle \\
\end{equation}
$$

The term $|01\rangle$ is 0 in this equation. That means the following equation must be true.

$$
\langle 01|\psi\rangle =
\langle 01|\psi_1 \otimes \psi_2\rangle =
\langle 0|\psi_1\rangle \langle 1|\psi_2\rangle = 0
$$

This means that either $\langle 0|\psi_1\rangle = 0$ or $\langle 1|\psi_2\rangle = 0$ or both are zero. But This will contradict the fact that the following two equations are true.

$$
\langle 00|\psi\rangle =
\langle 00|\psi_1 \otimes \psi_2\rangle =
\langle 0|\psi_1\rangle \langle 0|\psi_2\rangle = \frac{1}{2} \\
and \\
\langle 11|\psi\rangle =
\langle 11|\psi_1 \otimes \psi_2\rangle =
\langle 1|\psi_1\rangle \langle 1|\psi_2\rangle = \frac{1}{2}
$$

If $\langle 0|\psi_1\rangle = 0$, then it will contradict the first equation. If $\langle 1|\psi_2\rangle = 0$, then it will contradict the second equation. So this means that the above vector in `Ex-3` can't be written as product state. So they are entangled or correlated.

#### Examples of independent quantum state vectors.

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

### Some more commonly used quantum state vectors that are correlated or entangled.

The given below are some of the commonly used quantum state vectors that are in the entangled state.

#### Bell States

Bell states are two qbit quantum state vectors that are in the entangeled states named after the physicist Jhon Stewart Bell. For the same reason as the example `Ex-3`, Bell states are entangled states.

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

These four vectors are called `Bell basis vectors`. Similar to the `standard basis vectors` we could represent any vector of dimension 2 as a linear combination of these vectors. For example see the given below equation.

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

#### Additional examples of quantum multiple systems

So far we have seen quantum multiple systems that are made up of same kind of individual systems. It is possible to have different kind of individual systems in the joint system. 

Suppose consider the system $X_1$ which is a qbit and systems $X_2$ and $X_3$ which will represent the four suits of the standard deck of the cards. Here classical state set of the qbit is $\Sigma_1$ and the classical state set of $X_2$ and $X_3$ is $\Sigma_2$.

$$\Sigma_2 = {C, D, H, S}$$
where C - Clubs, D- Diamonds, H-Hearts, S-Spades.

$$
|\psi\rangle = 
\frac{1}{2}|0\rangle |D\rangle |H\rangle +
\frac{1}{2}|0\rangle |D\rangle |S\rangle +
\frac{1}{\sqrt{2}}|1\rangle |C\rangle |H\rangle
$$

Next consider the joint system $(X_1,X_2,X_3)$, where systems $X_1$, $X_2$ and $X_3$ are having the classical state set $\Sigma = \{0,1,2\}$. We call this system with three classical states as `trits` just like `bits`. In quantum world it is `qtrits`.

$$
|\psi\rangle = 
\frac{1}{\sqrt{3}}|0\rangle |1\rangle |1\rangle +
\frac{1}{\sqrt{3}}|0\rangle |2\rangle |0\rangle +
\frac{1}{\sqrt{3}}|1\rangle |0\rangle |2\rangle
$$

Generally a system with the classical state $\Sigma = \{0,1,2,...,d-1\}$ is called `qdits` for arbitrary value of d.


## What is the measurement of quantum multiple systems or the joint quantum system?

Standard basis measurement of quantum multiple systems is same as measuring a single quantum system. Suppose if particular quantum system is represented by a quantum state vector $|\psi\rangle$ and classical state set $\Sigma$, then the standard basis measurement for each classical state $a \in \Sigma$ is obtained with the probability equal to $| \langle a|\psi\rangle |^2$.

Suppose assume that the quantum systems $X_1,X_2,...,X_n$ are having the classical state set $\Sigma_1,\Sigma_2,...,\Sigma_n$ respectively. If the joint system $(X_1,X_2,...,X_n)$ is represented by a quantum state vector $|\psi\rangle$ and classical state set $\Sigma = \Sigma_1 \times \Sigma_2 \times \cdots \times \Sigma_n$, then the standard basis measurement for each classical state $(a_1,a_2,\cdots,a_n) \in \Sigma$ will be obtained with the probability equal to $|\langle a_1,a_2,\cdots,a_n|\psi\rangle|^2$

For example, suppose systems $X_1$ and $X_2$ are jointly in the state $|\psi\rangle$.

$$|\psi\rangle = \frac{3}{5} |00\rangle - i\frac{4}{5} |11\rangle$$

If we measure the quantum system that is in the above state, then the systems $(X_1,X_2)$ will be in the state $(0,0)$ with the probability $\frac{9}{25}$ and in the state $(1,1)$ with the probability $\frac{16}{25}$.


### How do we express the partial measurement of quantum multiple systems?

We could define the partial measurement of multiple quantum systems similar to classical multiple systems. Lets take an example of two qbits $X_1$ and $X_2$ with the classical state set $\Sigma_1$ and $\Sigma_2$ respectively. The joint system $(X_1,X_2)$ will be represented by a quantum state vector $|\psi\rangle$ using the Dirac notation.

$$
\begin{equation}\tag{4}
|\psi\rangle = \sum_{a,b \in \Sigma_1 \times \Sigma_2} 
\alpha_{ab} |ab\rangle
\end{equation}
$$

where $\{\alpha_{ab}: (a,b) \in \Sigma_1 \times \Sigma_2 \}$ is collection of complex numbers satisfying the condition that the sum of absolute value of those complex numbers should be equal to 1(Remember that this condition is equivalent to saying that the Euclidean norm is 1).

$$
\begin{equation}\tag{5}
\sum_{a,b \in \Sigma_1 \times \Sigma_2} |\alpha_{ab}|^2 = 1
\end{equation}
$$

As we already know that if both $X_1$ and $X_2$ are measured, then the probability that we will get the state (a,b) as outcome could be calculated by multiplying the classical state(`bra` notation) $\langle ab|$ and state vector(`ket` notation) $|\psi\rangle$.

$$
\begin{equation}\tag{6}
Pr((X_1,X_2)=(a,b))=|\langle ab|\psi\rangle|^2 = |\alpha_{ab}|^2
\end{equation}
$$

Suppose if we are only measuring the system $X_1$, then the probability outcome of `a` is computed by the following summation. This is the marginal(or reduced) probability of a joint system.

$$
\begin{equation}\tag{7}
Pr(X_1=a) = \sum_{b \in \Sigma_2} |\alpha_{ab}|^2
\end{equation}
$$

After measuring the quantum system $X_1$, it will collapse into one of the possible classical states $|a\rangle \in \Sigma_1$. If individual systems are not independent, then we know that the measurement of one(or proper subset) of the systems will change our knowledge about the other(or remaining) systems. So the quantum state vector of a joint system should reflect this change. This idea can be represented by conditional probability similar to the probabilistic settings.

Now we define the $|\psi\rangle$ in the `equation-4` in a slightly different format, so that we could use that definition to understand the conditional probability.


$$
\begin{equation}\tag{8}
\begin{split}
|\psi\rangle &= \sum_{a \in \Sigma_1} |a\rangle \otimes |\phi_a\rangle \\

|\phi_a\rangle &=\sum_{b \in \Sigma_2} \alpha_{ab} |b\rangle
\end{split}
\end{equation}
$$


Then the probability that $X_1=a$ that is defined in the `equation-7` can be equivalently defined using the Euclidean norm of the quantum state vector $|\phi_{ab}\rangle$ for any $a \in \Sigma_1$.

$$Pr(X_1=a) = || |\phi_a\rangle ||^2$$

Now suppose that we have measured $X_1=a$, then the state of the system $X_2$ will be represented by the following vector.

$$
\begin{equation}\tag{8}
|a\rangle \otimes 
\frac{|\phi_a\rangle}{|| |\phi_a\rangle||}
\end{equation}
$$

Here the resulting vector $|a\rangle \otimes |\phi_a\rangle$ will represent the quantum state of the system $X_2$ on condition that we have measured the state of the system $X_1 = a$ for any $a \in \Sigma_1$. The denominator term $|| |\phi_a\rangle ||$ is to make the Euclidean norm of the resulting vector to be equal to 1(This process is called normalization). This will make the resulting vecor a valid quantum state vector. Remember that in the probablistic setting we divided the vector by the sum of probabilities of that vector to do the normalization.

### Examples of partial measurement

Lets take an usual example of a joint system with two qbits $(X_1,X_2)$ which is represented by the following quantum state vector $|\psi\rangle$.

$$
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
$$

The probability of an outcome $X_1 = 0$ can defined by the following Euclidean norm,

$$
Pr(X_1=0) = 
\left|\left| \frac{1}{\sqrt{2}}|0\rangle -
i\frac{1}{\sqrt{6}}|1\rangle \right|\right|^2 
= \frac{1}{2} + \frac{1}{6} 
= \frac{2}{3}
$$

> **Note**: \
>Here note that the Euclidean norm of the vector is the square root of the sum of square of the the absolute value of each entry of the vector. To cancel out this square root we have to raise to the power 2 in the above equation. Here each entry of the vector is the complex number. Remember that the absolute value of the complex number is calculated using the formula $|a+bi| = \sqrt{a^2 + b^2}$

After measuring the $X_1=0$, the state of the whole system $|\psi\rangle$ collapses into a following vector.

$$
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
$$

If you try to verify the Euclidean norm of the above vector, then you will get the value $\frac{3}{4} +\frac{1}{4} = 1$. This is a useful check for the correctness of our calculation. This ensures that the resulting vector is a valid quantum state vector.

The probability of an outcome $X_1=1$ will be as follows,

$$
Pr(X_1 = 1) = 
\left|\left| \frac{1}{\sqrt{6}}|0\rangle +
i\frac{1}{\sqrt{6}}|1\rangle \right|\right|^2 
= \frac{1}{6} + \frac{1}{6} 
= \frac{1}{3}
$$

Here also the sum of $Pr(X_1=0) +Pr(X_1=1) = 1$ is again a useful check.
As we have done previously, as soon as we get the measurement outcome $X_1 = 1$, the state of the whole system will collapse into the measured outcome. When $X_1 = 1$, the state of the system $X_2$ will be defined as follows.

$$
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
$$

In a similar way we could define the case where only the system $X_2$ is measured and the $X_1$ is not measured.

### What about reduced quantum state of any one system?

This example shows the limitation of the simplified definition of the quantum information that we have been learning so far. In the probabilistic settings we have defined the reduced(or marginal) state of just one of the two systems(or the proper subset of the three or more systems). But the simplified definition of the quantum information using quantum state vectors doesn't give us a way to define the same for the quantum settings.

Suppose the probabilistic state of the two systems $(X_1,X_2)$ is represented by the following probability vector.

$$
|\phi\rangle = \sum_{a,b \in \Sigma_1 \times \Sigma_2}
r_{ab}|ab\rangle
$$

Then the reduced or marginal state of $X_1$ is

$$
\sum_{a,b \in \Sigma_1 \times \Sigma_2} 
r_{ab}|a\rangle
$$

But if we have a quantum state of the two systems $X_1,X_2$ is represented by the following quantum state vector.

$$
|\psi\rangle = \sum_{a,b \in \Sigma_1 \times \Sigma_2}
\alpha_{ab}|ab\rangle
$$

Then the following equation won't make any sense

$$
\sum_{a,b \in \Sigma_1 \times \Sigma_2} 
\alpha_{ab}|a\rangle
$$

The above vector doesn't always make sense because the resulting vecot won't always be a valid quantum state vector. The problem with the above equation is that in the probabilistic settings we have defined the probability of $X_1$ as $r_{ab}$ for each classical state $a \in \Sigma_1$ using the following sum formula,

$$
r_a = \sum_{b \in \Sigma_2} r_{ab}
$$

If we try to construct a similar formula for the quantum state, then we will get something like below.

$$
\alpha_a = \sum_{b \in \Sigma_2} \alpha_{ab}
$$

The above formula won't always give us a valid quantum state vector due to two reasons, First one is that $\alpha_{ab}$ is a complex number and the second is that we have defined the probability outcome of a quantum state vector using absolute values of those complex numbers. So directly adding up the complex numbers won't always give the correct probability for the state $X_1 = a$ for any $a \in \Sigma_1$. You can check this out with the `Ex-8`.

> **Note**: sum of absolute values squared of complex numbers is not equal to the absolute values square of the sum of complex numbers. For example suppose if $c_1$ and $c_2$ are two complex numbers, then $|c_1|^2 + |c_2|^2 \neq |c_1 + c_2|^2$. So we can't simply add the terms that contains $|a\rangle$ to get the complex number that corresponds to the state $|a\rangle$ of the system $X_1$, that will give us a wrong result.

The another way we may try is the following.

$$
\alpha_a = \sum_{b \in \Sigma_2} |\alpha_{ab}|^2
$$

We may try adding up absolute values of $\alpha_{ab}$. In fact this will give correct probability values for each state $a \in \Sigma_1$. But when we calculate absolute values we may loose some information about the system that was represented by the complex numbers(because of calculating absolute values). We will see that the more general description of quantum information will solve these kind of problems.

### Partial measurement of three or more systems

Measuring the proper subset of three or more systems is very similar to measuring just one of the two systems. In this case we will consider the subset of systems that are being measured as a single combined system and all the reamaing systems as the second system.

Assume that we have five systems $(X_1,X_2,X_3,X_4,X_5)$ together representing some information. The first two systems $X_1$ and $X_2$ are having a classical state set $\Sigma_1$ and all the remaining systems are having a classical state set $\Sigma_2$. The quantum state of the joint system is represented by the state vector $|\psi\rangle$.

$$
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
$$

So now assume that we are going to measure the first and third system in the joint systems $(X_1,X_2,X_3,X_4,X_5)$. So we will consider systems $X_1$ and $X_3$ together as the first system and all the remaining systems as the second system. We are going to group the similar states of the first system as we have done in the classical systems case. But since the system $X_2$ which is part of the second system but it is in the middle of $X_1$ and $X_3$. So we need a way of reordering these systems but still keep track of the initial order of them. For that purpose only we have labeled each vector with labels $1,2,3,4,5$ for the systems $(X_1,X_2,X_3,X_4,X_5)$ respectively. We will see soon that why we are doing this. So the equivalent vector for $|\psi\rangle$ with labels is as follows.

$$
|\psi\rangle = 
\frac{1}{\sqrt{5}}|0\rangle_1 |1\rangle_2 |H\rangle_3 |D\rangle_4 |S\rangle_5 +
\frac{1}{\sqrt{5}}|1\rangle_1 |1\rangle_2 |C\rangle_3 |D\rangle_4 |C\rangle_5 +
\frac{1}{\sqrt{5}}|0\rangle_1 |1\rangle_2 |H\rangle_3 |H\rangle_4 |D\rangle_5 +
\frac{1}{\sqrt{5}}|1\rangle_1 |0\rangle_2 |D\rangle_3 |D\rangle_4 |S\rangle_5 +
\frac{1}{\sqrt{5}}|1\rangle_1 |0\rangle_2 |C\rangle_3 |D\rangle_4 |S\rangle_5
$$

So now we will group them into two groups based on our measurement.

$$
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
$$

Now we will just take one part of the system and compute the probability outcome of the systems($X_1$ and $X_3$) and state vector for $(X_1,X_2,X_3,X_4,X_5)$ after the measurement. Then you can easily do the similar computation for the other two parts of the above equation.

The probability that we will obtain the result $X_1 = 0$ and $X_3 = H$ is as follows.

$$
\left|\left| 
    \left(
    \frac{1}{\sqrt{5}} |1\rangle_2 |D\rangle_4 |S\rangle_5 +
    \frac{1}{\sqrt{5}}|1\rangle_2 |H\rangle_4 |D\rangle_5
\right) \right|\right|^2 
= \frac{1}{5} + \frac{1}{5} = \frac{2}{5}
$$

The state of the systems $(X_1,X_2,X_3,X_4,X_5)$ after the measurement that $(X_1,X_3) = (0,H)$ is as follows. Remember that denominator will be the Euclidean norm not the square of Euclidean norm.

$$
\Rightarrow |0\rangle_1 |H\rangle_3 \otimes
\frac{
     \left(
    \frac{1}{\sqrt{5}} |1\rangle_2 |D\rangle_4 |S\rangle_5 +
    \frac{1}{\sqrt{5}}|1\rangle_2 |H\rangle_4 |D\rangle_5
\right)}
{\sqrt{\frac{2}{5}}} \\

= \frac{1}{\sqrt{2}} |0\rangle_1 |1\rangle_2 |H\rangle_3 |D\rangle_4 |S\rangle_5 +
\frac{1}{\sqrt{2}} |0\rangle_1 |1\rangle_2 |H\rangle_3 |H\rangle_4 |D\rangle_5
$$

Similary we can do for the other two parts.

#### Why do we need to keep the order of the vectors?

This is kind of important thing to note. If you have read previous blogs, then you might already know that the order of the cartesian product and tensor product doesn't matter as long as we keep the same order in all the places. Because of this reason we have used the subscript labels for the vectors in the dirac notation above.

Initially we defined the order of the systems as $(X_1,X_2,X_3,X_4,X_5)$. So all the cartesian products and tensor products should follow the same ordering. When we group the terms of the vector that are being measured we change the order of the vectors for the sake of simplicity. This change in order doesn't mean we can change order of the tensor product there. The order of the tensor product should be same as the order of the systems in $(X_1,X_2,X_3,X_4,X_5)$. To keep track of this information we use the labels here. 

These labels $1,2,3,4,5$(This can be any labels doesn't always need to be numbers) corresponds to the systems $(X_1,X_2,X_3,X_4,X_5)$ respectively. So even though we wrote down like this $|0\rangle_1 |H\rangle_3 |1\rangle_2 |D\rangle_4 |S\rangle_5$, Here the implicit order of the tensor product is as follows $|0\rangle_1 |1\rangle_2 |H\rangle_3 |D\rangle_4 |S\rangle_5$.


## What is unitary operation on quantum multiple systems?

So the unitary operations on multiple quantum systems bring ideas from both unitary operation on the quantum single system and probabilistic operations on the classical single system. When we think about the multiple systems as a single combined system then the unitary operations are defined by the unitary matrices similar to the quantum single sytem. But here the row and column indeces of the unitary matrix will correspond to the cartesian product set of the classical state sets of the individual systems.

Lets take an example of two qbits $(X_1,X_2)$ where $X_1$ and $X_2$ has the classical state set $\Sigma=\{0,1\}$. Then the following matrix applies Hadamard operation on the each individual bit of the two qbits system.

$$ 
\begin{equation}\tag{Ex-10}

H = 
\begin{pmatrix} 
\frac{1}{2} & \frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\\\
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\\\
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} & -\frac{1}{2} \\\\
\frac{1}{2} & -\frac{1}{2} & -\frac{1}{2} & \frac{1}{2}
\end{pmatrix}

\end{equation}
$$

This can be obtained using the formula specified in `Ex-8` in the [131_MS_Classical_Information](./131_MS_Classical_Information.md) blog. You can check that for this matrix $H H^\dagger  = H^\dagger H = I$, where I is identity matrix.

If you apply this operation on the state vector $|01\rangle$ you will get the following result. This is the usuall matrix multiplication.

$$
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
$$

We have got the result as expected. Here note that we are representing the result in the vector form and also in dirac notation. Remember that specifying full matrices and vectors won't be always possible. So sometimes we use dirac notations to simplify things. But while using dirac notation we may loose some patterns of the operations, which we might have figured out if we have used the full matrix form. So both these approaches has its own pros and cons.

#### What is reversible operations?

If the unitary operations are also deterministic, then we call them reversible operations. When we apply deterministic operation on some classical state it will always give the result as one of the possible calssical states. We have seen one such example in `Ex-7` in the [131_MS_Classical_Information](./131_MS_Classical_Information.md) blog. The reverse operation of the particular unitary matrix is computed by the `conjugate transpose` of the unitary matrix that represents the operation.

$$
U = \sum_{k=0}^{7} |binary \; encoding\; of \;((k+1) \;mod \;8)\rangle
\langle binary \; encoding\; of \; k| \\
$$

The above operation is deterministic. If you give the input number from 0 to 7 in the binary form, then this operation will add 1 to that number and find the (mod 8) of that new number. The conjugate transpose of the U is as follows.

$$
\begin{equation}\tag{Ex-11}
\begin{split}

U^\dagger = \sum_{k=0}^{7}
| binary \; encoding\; of \; k\rangle
\langle binary \; encoding\; of \;((k+1) \;mod \;8)| \\

= \sum_{k=0}^{7} |binary \; encoding\; of \;((k-1) \;mod \;8)\rangle
\langle binary \; encoding\; of \; k|

\end{split}
\end{equation}
$$

This opearation does the reverse or inverse of the operation done by the U.


### How do we represent independent operations?

If the unitary operations are applied individually on the individual systems of the collective systems, then the operation on the combined system will be described by the tensor product of the unitary matrices that represent the individual operation. If you can think about it this is analogous to what we have done for the classical multiple systems.

Suppose If $U_1,U_2,\cdots,U_n$ are unitary matrices that represent the unitary operations on the individual systems $X_1,X_2,\cdots,X_n$, then the tensor product $U_1 \otimes U_2 \otimes \cdots \otimes U_n$ will define the combined operation on the joint system $(X_1,X_2,\cdots,X_n)$. The fact that the tensor product of unitary matrices is again a unitary matrix can be proved as follows,

$$
\begin{equation}\tag{9}
\begin{split}
&\Rightarrow (U_1 \otimes U_2 \otimes \cdots \otimes U_n)(U_1 \otimes U_2 \otimes \cdots \otimes U_n)^\dagger \\

&= (U_1 \otimes U_2 \otimes \cdots \otimes U_n)(U_1^\dagger \otimes U_2^\dagger \otimes \cdots \otimes U_n^\dagger) \\

&= (U_1 U_1^\dagger) \otimes (U_2 U_2^\dagger) \otimes \cdots \otimes (U_n U_n^\dagger) \\

&= I_1 \otimes I_2 \otimes \cdots \otimes I_n \\

&= I

\end{split} 
\end{equation}
$$


> **The mixed-product property**: the property of the tensor product that is used here is: $(A \otimes B) (C \otimes D) = AC \otimes BD$.

In the second step we have used the fact that computing tensor product of matrices and then conjugate transposing it is equal to first conjugate transposing each of the matrices then finding the tensor product. In the third step we have used the fact that tensor product of matrices is multiplicative. Since all the $U_i$ for $1 \leq i \leq n$ are unitary matrices we got the Identity matrices as a result. Then the tensor product of these idenetity matrices is going to be a identity matrix that corresponds to the joint system $(X_1,X_2,\cdots,X_n)$.

#### Doing nothing on one system

One more thing we have to learn is that there might be cases when we want apply some operation on just one(or proper subset) of the systems and do nothing for other(or remaining) systems. We have already learnt about the similar case in the probabilistic operation. Here is also it is going to be the same idea. Doing nothin on the other(or remaining) systems is equivalent to applying the identity operation. We already know that the identity operation is represented by the idenetity matrix $I_X$ with row and column indeces corresponding to the classical state set of the system X.

For example take an example of two qbits $(X_1,X_2)$ and we want to apply an Hadamard operation on $X_1$ and do nothing on $X_2$. This operation can be described by the following unitary matrix.

$$
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
$$

Similarly we can define unitary matrix for the case where we apply hadamard operation on the system $X_2$ and do nothing on the $X_1$. This unitary operation can be described by the unitary matrix $I_{X_1} \otimes H$.



### Examples of the non independent operations

In the previous section we have learnt about the independent operations. But not all the operations on the combined multiple systems can be represented as the tensor product of the unitary matrices, just like the fact that not all the quantum state vectors are product vectors. 

For example consider a swap or controlled unitary operations. In thse cases the nature of the operation itself is not for the individual systems. Swap operation will always need two or more systems then one we can swap classical states of the two systems(or two subset of the systems). Similary in the case of controlled unitary operation we always need one(or subset of systems) as control systems and remaining systems as target systems. We see some of these examples below.

### The swap operation 

Lets assume that two quantum systems $X_1$ and $X_2$ with the classical state set $\Sigma$. Note that having the same classical state set is necessary because we are doing the swap operation. Then the swap operation on the joint system $(X_1,X_2)$ will inter change the contents of the two systems. This operation we define as SWAP. Then the swap operation for any two calssical states $a,b \in \Sigma$ is defined as follows

$$ SWAP \; |a\rangle|b\rangle  = |b\rangle|a\rangle$$

We can compute the unitary matrix for the swap operation using the following equation.

$$ SWAP = \sum_{c,d \in \Sigma}|c\rangle \langle d| \otimes |d\rangle \langle c|$$

We can derive this using the mixed-product property of the tensor product. Suppose for the input $\langle d|  \otimes \langle c|$ the output is $\langle c| \otimes \langle d|$, then based on the properties of the tensor product we can derive the following equation.

$$
\begin{split}

&=\sum_{c,d \in \Sigma} (|c\rangle \otimes |d\rangle ) (\langle d| \otimes \langle c|) \\

&= \sum_{c,d \in \Sigma} |c\rangle \langle d| \otimes |d\rangle \langle c| \\

\end{split}
$$

or we can think of the above equation as we are defining the input vs ouput combination for each of the individual systems separately and then after that we are finding tensor product of those two matrices. For each pair $c,d \in \Sigma$, for the first system if $\langle d|$ is the input, then the $|c\rangle$ will be the output. But at the same time for the second system $\langle c|$ should be the input and the $|d\rangle$ should be the output.


>**Important:** \
> In the above definitions we are defining the input as row vector such as $\langle d$ and output as column vector such as $|c\rangle$. This is only for the purpose of computing the unitary matices. But usually when we apply unitary operation to a column vector it gives another column vector as an output.

The swap operation the joint system of two qbits $(X_1,X_2)$ is defined as follows.

$$
\begin{equation}\tag{Ex-13}
SWAP = \begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 0 & 1 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
\end{equation}
$$

### The controlled Unitary operation

Lets take an example that X is a qbit and Y is an arbitrary quantum system. We have some unitay operation that is described by the unitary matrix U. The controlled unitary operation is that when X=0 then do nothing to Y and whne X=1 then apply the unitary operation on Y. The unitary matrix for this can be computed as follows. Here $I_Y$ is the identity matrix that corresponds to the system Y.

$$
CU = |0\rangle \langle 0| \otimes I_Y + |1\rangle \langle 1| \otimes U
$$

Suppose we want to apply the controlled pauli X operation(It is the NOT operation or $\sigma_x$ operation). We have seen this pauli-X operation in `Ex-4` in the [101_SS_Quantum_Information](./101_SS_Quantum_Information.md).

$$
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
$$

Another example is Contolled pauli-Z(It is phase flip or $\sigma_z$ operation) operation.

$$
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
$$


#### Fredkin operation or Fredkin gate

Now consider a three qbit systems $(X_1,X_2,X_3)$. The first system $X_1$ is a controll bit and we apply the swap operation on the remaining two systems $X_2$ and $X_3$. This operation is called Fredkin operation(or Fredkin gate) named for the Edward Fredkin. Here $I_{X_2}$ and $I_{X_3}$ are identity matrices that correspond to systems $X_2$ and $X_3$. Here the SWAP is a matrix from the example `Ex-13`.

$$
CSWAP |0cb\rangle = |0cb\rangle \\
CSWAP |1cb\rangle = |1bc\rangle
$$

$$
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
$$

Here to understand this better try to visualize how this matrix operation may be applied on any particular quantum state vector.


#### Toffoli operation or Toffoli gate

Now we will see about the controlled-controlled NOT operation( or CCX operation). It is called Toffoli operation (or Toffoli gate) named for the Tommaso Toffoli. Suppose if we have same three qbit system $(X_1,X_2,X_3)$ as in the previous example, then first two bits $X_1$ and $X_2$ are controll bits and the controlled NOT operation is applied on the third bit $X_3$. 

$$
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
$$


## How does the partial operations and measurements affects the entangled systems?

> Note that Measurement is a kind of operation. So as soon as we measure one of the entangled systems the whole system will collapse into that outcome. We will see in the future that just by measuring the entangled system we won't be able control the outcome of the measurement. The measurement outcome is kind of random(that only depends on the quantum state). So we can't use this particular property for faster than light communication. Applying some operation to one of the entangled pair might alter the probability outcome of the the whole entangled system, but that will not give the gurenteed outcome without destroying the entanglement itself. We will see one example for each of these cases below.  



If we apply some operation to just one(or subset) of the entangled systems and do nothing to the remaing system, then what will happen? We will discuss about it clearly here.

> Assume that there are two qbits that are in an entangled state like $|\phi_+ \rangle$ state. Alice has one qbit and Bob has another qbit in far away location. If Alice applies the NOT operation on her qbit. will it affect the state of the Bob's qbit?


Remember that in classical settings we have discussed that measurement or applying some operation on one system doesn't affect the probability outcome of the other system. It will not always be true for the quantum system. If two quantum systems are entangled, then applying some operation to the first system will try to preserve the overall system in an entangled state(even though it will not physically change the state of the second system).


When two qubits are entangled in a state such as $|\phi^+\rangle$, the entanglement implies a strong correlation between their states. The $|\phi^+\rangle$ Bell state is given by:

\[ |\phi^+\rangle = \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle) \]

In this state, if Alice and Bob each have one qubit, and they are far apart, their joint state is described as being either both in $|0\rangle$ or both in $|1\rangle$, with equal probability.

Now, let's consider what happens when Alice applies a NOT operation (Pauli-X gate) to her qubit. The NOT operation flips the state of a qubit, changing $|0\rangle$ to $|1\rangle$ and $|1\rangle$ to $|0\rangle$. 

Applying the NOT operation on Alice's qubit would transform the joint state as follows:

1. The original state is $|\phi^+\rangle = \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle)$.

2. Alice applies the NOT operation to her qubit:
   - $|0\rangle \rightarrow |1\rangle$
   - $|1\rangle \rightarrow |0\rangle$

3. Applying the NOT operation on Alice's qubit modifies the joint state:
   \[
   (X \otimes I) |\phi^+\rangle = (X \otimes I) \left( \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle) \right)
   \]
   - $X|0\rangle = |1\rangle$
   - $X|1\rangle = |0\rangle$

   Therefore, applying the NOT operation on Alice's qubit changes the state to:
   \[
   \frac{1}{\sqrt{2}} (|10\rangle + |01\rangle)
   \]

This new state, $\frac{1}{\sqrt{2}} (|10\rangle + |01\rangle)$, is known as the $|\psi^+\rangle$ Bell state.

#### Effect on Bob's Qubit

Bob's qubit is now part of a new entangled state $|\psi^+\rangle$. If Bob measures his qubit, he will still find it to be perfectly correlated with Alice's qubit, but now in the opposite way compared to the original state:

- If Alice's qubit is measured and found to be $|1\rangle$, Bob's qubit will be $|0\rangle$.
- If Alice's qubit is measured and found to be $|0\rangle$, Bob's qubit will be $|1\rangle$.

#### Summary

When Alice applies the NOT operation on her qubit, the overall entangled state of the system changes from $|\phi^+\rangle$ to $|\psi^+\rangle$. This means that the correlation between Alice's and Bob's qubits changes, but no instantaneous information is transferred between Alice and Bob. Bob's qubit state is affected in the sense that the joint entangled state is different, but Alice's local operation does not send any information to Bob faster than the speed of light. The entangled nature of their qubits ensures that any measurement they perform will still show correlated results appropriate to the new entangled state.



>***Note*** The property of changing probabilities in one part of an entangled(or correlated) system affecting another part due to quantum entanglement is unique to quantum mechanics and does not have a direct analog in classical, non-quantum correlated systems. So if there are two classical bits that are correlated and we apply some operation on the first classical bit, then that doesn't change the probability outcome of the other classical bit. But in case of quantum bit(qbit) applying some operation on the first qbit will change the probability outcome of the second qbit.