# Quantum Information(Single System)
In this blog we are going to explore about the Quantum Information.

### What is the quantom information and quantum system?

If we use the rules of classical physics to describe and process the information, then we call that the classical information. If we use the rules of quantum physics to describe and process the information, then we call that the quantum information. In the realm of quantum physics things doesn't follow the rules of classical physics. If we want to describe the state of a quantum system, then we need to understand the quantum informatiom(e.g electrons, photons, atoms etc.). The system that is described by the rules of quantum mechanics is called a quantum system.

### What is a quantum state?

- So when we analyse the quantum system we will come to see that the quantum systems are just like the classical systems. It can be in one of the possible classical states. But the property that differentiates the quantum system is that it can also be in one of the possible quantum states. Quantum mechanics allows the quantum system to be in multiple states at the same time. This property of the quantum system is called qunatum superposition. This particular property of the quantum system is one of the reasons why quantum computer are expected to be more efficient than classical computers(There are some other properties like entanglement and interference). 

- So this means that we can't just use the ideas from classical systems to describe the quantum system. Since quantum systems can be in multiple states at the same time, there is some probability value associated with each state of the quantum system.

### We might think that can't we use the probabilistics computation model to represent these quantum systems?

- Though the quantum mechanics indirectly associates the probability to each state of the quantum system, We can't use the probabilistic computation model for quantum systems. Remember that probabilistic systems associates some probability(possitive real number between 0 and 1) with each classical state of the system. Since the probability associated with each state of the system can be only a possitive real number, they should add upto 1 to be a valid probabilistic state vector. But properties of quantum system allows us to associate some complex number amplitude with each state of the quantum system. That's why we can't use the probabilistic computation model to represent quantum systems.

- But the quantum systems will allow the complex numbers amplitude for each possible state of the system.

### Why does the quantum system allow complex number amplitude?

The quantum systems can be in multiple states at the same time, but that does not mean that it can directly associates probability with each state of the system. Rather it associates some complex number amplitude with each state of the system. Upon measuring the quantum systems these amplitude values represent the probability outcome associated with each state of the system. We will soon see that we can use the absolute values of these complex number to find the probability associated with each state of the system. 

The physical properties of quantum system such as interference allow these multiple quantum states to interfere with each other to add-up or cancel-out each other. If amplitudes corresponds to particular state adds-up, then the probability associated with that state will increase and conversly if amplitudes cancel-out each other, then the probability value reduces. Because of this reason we can't directly use the possitive real number but complex numbers to represent these amplitude values. 

> Side Note:\
> If you are someone who remember about the double slit experiement from high school, then you can understand this interference better. In double slit experiement we send light(photons) through two very closly seperated slits. in the other side of the slits we have some screen kind of setting which can measure the photons. We will see dark and bright patterns of light due to interference of photons. The dark spots corresponds to negative interference and bright spots correspond to possitive interference. This double slit experiement will also show the superposition property of the photons. Even if you send a single photon at a time, this interference pattern will show up. This means each photon interfere with itself due to the superposition property of a the quantum system. When only single slit is open this pattern emerges beacause there is only single path for photon to follow, but when two slits are open, that allows photon to travel in both path simultaneously and create interference with itself.(These interference properties are due to the wave nature of these photons. Quantum systems like photonos, electors sometimes act like wave and sometimes act like particles. This is called the famous dual-nature of a quantum system).


- One common example of quantum system is a qubit. This is analogous term to the bit in the classical computers for quantum computers. 

### What is a qubit?

We know that a bit is a most common way of describing and processing the information about the classical system state mathematically in digital computers. Similarly qubit is a common way of describing and processing the information about some quantum system(such as quantum computers) in a quantum computer. Here the quantum information describes the state of a quantum system at any moment of time.

Similar to the bit the qubit is also having finite and non-emtpy set of classical states {0, 1}. Apart from this qubit can also be in any one of the possible quantum states.

### How do we represent a qubit mathematically?

Similar to a classical bit we will represent a qubit using a column vector. But unlike deterministic or probabilistic states, the qunatum state vector can have a complex number entries. (Note that since we allow complex numbers in the quantum state vector, it can also have negative real number in any entry. This won't be a problem because of the way we compute the probability associated with each quantum state of the system from the quantum state vector).

* Just making this small change in the state vector is enough to bring us from the classical world to the quantum world. In general the following way can be used reresent a state of any quantum system.

$$ 
\begin{equation}\tag{Ex-1}
v = \begin{pmatrix}
\alpha _1 \\ . \\ . \\ . \\ \alpha _n 
\end{pmatrix} 
\end{equation}
$$

* Still the quantun system will have n possible classical states. Other than that it can be in any one of the possible quantum states. Keep in mind that there are some conditions that should be satified by a column vector to be a valid quantum state vector.


$$ 
\begin{equation}\tag{1}
Euclidean \; norm \; ||v|| = \sqrt{\sum_{k=1}^n (\alpha _k)^2} 
\end{equation}
$$

> **Rules: quantum state vector** \
>Two important rules about quantum states vector is that 
> * The entries should be a complex number. 
> * Euclidean norm of the quantum state vector should be 1(Or we can say that the sum of absolute values(of each entry) squared of quantum state vector should be equal to 1. Remember that the Euclidean norm just applies square root operation on top of it). We use the notation `||a||` to represent Euclidean norm of the vector $|a\rangle$. To learn about Euclidean norm see the notes section.
>
> This vector with the above mentioned properties is called a unit vector.


In the given below `Ex-2`, we have quantum state vectors with n=2(which means there are two possible classical states for that quantum system). The first two listed are the two possible classical states which we can also consider a quantum state(This is simply because their entries happen to have complex numbers with imaginary part 0). 

The two vectors $|+\rangle$ and $|-\rangle$ are some of the commonly used quantum states. The vector $|\psi\rangle$ is just a random quantum state which doesn't have any special meaning. We will use the symbol $\psi$ for representing an arbitrary quantum state.

$$ 
\begin{equation}\tag{Ex-2}

|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} 
\;\;\;
|1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}
 \;\;\;
|+\rangle = \begin{pmatrix} \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} \end{pmatrix} 
\;\;\;
|-\rangle = \begin{pmatrix} \frac{1}{\sqrt{2}} \\ -\frac{1}{\sqrt{2}} \end{pmatrix}

\end{equation}
$$

$$
|\psi\rangle = \begin{pmatrix} \frac{1+2i}{3} \\ \frac{2}{3} \end{pmatrix}
$$


### What is special about $|+\rangle$ and $|-\rangle$?
The $|+\rangle$ and $|-\rangle$ are special in the way that If we find the absolute value of each entry of the these vector, then both will give equal probabilities for being a classical state $|0\rangle$ and $|1\rangle$. The following eqution reprsents this concept of equal probability in a more formal way using a dirac notation to represent a $|+\rangle$ and $|-\rangle$ states.

$$
|+\rangle = 
\frac{1}{\sqrt{2}}|0\rangle +  
\frac{1}{\sqrt{2}}|1\rangle
 \; \;  \; \;
|-\rangle = 
\frac{1}{\sqrt{2}}|0\rangle -  
\frac{1}{\sqrt{2}}|1\rangle
$$

### How can we describe the superposition using quantum state vector?

Remember that still the two vectors $|0\rangle$ and $|1\rangle$ are the standard basis for quantum system also. So this means any quantum state can be written as a linear combination of these two standard basis vectors. This linear combination is called 'superposition' in quantum world. That means any quantum state can be written as the superposition(or linear combination) of vectors from the basis set(which usually is the standard basis). 

- That means that, If the quantum system is in the $|+\rangle$ state, then that means the system is in both $|0\rangle$ and $|1\rangle$ states with equal probability.

In the above equations we are writing a quantum states $|+\rangle$ and $|-\rangle$ as a linear combination of basis vectors. Also if you notice that both these states only differ by a sign of a imaginary part(or can say that only differ by phase not by the amplitude). There is a way to differentiate these two quantum states by applying some operations on them. We will see more about these operations on a quantum system in upcoming sections.

> Notice that all the five of these quantum states have a Euclidean norm of 1(then only we can say that it is a valid quantum state).
> $$|| |0\rangle || = || |1\rangle || = || |+\rangle || = || |-\rangle || = || |\psi\rangle || = 1$$
>I will just show for one quantum state how we can compute the Euclidean norm.
>$$ || |\psi\rangle || = 
\sqrt{
    \left|\frac{1+2i}{3} \right|^2 + 
    \left| \frac{2}{3} \right|^2
} = 1 $$

### How can we get the probability associated with each classical state of a quantum system?

We already know that the absolute value of particular entry of a quantum state vector is a probability of outcome of the classical state which corresponds to the position of that particular entry. For example lets take the $|+\rangle$ or $|-\rangle$ state, we can calculate the probability associated with each of the classical states for both of these states as follows.

$$
Probability\ of\ being\ |0\rangle 
= \left| \frac{1}{\sqrt{2}} \right|^2
= \frac{1}{2} \\

Probability\ of\ being\ |1\rangle 
= \left| \frac{1}{\sqrt{2}} \right|^2 
= \left| -\frac{1}{\sqrt{2}} \right|^2
= \frac{1}{2}
$$ 

As we have previously explained both these states have the same probability associated with both of it's classical states. When we measure these states we get the results $|0\rangle$ and $|1\rangle$ with the equal probability of $\frac{1}{2}$

>where the absolute value of complex number is $|a+bi| = \sqrt{a^2 + b^2} $

### How can we represent a quantum state vector with more than two possible states?

In the classical information blog we have seen that we can represent not only a binary system but also any classical system can be represented by a state vector. Similar idea works for a quantum system also. We can represent a system with any number of classical states using a quantum state vector. 

But we can't say all of these representation will make some practical sense. Just for an example, assume that the fan is having a classical states set:  Σ = {HIGH, MEDIUM, LOW, OFF}. The quantum state of the fan can be represented as follow(even though associating quantum state with fan doesn't make any sense):

$$ 
\begin{equation}\tag{Ex-3}

|\psi\rangle 
=  \begin{pmatrix}  \frac{1}{2} \\  0  \\  -\frac{i}{2}  \\  \frac{1}{\sqrt{2}}  \end{pmatrix} 
=  \frac{1}{2} |HIGH\rangle - \frac{i}{2} |LOW\rangle +  \frac{1}{\sqrt{2}} |OFF\rangle 

\end{equation}
$$

Here we have represented system with four classical states. We do this to make a point that we can represent a system with any number of classical states as a quantum state vector(in fact we can do that for classical state vector also).

One more thing that we notice here is that when we reprsent a system with many number classical states the vector representation becomes clumsy. That's the reason we have to appriciate the Dirac notation. Dirac notation allows us to represent a state of a system with any number of classical states in a neat and readable way without any ambiguity. 

We can do that by writing a quantum state vector as a linear combination of dirac notation of the standard basis vectors. 
Remember that once we specify the order of the classical states then the dirac notation implicitly follows that.

## Measurement of quantum system

### What do we mean by measuring a quantum state of a qubit?

Without the action of measuring a quantum system we couldn't know the state of the quantum system with certainty. The action of measuring will reveal the state of the quantum system. Without measurement there is some probability associated with each classical state of the system(This idea can be generalized to more than just a classical states set. We will learn more about that when we learn about projective measurements in future blogs). As soon as we measure the system it will collapse into one of the possible classical states. But the measured result state that we get will depend on the probability associated with that outcome.

The simple way of measurement is called the standard basis measurement where results can be one of the possible classical states. Later we will see more general notion of the measurement. The action of measurement itself is a kind of operation that changes our knowledge about the system. As soon as we measure the system the state of the system goes from a particular quantum state to some classical state(We will see about more general notion of operation in the next section).  

### What is a standard basis measurement?

The standard basis measurement links the absolute value squared of each entry of a quantum state vector to the probability that we will get specific calssical state as an outcome. We can get the probability associated with specific classical state by calculating the absolute value of the entry of the quantum state vector that corresponds to it. This is called Born rule of quantum mechanics. Take the following arbitrary example of qubit,

$$ 
|\psi\rangle = \sqrt{\frac{3}{4}}|0\rangle + i\sqrt{\frac{1}{4}}|1\rangle
= \begin{pmatrix} \sqrt{\frac{3}{4}} \\ i\sqrt{\frac{1}{4}} \end{pmatrix}
$$

Here the probability associated with classical states $|0\rangle$ and $|1\rangle$ are.
$$
Probability\ of\ getting\ |0\rangle 
= \left| \sqrt{\frac{3}{4}} \right|^2 
= \frac{3}{4} \\

Probability\ of\ being\ |1\rangle 
= \left| i\sqrt{\frac{1}{4}} \right|^2
= \frac{1}{4}
$$ 


#### What does the probability associated with classical state mean?

If we measure the quantum system, then we won't always get a same result on each measurement. But rather we may get different classical states as an outcome for different measurements. These results will be based on the probability associated with each classical state of the quantum state vector. 

* We have seen previously that both $|+\rangle$ or $|-\rangle$ quantum states have the $Pr(outcome = |0\rangle) =  \frac{1}{2}$ and $Pr(outcome = |1\rangle) =  \frac{1}{2}$. So when you try to measure these quantum states you will get a classical state $|0\rangle$ as an outcome for half of the times and $|1\rangle$ for other half.(for exmaple if you measure the qubit for 100 times, then 50 times you will get classical state 0 (represented by $|0\rangle$) and 50 times you will get 1. but it could be in some random order.)

>Note: do you remember about the double slit experiement? then the notion of the measurement is similar to how we recorded the dark and light spots on the other side of the double slit. Thought it will be done in a more systematic way to make it less error prone and more efficient.


## Operation and Unitary operation?

### How does the operation on the quantum system differs from a classical system?

Simialer to the deterministic and probabilistic operations on the classical system. We can apply some operations on the quantum system. These operations will change the state of the system from one quantum state to another quantum state.(Sometimes the operation on a quantum system may change the system to a classical state with some probability. The action of measuring itself is a one of that kind which is called standard basis measurement).

The notion of operation is very important because the kind of operation that we can implement using practical hardwares will determine the applications of the quantum systems. Also since quantum systems behaves differently than the classical systems based on rules of the quantum physics, this allows us to apply different kind of operations on a quantum system then a classical system. If we can use some of these operations for our advantage we can make the computation more efficient than our classical system. The operations that we can apply on quantum systems are called unitary operations.

- Just to give you an idea, in a classical computer we have AND, OR, NOT operations using which we can implement all kind of mathematical operation that we use in our computers. These operations will have some fundamental speed limit in the hardware level, so we might not be able to solve some complex problems(like prime factorization) just using these operation. Suppose some operation in a quantum computer can implement a prime factorization more efficiently than these classical operations, then we can use quantum computers to solve those computational problems.

### What exactly is a unitary operation ?

Similar to classical information we can represent a operation on a quantum system using a matrix. More specifically the operations on a quantum system are described by a unitary matrix. That's why this is called a unitary operation. You can see the notes section of this blog to know more about a unitary matrix. These matrices has a particular behaviour that is: After applying these operations the Euclidean norm of the resulting quantum staes doesn't changes. So If we apply a unitary operation to a quantum state vector, then you will get another quntum state vector as an outcome. For example lets take an arbitrary quantum state vector $\psi$, We can multiply this state by some unitary matrix M to get another quantum state vector. formally said $|| M|\psi\rangle || = || |\psi\rangle ||$.

### Examples of unitray operation.
The following are the some of the commonly used unitary opeartions.

#### Pauli Operations:

$$  
\begin{equation}\tag{Ex-4}

I =
\begin{pmatrix} 
1 & 0 \\ 
0 & 1 
\end{pmatrix}, \;\;
\sigma_x = 
\begin{pmatrix} 
0 & 1 \\ 
1 & 0 
\end{pmatrix}, \;\;
\sigma_y = 
\begin{pmatrix} 
0 & -i \\ 
i & 0 
\end{pmatrix}, \;\;
\sigma_z = 
\begin{pmatrix} 
1 & 0 \\ 
0 & -1 
\end{pmatrix} \;\;

\end{equation}
$$

Here `I` is an identity matrix, becuse $I|0\rangle = |0\rangle$ and $I|1\rangle = |1\rangle$. $\sigma_x$ is a bit flip or NOT operation
$\sigma_z$ is called phase flip operation, because $\sigma_z|0\rangle = |0\rangle$ and $\sigma_z|1\rangle = -|1\rangle$. Here the $\Sigma_x$, $\Sigma_y$ and $\Sigma_z$ operations are sometimes referred to as X, Y and Z.

#### Hadamard Operation:

$$ 
\begin{equation}\tag{Ex-5}

H = 
\begin{pmatrix} 
\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ 
\frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} 
\end{pmatrix}

\end{equation}
$$

The matrix H is called self inverse operation because of the fact that $H^2 = I$.

#### Phase Operation:

$$ 
\begin{equation}\tag{Ex-6}
P_\theta = 
\begin{pmatrix} 
1 & 0 \\ 0 & e^{i\theta} 
\end{pmatrix}
\end{equation}
$$

$$ 
S = P_\frac{\pi}{2} = 
\begin{pmatrix} 
1 & 0 \\ 
0 & i 
\end{pmatrix}, \;\;

T = P_\frac{\pi}{4} = 
\begin{pmatrix} 
1 & 0 \\ 
0 & \frac{1+i}{\sqrt{2}} 
\end{pmatrix}
$$

Here $\theta$ can be any real number and $e^{i\theta} = cos(\theta) + i sin(\theta)$. Because of this we can show the equivalities $P_0 = I$ and $P_\pi = \sigma_z $. Here note that $S^2 = \sigma_z$.


All these operations are unitary operations. I think its best to discuss the detailed behaviour of these operations wherever we use them. As an example we will see the Hadamard operation now. You can just do the normal matrix multiplications to apply these operation on a quantum state vector. Previously we have discussed that we can differentiate the $|+\rangle$ and the $|-\rangle$ states using some opeartion. That operation is an Hadamard operation.

### How can we differentiate $|+\rangle$ and $|-\rangle$ states?

$$ 
H|+\rangle = |0\rangle, \ \ 
H|-\rangle = |1\rangle
$$

We know that we can't differentiate the $|+\rangle$ and $|-\rangle$ using the standard basis measurement. But when we apply Hadamard operation to these quantum states we will get differnt outputs as an outcome. So Hadamard operation can differentiate the states $|+\rangle$ and $|-\rangle$. Note the following operations also.

$$
H|0\rangle = |+\rangle, \ \ 
H|1\rangle = |-\rangle
$$

* All these operations are simple matrix multiplications. So try to visualize them as matrix multiplications. For example H is two dimensional matrix and $|0\rangle$ is a column vector. When you multiply them together you will get another column vector as a result which is $|+\rangle$.

* Here note taht applying an Hadamard operation on $|+\rangle$ two times will result in $|+\rangle$ again. So it is equivalent to an identity operation.

### Can we represent multiple unitary operations together as a single matrix?

When we multiply multiple stochastic matrices we got combined stochastic operation, similarly the composition of unitary operations can be applied to a quantum state. For exmaple If you apply H operation then S operation, then again H operation, it can be represented by a matrix `R = HSH`.

$$ 
\begin{equation}\tag{Ex-7}
R = HSH = 
\begin{pmatrix} 
\frac{1+i}{2} & \frac{1-i}{2} \\ 
\frac{1-i}{2} & \frac{1+i}{2}
\end{pmatrix}
\end{equation}
$$

If we compute the square of R, then we will get $R^2 = I$. Becuse $R^2|0\rangle = |0\rangle$ and $R^2|1\rangle = |1\rangle$. So this implies that $R = \sqrt{I}$.

### Can we apply a unitary operation on a quantum system with more than two classical states?

The unitary operations is not restricted to use only with a qubit. The qubit is a simple form of quantum system with just two possible classical states. We can apply unitary operations for a system with more than just two classical states. For example the follwing the matrix is called permutation matrix. This is called a permuation operationb because it will just rearrange the entries of the state vector.

$$ A = 
\begin{pmatrix} 
0 & 1 & 0 \\ 
0 & 0 & 1 \\ 
1 & 0 & 0
\end{pmatrix}
$$

$$ A|0\rangle = |2\rangle, \; A|1\rangle = |0\rangle, \; A|2\rangle = |1\rangle$$
 You can think of $\sigma_x$ operation as a simple permuation operation for a qubit.

The following is the unitary operation for the quantum fourier transform for system with n=4 classical states. We can define quantum fourier transform matrix for any possitive integer n. We will use this operation in future sections.

$$ U = \frac{1}{2} \begin{pmatrix} 1 & 1 & 1 & 1 \\ 1 & i & -1 & -i \\ 1 & -1 & 1 & -1 \\ 1 & -i & -1 & i \end{pmatrix}$$

**Why?**: The way we are going to define multiple systems will require us to have a state vector with more than just two classical states. We will see about these combined systems(combination of simple systems which we have studied in this lesson) in the next blog. Thats why I have shown here the way we can represent an operation on a quantum state vector with three or more classical states. 

### Can we construct unitary operation matrices similar to how we constructed stochastic matrices for probabilistic systems?

For classical systems we have written the probabilistic operation matrix as a linear combination of deterministic operations as long as the resulting matrix is a valid stochastic matrix. Can we do a similar kind of logic for constructing unitary operation matrices from deterministic operations for quatum systems?

In quantum system simple unitary matrices can't be written as linear combination of other unitary matrices(we know that all deterministic operations are unitary) like we did for probabilistic operations. 

However, certain quantum operations (called Kraus operators) allow expressing mixed-state evolutions (quantum channels) as sums of operations applied to density matrices. But don't worry about any of this now, we will explore this when we learn about the density matrix formulation of the quantum systems.


## Notes

### What is a complex number?
Complex numbers are the number which contains real and imaginary part. For example $a+bi$ is a complex number where the number a is the real part and b is the imaginary part. The complex numbers were introduced because we didn't have a proper way of defining the square root of the negative numbers. After the introduction of the notation $ i = \sqrt{-1} $ we can find the square root of imaginary number by using this notation. 

* Mainly introduction of complex number solved the problem of getting solution to the polynomial which doesn't have solution in the real numbers set. For example $ x^2 = -1 $ can have two solutions x= i and x = -i in the complex world with only imaginary part present in both the solutions.

### What is absolute value of a complex number?

The absolute value of a complex number is a square root of the sum of the square of the real and imaginary part of the complex number. Suppose c = a + bi is a complex number, then the following is th absolute value of the complex number.

$$ |c| = \sqrt{a^2 + b^2} $$

### What is 1-norm or L-1 norm?
It is the sum of absolute values of the elements of the column vector.

$$ v = \begin{pmatrix} v_1 & v_2 & . & . & . & v_n\end{pmatrix} $$

Then the 1-norm is 

$$ |v| = |v_1| + |v_2| + ... + |v_n|$$
 

### What is Euclidean norm or 2-norm or L-2 norm? 
It is the square root of the sum of the absolute value squared of the elements of the column vector. This Euclidean norm give the shortest distance from the orgin for any vector v.

Then the 2-norm is 

$$ ||v|| = \sqrt{|v_1|^2 + |v_2|^2 + ... + |v_n|^2}$$
 

### What is a Unit vector?
Unit vectors will have exact distance of 1 from the origin. This means they will have Euclidean norm 1. These unit vectors represent the direction of a vector. For any vector v we can compute the unit vector by using the following formula. The unit vector is represented by a notation $\hat{v}$. Remember that we have to divide a vector by a Euclidean norm.
  
$$ \hat{v} = \frac{v}{||v||}$$

### what is Unitary Matrix?
* Unitary matrix is a square matrix with complex numbers as its entries, where the inverse of the unitary matrix is equal to the complex conjugate transpose of a matrix. When you multiply a unitary matix with its conjugate transpose matrix you will get a identity matrix as a result(what you would have expected when multiplying a matrix with its inverse).

* The matrix A with complex number entries is said to be unitary matrix if the complex conjugate transpose of a matrix A is same as inverse of a matrix A. This can be formulated as given below.

 $$ AA^† = A^† A = I $$
 Here $ A^† $ is spelled as `A dagger` and is the notation for complex conjugate transpose of a matrix. The I is the notation for an identity matrix.

 ### What is Conjugate Transpose? 

Conjugate transpose of a matrix is a normal transpose operation on a matrix together with computing the complex conjugate of each complex number entry of the matrix.
