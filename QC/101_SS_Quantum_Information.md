# Quantum Information(Single System)
In this blog we are going to explore about the Quantum Information. This is about how can we mathematically define and compute the quantum states of the single quantum system. Similary to Clssical Information which we have seen in the previous blog we are going to focus on a single quantum system in isolation. We will see how the quantum states can be represented by qbit and How can we apply some operations on that qbit. Similar to as we have seen the Bit as an individual classical system, we will see a Qbit as an individual quantum system.

> **Important: Here after in most of the places wherever it is possible, We will directly use Dirac notations for all the mathematical operations instead of explicitly doing things with the matrices.**


## What is Quantom Information?

* Similar to how classical information of digital systems is represented by a Bit, The quantum information is represented by a Qbit in the quantum systems(such as quantum computers). The Quantum information means the state of a quantum system(for e.g Qbit) at any moment of time. 

* **Qbit**: Similar to the bit the qbit is also having finite and non-emtpy set of classical states {0, 1}. Apart from this qbit can also be in one of the many quantum states. In the next section we will see some of the possible states that qbit can be.

## How do we represent a qbit?

* Similar to the classical bit we will represent a qbit using a column vector. But unlike deterministic or probabilistic states, the qunatum state vector can have a complex number entries also. (Note that since we allow complex numbers in the quantum state vector, it can also have negative real number in the entries)

* Just making this small change in the state vector is enough to bring us from a classical world to a quantum world. In the following way we can reresent a state of the any quantum system in general.

$$ v = \begin{pmatrix} \alpha _1 \\ . \\ . \\ . \\ \alpha _n \end{pmatrix} $$

* Here the quantun system will have n possible classical states. Other than that it can be in any one of the many possible quantum states.


$$ Euclidean \; norm \; ||v|| = \sqrt{\sum_{k=1}^n (\alpha _k)^2} $$

> **Rules: Two important rules about quantum states vector is that their entries should be a complex number and Euclidean norm of the quantum state vector should be 1(Or we can say the sum of absolute values squared of each entry of quantum state vector should be equal to 1. Remember that the Euclidean norm just applies square root operation on top of it).**



* In the given below examples, we have quantum state vectors with n=2(which means there are two possible classical states for that quantum system). The first two listed are the two possible classical states which we can also consider a quantum state because their entries imaginary parts are just happened to be 0. Still these two vectors are the standard basis for quantum state vectors also. So this means any quantum state can be written as linear combination of the two standard basis vectors. 

* This linear combination is called 'superposition' in quantum world. That means any quantum state can be written as superposition of it's classical states(which usually is the standard basis)

* The second two are the some of the commonly used quantum states. The last one is just a random quantum state which doesn't have any special meaning. We will use the symbol $\psi$ for representing any arbitrary quantum state.

$$ |0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix} 
\;\;\;
|1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}
 \;\;\;
|+\rangle = \begin{pmatrix} \frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} \end{pmatrix} 
\;\;\;
|-\rangle = \begin{pmatrix} \frac{1}{\sqrt{2}} \\ -\frac{1}{\sqrt{2}} \end{pmatrix}$$

$$
|\psi\rangle = \begin{pmatrix} \frac{1+2i}{3} \\ \frac{2}{3} \end{pmatrix}
$$

* `Superposition or linear combination of standard basis`: The $|+\rangle$ and $|-\rangle$ are special in the way that when we find the absolute value of each entry of the these vector both will give equal probabilities for classical states $|0\rangle$ and $|1\rangle$. The following eqution reprsents this equal probability of classical states in a more systematic way using a dirac notation to represent a $|+\rangle$ state.

$$
|+\rangle = 
\frac{1}{\sqrt{2}}|0\rangle +  
\frac{1}{\sqrt{2}}|1\rangle
 \; \;  \; \;
|-\rangle = 
\frac{1}{\sqrt{2}}|0\rangle -  
\frac{1}{\sqrt{2}}|1\rangle
$$


* In the above equations we writing a quantum state as a linear combination of basis vectors. (note: As we discussed in quantum systems linear combination and superpositon are synonymous to each other). Also if you notice both these states only differ by a sign of a imaginary part. To differentiate then we will use some speacial operations on them. We will see more about operation on quantum system in coming sections.


> Notice that for all the five of these quantum states have a Eucliean norm of 1(then only we can say that it is a valid quantum state). 
> $$|| |0\rangle || = || |1\rangle || = || |+\rangle || = || |-\rangle || = || |\psi\rangle || = 1$$
>I will just show for one quantum state how we can compute the Euclidean norm.
>$$ || |\psi\rangle || = 
\sqrt{
    \left|\frac{1+2i}{3} \right|^2 + 
    \left| \frac{2}{3} \right|^2
} = 1 $$

### What is the difference between Quantum State and Probabilistic State?

* Remember that the absolute value of particular entry of a quantum state vector is a probability of getting the classical state which corresponds to the position of that particular entry. For example in a $|+\rangle $ state we can define the probability for each standard basis vectos: $Pr(result = |1\rangle) = \frac{1}{2}$ and $Pr(result = |0\rangle) = \frac{1}{2}$. 

* If each entry of the quantum state associates some probability value to some classical state, then why do we need a quantum state vector? we can just use the probabilistic state vector to represent a quantum state right? We will soon see that the operations that we can apply on quantum states is not same as that we can apply on probabilistic states.

* You might have already noticed that quantum state vector can also have negative real number as a entry. This is because negative real number is also a valid complex number with imaginary part set to 0. These differences will create new possibilities of the operations that we can apply on the quantum systems(both theoretically and practically).(note: by practically I mean using qunatum physics as the base we can develop circuits which can physically represent these quantum operations similart to AND, OR, and NOT gates in classical world)

### Can we represent quantum state vector for system with more than two states

* In the classical information blog we have seen that we can represent not only a binary system but any classical system can be modeled as a state vector. Similar idealogy works for quantum system. We can represent any system by a quantum state vector. 

* But we can't say all of these representation will make some practical sense. For example the fan is having a classical states set:  Σ = {HIGH, MEDIUM, LOW, OFF}. The quantum state of the fan can be represented as follow(even though quantum state is not used for this):

$$ 
|\psi\rangle 
=  \begin{pmatrix}  \frac{1}{2} \\  0  \\  -\frac{i}{2}  \\  \frac{1}{\sqrt{2}}  \end{pmatrix} 
=  \frac{1}{2} |HIGH\rangle - \frac{i}{2} |LOW\rangle +  \frac{1}{\sqrt{2}} |OFF\rangle 
$$

* Here we have represented system with four classical states. We do this to make a point that we can represent a system with any number of classical states as a quantum state vector(in fact we can do that in classical state vector also).

* One more thing that we can notice here is when we reprsent a system with more classical states the vector representation becomes clumsy. That's the reason we have to appriciate the Dirac notation. Dirac notation allows us to represent a state of a system with any number of classical states in neat and readable way without any ambigous. 

* We can do that by writing a quantum state vector as a linear combination of diracc notation of the standard basis vectors(for exmaple here $|HIGH\rangle$). 

> That is the reason here after we will try to use the dirac notations to represent a quantum state vectors wherever it is possible. One more advantage is each time we don't have to explicitly mention the order of entries in state vector for each classical state.


## What do we mean by measuring a quantum state of a qbit?

* Similar to measuring the classical system, before measuring a quantum system we don't know the state of the quantum system with certainty. The action of measuring will reveal the classical state of the quantum system. So when we measure a quantum system we won't get some quantum state vector as a result. But rather we will get one of the possible classical states as the result.

* The simple way of measurement is standard basis measurement. Later we will see more general notion of the measurement. This measurement itself is a kind of operation which changes system from a particular quantum state to classical state(We will see about more kind of operation in next and future topics).

* Before the action of measuring we don't know for sure the state of a quantum system. But as soon as we measure it, it will collapse to some classical state with some probabilty. After measuring the system can't be in some quantum state. 

#### Standard basis measurement

* The standard basis measurement links the absolute value squared of each entry of a quantum state vector to the probability that we will get specific calssical state as a result. The probability for specific classical state will be get from the entry of the quantum state vector that corresponds to it. This is called Born rule of quantum mechanics.

#### what does the classical state with associated probability mean?

* So when we measure the quantum system we won't always get a same result. But rather we may get different answers for different measurements. But these answers will be based on the probability associated classical states that is represented by the quantum state. 

* $|+\rangle$ or $|-\rangle$ then both of these quantum states has the $Pr(result = |0\rangle) =  \frac{1}{2}$ and $Pr(result = |1\rangle) =  \frac{1}{2}$. So when you try to measure these quantum states you will get a classical state $|0\rangle$ for half of the times and $|1\rangle$ for other time.(for exmaple if you measure the qbit for 100 times, then 50 times you will get classical state 0 (represented by $|0\rangle$) anf 50 times you will get 1. but it will be in some random order.)

* because of this we can't differentiate the $|+\rangle$ and $|-\rangle$ state using standard basis measurement. We will see in future there are some operations on these quantum states that will differentiate them.


## What is a Operation and Unitary operation?

* Simialer to the deterministic and probabilistic operations on the classical system. We can apply some operations on the quantum system. These operations will change the state of system from one quantum state to another quantum state.(Sometimes the operation on a quantum system may change the system to a classical state with some probability. The action of measuring itself is a one of that kind).

* Unitary operations are carried out by a unitary matrices. You can see the notes section of this blog to know more about the unitary matrix. These matrices has some particular behaviour that is: After applying these operations the Euclidean norm of the quantum staes doesn't changes. So when we apply some unitary operation to some quantum state you will get another quntum state as a result. For example the $\psi$ is some quantum state then we can multiply this state by some unitary matrix M to get another quantum state. formally said $|| M|\psi\rangle || = || |\psi\rangle ||$.

### Examples of unitray operation.
The following are the some of the commonly used unitary opeartions.

#### Pauli Operations:

$$  
I =\begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}, \;\;
\sigma_x = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix}, \;\;
\sigma_y = \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix}, \;\;
\sigma_z = \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix}, \;\;
$$
Here `I` is a bit flip or NOT operation. becuse $I|0\rangle = |0\rangle$ and $I|1\rangle = |1\rangle$.

$\sigma_z$ is called phase flip operation, because $\sigma_z|0\rangle = |0\rangle$ and $\sigma_z|1\rangle = -|1\rangle$.

#### Hadamard Operation:

$$ H = 
\begin{pmatrix} 
\frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \\ 
\frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} 
\end{pmatrix}
$$

#### Phase Operation:

$$ P_\theta = 
\begin{pmatrix} 1 & 0 \\ 0 & e^{i\theta} \end{pmatrix}
$$

$$ 
S = P_\frac{\pi}{2} = \begin{pmatrix} 1 & 0 \\ 0 & i \end{pmatrix}, \;\;
T = P_\frac{\pi}{4} = \begin{pmatrix} 1 & 0 \\ 0 & \frac{1+i}{\sqrt{2}} \end{pmatrix}
$$

Here $\theta$ can be any real number and $e^{i\theta} = cos(\theta) + i sin(\theta)$. Because of this we can show the equivalities $P_0 = I$ and $P_\pi = \sigma_z $


All these operations are unitary operations. I think its best to discuss the detailed behaviour of these operation wherever we use them. As an example we will see the Hadamard operation now. You can just do the normal matrix multiplications to get these results.

$$ 
H|0\rangle = |+\rangle, \;
H|1\rangle = |-\rangle, \;
H|+\rangle = |0\rangle, \;
H|-\rangle = |1\rangle
$$

* Here note that previously we discussed that we can't differentiate the $|+\rangle$ and $|-\rangle$ using the standard basis measurement. But when we apply Hadamard operation to those quantum state we will get differnt outputs as a result. So Hadamard operation differentiates the states $|+\rangle$ and $|-\rangle$.

* All these operations are simple matrix multiplications. So try to visualize them as matrix multiplications. For example H is two dimensional matrix and $|0\rangle$ is a column vector. When you multiply them together you will get another column vector as a result which $|+\rangle$.

### Composition of unitary operations(Matrix Associative property)

* Like we did in the classical operations, the composition of unitary operations can be applied to the quantum states. For exmaple If you apply H operation then S operation, then again H operation, it can be represented by a matrix `R = HSH`.

$$ R = HSH = \begin{pmatrix} \frac{1+i}{2} & \frac{1-i}{2} \\ \frac{1-i}{2} & \frac{1+i}{2}\end{pmatrix}$$

* The square of the operation R is kind of suprising one. $R^2 = I$. Becuse $R^2|0\rangle = |1\rangle$ and $R^2|1\rangle = |0\rangle$. So this implies that $R = \sqrt{I}$.

### Can we apply this unitary operation on larger systems?

* These unitary operations are not restricted to use only with qbit. The qbit is a simple form of quantum system with just two possible quantum states. We can apply unitary operations for systems with more classical states also. For example the follwing the matrix is called permutation unitary matrix. This permuation operation will just rearrange the entries of the state vector.

$$ A = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 1 & 0 & 0\end{pmatrix}$$

$$ A|0\rangle = |2\rangle, \; A|1\rangle = |0\rangle, \; A|2\rangle = |1\rangle$$

* You can think of `NOT` operation as simple permuation operation for a qbit.

* The following is the unitary operation for quantum fourier transform for system with n=4 classical states. We can define quantum fourier transform matrix for any possitive integer n. We will use this operation in future sections.

$$ U = \frac{1}{2} \begin{pmatrix} 1 & 1 & 1 & 1 \\ 1 & i & -1 & -i \\ 1 & -1 & 1 & -1 \\ 1 & -i & -1 & i \end{pmatrix}$$

* **Why?**: The way we are going to represent multiple systems will require us to have a state vector which represents more than two possible states for the combined system(combination of single systems which we have studied in this lesson). That why I have shown here the way we can represent quantum vector with more than two classical states. 




## Notes

### What is a complex number?
Complex numbers are the number which contains real and imaginary part. For example a+bi is a complex number where the number a is the real part and b is the imaginary part. The complex numbers was introduced because before this imaginary number we didn't have a proper way of defining the square root of the negative numbers. After the introduction of the notation $ i = \sqrt{-1} $ we can find the square root of imaginary number by using this notation. 

* Mainly introduction of complex number solved the problem of getting solution to the polynomial which doesn't have solution in the real numbers set. For example $ x^2 = -1 $ can have two solutions x= i and x = -i in the complex world with only imaginary part present in both the solutions.

### What is absolute value of complex number?

The absolute value of a complex number is a square root of the sum of the square of the real and imaginary part of the complex number. Suppose c = a + bi then the abosolute values is, the following is th absolute value of the complex number.

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
Unit vectors will have exact distance of 1 from the origin. This means they will have Euclidean norm 1. These unit vectors represent the direction of a vector. For any vector v we can compute the unit vector by using the following formula.
  
$$ \hat{v} = \frac{v}{||v||}$$

### what is Unitary Matrix?
* Unitary matrix is a square matrix with complex numbers as its entries, wehere the inverse of the unitary matrix is equal to the complex conjugate transpose of a matrix. When you multiply a unitary matix with its conjugate transpose matrix you will get a identity matrix as a result(what you would have expected when multiplying a matrix with its inverse).

* The matrix A with complex number entries is said to be unitary matrix if the complex conjugate transpose of a matrix A is same as inverse of a matrix A. This can be formulated as given below.

 $$ AA^† = A^† A = I $$
 Here $ A^† $ is spelled as `A dagger` and is the notation for complex conjugate transpose of a matrix. The I is the notation for identity matrix.

 ### What is Conjugate Transpose? 

Conjugate transpose of a matrix is a normal transpose operation on a matrix together with computing the complex conjugate of each complex number entry of the matrix.
