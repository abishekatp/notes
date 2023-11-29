# Classical Information(Single System)

## Classical information

### What is the classical information?

Classical information is a knowledge about the state of the classical system. These states are called classical states. 

### What is the calssical system?

Any day to day objects you see or interact with can be considered as a classical systems for example Fan, Television, Car, etc. More complex things like Planes, Computers, Rockets can also be considered as classical system.

### What is the clasical states of the classical system?

-  Consideer a Fan as a classical system which is in one of the following states at any moment of time: $\Sigma$ = {HIGH, MEDIUM, LOW and OFF}. 

- The torch light is a classical system which can be in one of the following states: $\Sigma$ = {OFF, ON}. 

- Our digital systems(like computers, smart watches and many more) are very similar to this torch light analogy. In a digital computer the information is stored and processed in the form of Bits which can be either in a state 0 or a state 1. We use the symbol $\Sigma$ to represent the set of possible states.

### what is classical state set? 

- The classical state set is the set of possible states of the classical system. The classical state can be represented by a non-empty finite set. Some systems can have infinitely many classical states but we will focus on system with finite number of classical states now.

> Note that the term classical is used here to specifically differentiate the information that can be represented by a quantum systems.

## Bit

### What is a bit?

The term bit is a short form of Binary Digit. A single bit can represent some information using two classical states $\Sigma = \{ 0 , 1 \}$.

### Where we use bit?

The term bit is used to represent a fundamental way we define and process the information in computers and many other digital systems. All the numbers, charactors and everything you see or process in the computer is represented by bits under the wood. 

### Why do we use binary system(or bit)?

All the digital devices we see today are mainly made up of transistors and logical gates. These components can efficiently store and process the electrical signals of HIGH(like 5 voltage) and LOW(like 0 voltage) voltages. So the intutive way of representing these information mathematically is using binary digits(or numbers).

## State of the Classical System

### How can we represent the state of the classical system mathematically?

We can think of some different ways to represent classical states of a classical system. For example each state of a system can be represented by some characters like {a,b,c,...}. We may try to represent each character by numbers like {1,2,3,...}. But will these approaches be helpful for mathematically processing classical information. Not every way we think of can be a optimal or scalable answer to this problem.

One good solution we have found for this problem is representing each state of the system by a vector. A vector is a matrix with only one dimension.There are two kinds of vectors namely column vector(matrix with a single column) and row vector(matrix with a single row).

### What is a state vector?

When column or row vector is used to represent the classical state of the system then it is called state vector. More commonly we use column vector to represent the state. 

### How column vector represents the state?

If particular system has n classical states then we will create a column vector of length n to represent the state of that system. The i'th state s(i) of the system will have 1 in the i'th index of the column vector and 0 in all the remaining indices where 1 <= i <= n.

### Why do we need row vector then?

One fundamental operation that we can apply on matrix is matrix transformation. When we discuss different properties of the classical system there will be a situation where we need to apply transformation to the column vector, during that time we will need row vector to do the computation. Also remember that the row vector is a equivalent way of representing a state of the system.

### How do we differentiate row and column vector?

When we label(giving some name) the row or column vector we use the dirac notation to differentiate them. 

### What is a dirac notation of column vector?

If you take a torch light example it can be in one of two states OFF or ON. The column vector of this system can be represented in a following way.

$$ |OFF\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |ON\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$

This particular notation is called `ket`. Here the **OFF** is represented by a first position of a column vector and the state **ON** is  by a second position of a vector.

### What is a dirac notation of a row vector?
 
The state of the same torch light example can be represented by a row vector in a following way. This notation is called `bra`.

$$ \langle OFF| = \begin{pmatrix} 0 & 1\end{pmatrix} $$
$$ \langle ON| = \begin{pmatrix} 1 & 0\end{pmatrix} $$


### How do we represent a bit using dirac notation?

The following column vectors are used to represent a bit. the first index of the column vector corresponds to state 0 and secons corresponds to state 1.

$$ |0\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |1\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$

These two states are called deterministic states of the binary system. These two state vectors are specifically called standard basis vectors of dimension 2. 

### What is a deterministic state?

When a state vector has a value 1 in exactly one position of the vector and 0 in all the remaining positions then it is called a deterministic state. If a state vector of the system is deterministic, then it will define the classical state of the system either as 0 or 1(in case of binary system) without any ambiguity.

There is also a different kind of state vector called probabilistic state vector.

### What is a probabilistic state vector or probability vector?

In the probability vector, entries of the vector will be a real numbers with a constraint that the sum of the entries should add up to 1.

### Why the sum of the entries of the probability should be 1?

In a probability vector each entry of the vector corresponds to a probability associated with the state that corresponds to that particular entry(or index) of the vector. So to satisfy the condition that the total probability of the system should be 1, the sum should be 1.

### Why the vectors $|0\rangle$ and $|1\rangle$ are called standard basis vectors?

Using these two vectors $|0\rangle$ and $|1\rangle$ we can represent any deterministic or probabilistic state of the classical systems. The above is true because we can write any other vector of dimension two as a linear combination of these two vectors. This idea can be generalized to any classical system with n classical states.



## Probability vector

### Why do we need a probability vector?

We don't always know the current state of the clssical system for sure. Sometime the state of the classical system can be unknown. If your friend is holding a torch light inside a room. You won't know the state of the torch light untill you go and see inside the room. Untill then the probabilty of torch being ON will be 1/2 and being OFF can be 1/2. Then you can represent the state of the torch light using following column vector. 

$$ 
|state\rangle = 
\begin{pmatrix} \frac{1}{2} \\ \frac{1}{2} \end{pmatrix} = 
\frac{1}{2} |OFF\rangle + 
\frac{1}{2} |ON\rangle
$$

This is because we don't always know the state of some classical system with confident. We can represent these uncertainty using a probabilistic vectors. Here we associate some probability for system being in each of the classical state. For example in the above state 

$$ 
Pr(light=OFF)= \frac{1}{2} \;\; and \;\;  
Pr(light=ON) = \frac{1}{2} 
$$

Here you can also see that some probabilistic state of the classical system is represented by a linear combination of column vectors from the standard basis set. This is what I was trying to explain about standard basis vectors previously.

This way of thinking is very useful, because in real world there can be hardware or environmental condition which will change the state of the system with some probability. For example take a same example as your friend holding torch light inside room. But now you know some extra information that today there is power shortage in that area and it is dark outside. Now the probability of torch light being ON will be increased.

The similar kind of thing can happen in our computers also. So when we represent a classical information using state $ |state\rangle $ it can have some higer probability of being 0 than 1 or vice versa. When we introduce probabilic state into our classical information we can easily handle these kind of situations.

> **Note: Probability Vector** \
One important thing about representing a probabilistic state by a column vector is: 
> * All the entries of the column vector should contain non-negative real numbers
> * when the sum of entries in the column vector should be 1. This is because the total probability of a system can be at most one. 
>
>If the particular vector obeys the above rules then we call that as probability vector.



## What do we mean by measuring the state of a classical single system?

In previous section we have seen that we don't know the actual state of a torch light until we go inside room and see it's status. This action of checking the state of a system is called measuring the state of the system formally. Untill we mesure the state of the system, the state can be represented by some probabilistic vector based on our knowledge about the system.

As soon as we go and measure the state of the system the state will go from a probabilistic state to one of the possible deterministic states. As soon as we go inside the room and check the torch light, it will be either **OFF or ON**.

## What is matrix operation on classical system and why do we use it?

So we have seen what is classical information and we can represent them either as deterministic vector or probabilistic vector. We also discussed that the state of the system might change over time. How can the state of the system will change. It might be because of the reason that someone interacted with the system.

In our torch light example it might be you friend who is switching OFF or ON the torch light. This particular interaction with a system can be represented by a mathematical operations formally. There can be two kind of operations namely deterministic operation or probabilistic operation. We will see them one by one now.

Before we get into that we have to understand that another way of representing operation mathematically is using funcions. Functions will take some input and apply some operations on the input and produce an output. Here we are going to represent these operations using two dimensional matrices. 

When we multiply some matrix with a particular state vector it is kind of applying some logic on each individual elements of a vector based on some mathematical function. So in a broad thinking these matrices are representing some operation of a particular function.

### What is deterministic operation?

As name suggests these operations create a deterministic changes in the system. For example the action of switching on the torch light is a deterministic operation which changes the state of a torch light from OFF to the state ON. 

Suppose there is single push button in the torch light. If you click on the button, it will switch on the light. If you click on it again, then it will switch off the light. This is very common operation on classical binary system called `NOT` operation formally. When you apply this operation it will change current state to the other possible state in a set. If current state is 0 then it will become 1 and vice versa. We can repersent this operation using following matrix.

$$ NOT = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} $$

$$ 
NOT|0\rangle = 
\begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} 
\begin{pmatrix} 1 \\ 0 \end{pmatrix} = 
\begin{pmatrix} 0 \\ 1 \end{pmatrix}
$$

$$ 
NOT|1\rangle = \begin{pmatrix} 0 & 1 \\ 1 & 0 \end{pmatrix} 
\begin{pmatrix} 0 \\ 1 \end{pmatrix} =
\begin{pmatrix} 1 \\ 0 \end{pmatrix}
$$

Here $ NOT|0\rangle $ is matrix multiplication NOT applied on a column vector for state 0 of a binary system.

#### How can we compute some matrix M that is equivalent of applying function f?

We have seen that the matrices in the matrix operation represent some mathematical function applied on some classical state. How can we find this matrix when we know the kind of function we want to apply. $ |f(a)\rangle$ is a function applied to some vector a, where the fucntion is `f:Σ->Σ`.

We have seen about `ketbra` operation in dirac notation section. When we know what is the output for each input, then we can apply the `ketbra` opertion for each of these output(as column vector) and input(as a row vector) vectors. After that if we sum all the resultant 2 dimensional matrices we will get a matrix M that represent the input output relationship that we need.

$$ M = \sum_{a ∈ \Sigma} |f(a)\rangle \langle a|$$


For example the following equations compute the matrix for NOT operation on the torch light that we have discussed previously. Here $\Sigma$ = {OFF, ON} or you can think of equivalent binary operation. Our function will be f(ON) = OFF and f(OFF) = ON.


$$ 
NOT = \sum_{a ∈ \Sigma} |f(a)\rangle \langle a| = 
|ON\rangle \langle OFF| + 
|OFF\rangle \langle ON| = 
\begin{pmatrix} 0 & 1 \\ 1  & 0 \end{pmatrix}
$$


### What is probabilistic operation?

Not all operations are deterministic. Some of the operation can change the state of the classical system in a probabilistic way. For example If you take a torch light example. Think of this torch light as a smart torch light. It will change the brightness of the light based on the darkness of the enviroment using some sensors.

So to make this idea simple we will say the torch light is represented by two classical system. One representing status of torch light `Σ = {OFF, ON}` and another single system representing the brightness of torch light `Σ1 = {LOW, HIGH}`. Now this `Σ1` depends on the environmental conditions. So the operations applied on this new system $\Sigma 1$ will be probabilistic. 

$$ |LOW\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |HIGH\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$

> Don't think about the relationships between $\Sigma$ and $\Sigma 1$. We will see about their relationship and how we can represent them together in a blog about multiple systems. As of now consider $\Sigma$ and $\Sigma 1$ are two separate individual classical systems.

When probability of darkness is larger, then the probability of state HIGH will be higher. For example $ Pr(HIGH) = \frac{3}{4} $ and $ Pr(LOW) = \frac{1}{4} $.

So now the current classical state is LOW means it is flipped to the state HIGH with probability $ \frac{3}{4} $. We can represent this operation using the folowing matrix. We just assume that if current classical state is HIGH, then the result will be Pr(HIGH) = 1 and Pr(LOW)=0.

$$ \begin{pmatrix} 3/4 & 1 \\ 1/4 & 0 \end{pmatrix} $$

> **Note: Stochastic Matrix**\
Similar rules as we discussed in the probabilistic vector applies to probabilistic operations also. 
> * The sum of values in each column of the matrix should add up to 1. 
> * Each entry of the matrix should be non-negative real numbers.
>
>`Stochastic matrix`: This probability matrix that obeys the above mentioned rules is called stochastic matrix. These matrices will always map the probability vector to another probability vector as an output.

Another way of thinking about these probability matris is such that they are multiple determinist matrix operation each appliede with some probability. So we can always represent the probabilist operation as a linear combination of deterministic operation with some probability associated with each deterministic operation. For example the previous probabilistic operation can be written as linear combination of following deterministic operations.

$$ 
\begin{pmatrix} 3/4 & 1 \\ 1/4 & 0 \end{pmatrix} =  
\frac{3}{4}\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} +
\frac{1}{4}\begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix} +
\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}
$$

### composition of matrix operations(Matrix Associative property)

All the properties of matrix multiplication is valid here. Assume that $M_1$ and $M_2$ are the matrix operations applied on some state vector. The fact that matrix multiplication is associative and but not cummutative results in following equivalities and inequivalities.

$$ (M_1 M_2)a = M_1 (M_2a)$$

because matrix multiplication is associative. So first applying $M_2$ opeation then applying $M_1$ operation is same as applying the result matrix matrix multiplication $M_1 M_2$ to the state a.

$$ (M_1 M_2)a \neq (M_2 M_1)a$$

because matrix multiplication is not cummutative.


## Notes

### What is Orthonormal Basis & Standard Basis?

A subset {v1, v2,...,v(k)} of the Vector Space V with a inner product <,> is callled orthonormal if < v(i), v(j) > = 0 for any i!=j and 1<= i,j <= k. This means the vectors in the subset are mutually perpendicular to each other and each vector has length 1 ( means < v(i), v(i) > = 1).

An onthonormal set should contain only linearly independent vectors so that it can be a vector basis for a vector space it spans. Such a basis is called orthonormal basis. 

Here linearly independent means no linear combination of vectors v(j)'s in the basis should form another vector v(i) in the same basis set where i!=j. The vector basis spans a vector space means we can represent any vector in the vector space as a linear combination of vectors in the basis set.

Common example of a orthonormal basis is for standard basis e(i) for the Eucliden Vector Space(**R**^n) where e(i) is the vector with 1 at the i'th position and 0 in the all other positions. Here n is the dimension of the vector space and i = 1,2,...,n. Here the notation **R** tries to explain that each vector in this vector space is a n-tuple of real numbers.

**Standard Basis**: Standard basis is a special case of Orthonormal basis where each vector in the basis has 1 in exactly one position and 0 in all other positions.

