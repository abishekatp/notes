# Classical Information(Single system)

### What is the classical information?

Classical information is a knowledge about the state of the classical system. These states are called classical states. 

### What is a calssical system?

You can think of a classical system is any day to day objects you see or interact.

- For example fans, torch lights, elevators and etc can be considered as classical systems. Usually these are all simple systems with small set of possible classical states. 

- The things like cars, planes, computers and rockets can also be considered as classical system. These are all complex systems with wide range of classical states. More complex systems like these can be easily represented using multiple systems. 

### What is the clasical state?

Any classical system will be in one of the possible classicle states at any moment of time.

-  Consideer a fan as a classical system which is in one of the following states at any moment of time: {HIGH, MEDIUM, LOW and OFF}. 

- The torch light is a classical system which can be in one of the following states: {OFF, ON}. 

- A bit is a classical system which can be eithe in a state 0 or 1. The complex modern digital systems like computers are represented by millions of these individual systems called bits. We will see more about this later when we learn about how we can combine multiple simple systems together to form a complex system.

### what is a classical state set? 

- The set of all possible states of the classical system is called classical state set. This set should be a non-empty finite set. Some systems can have infinitely many classical states but we will focus on system with finite number of classical states now. We use the symbol $\Sigma$ to represent the set of possible states. The classical state set of torch light is as follows.

$$\Sigma = \{OFF, ON \}$$

> Note that the term classical is used here to specifically differentiate the information that can be represented by a quantum systems.

### What is a single system?

 In general there is no strict line between single system and multiple systems. We can consider a car as a single system which will be in one of the possible states {ON, OFF, MOVING FRONT, MOVING BACK, etc...}. At the same time we can consider a car as a multiple systems that is combination of many individual single systems such as breaking system, clutch system, accelerator system, user saftey system and etc...

 - So the concept of single or multiple systems can be defined as per our needs.

 - Usually we consider a simple system like a Bit as a single systems and then build on top of it as a combination of these single systems to represent some complex system. For example a video game is a complex system that is represented by the combination of bits.

 - Remember that at any moment of time we can think of some multiple systems as a single system. So we can use the same ideas that we discuss here for multiple systems also. We will dicuss about this further in multiple systems section.

## Bit

### What is a bit?

The term bit is a short term for Binary Digit. A single bit can represent some information using two classical states $\Sigma = \{ 0 , 1 \}$.

### Where we use bit?

The bit is used to represent and process the information in digital computers and many other digital systems. All the numbers, charactors that are stored and processed by computers are represented by bits under the wood. 

### Why do we use binary system(or bit)?

All the digital devices we see today are mainly made up of transistors and logical gates. These components can efficiently store and process the electrical signals of HIGH(5 voltage signal) and LOW(0 voltage signal) voltages. So the intutive way of representing these information mathematically is using binary digits(or numbers).

## State of the Classical System

### How can we represent the state of the classical system mathematically?

We can think of different ways to represent the classical states of some system. For example each state of a system can be represented by some characters like {a,b,c,...} or we may try to represent each character by numbers like {1,2,3,...}. But will these approaches be helpful for mathematically processing classical information. Not every way we think of can be an optimal or a scalable answer to this problem.

One good solution that we have found is representing each state of the system by a vector. A vector can be simply represented by a matrix with only one dimension. This will be helpful for us to define properties of and operations on the classical state set. There are two ways to represent a vectors namely column vector(matrix with a single column) and a row vector(matrix with a single row).

### What is a state vector?

When column or row vector is used to represent a classical state of the system then it is called state vector. More commonly we use the column vector to represent a state. 

### How column vector represents a state?

If particular system has n classical states then we will create a column vector of length n to represent the state of that system. The i'th state s(i) of the system will have 1 in the i'th index of the column vector and 0 in all the remaining indices where 1 <= i <= n.

### Why do we need row vector then?

One fundamental operation that we can apply on matrix is a matrix transpose. When we discuss different properties of the classical system there will be a situation where we need to apply transformation to the column vector, during that time we will need row vector to do the computation(remember that when we transpose a column vector then we will get a row vector). Also remember that the row vector is a equivalent way of representing a state of the system.

### How do we differentiate row and column vector?

When we label(giving some name) the row or column vector we use the dirac notation to differentiate them. 

### What is a dirac notation of column vector?

If you take a torch light example it can be in any one of the two states OFF or ON. The column vector of this system can be represented in a following way.

$$ |OFF\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |ON\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$

This particular notation is called `ket`. Here the **OFF** is represented by the first position of a column vector and the state **ON** is by the second position of a vector.

### What is a dirac notation of a row vector?
 
The state of the same torch light example can be represented by a row vector in a following way. This notation is called `bra`.

$$ \langle OFF| = \begin{pmatrix} 0 & 1\end{pmatrix} $$
$$ \langle ON| = \begin{pmatrix} 1 & 0\end{pmatrix} $$


### How do we represent a bit using dirac notation?

The following column vectors can be used to represent a bit. the first index of the column vector corresponds to the state 0 and second corresponds to the state 1.

$$ |0\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |1\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$

These two states are called the deterministic states of the binary system. These two state vectors are specifically called standard basis vectors of dimension 2. 

### What is a deterministic state?

When a state vector has a value 1 in exactly one position of the vector and 0 in all the remaining positions then it is called a deterministic state. If only the one index of the vector has the value 1, then we can deterministically(without any ambiguity) tell the state of the system.

There is also a different kind of state vector called probabilistic state vector that doesn't have this deterministic property. We will see about it later.

### Why do the vectors $|0\rangle$ and $|1\rangle$ are called standard basis vectors?

Using these two vectors $|0\rangle$ and $|1\rangle$ we can represent any deterministic or probabilistic state of the classical systems. The above is true because we can write any other vector of dimension two as a linear combination of these two vectors. This idea can be generalized to any classical system with the n classical states.

> Note that the set of vectors that form a standard basis is called standard basis set.


## Probability vector

### What is a probabilistic state vector or probability vector?

In the probability vector, entries of the vector will be a real numbers with a constraint that the sum of the entries should add up to 1.

> **Note:** \
One important thing about representing a probabilistic state by a column vector is: 
> * All the entries of the column vector should contain non-negative real numbers
> * when the sum of entries of the column vector, then it should give us the result 1. This is because the total probability of a system can be at most one. 
>
>If the particular vector obeys the above rules, then we call that a probability vector.


### Why the sum of the entries of the probability should be 1?

In a probability vector each entry of the vector corresponds to a probability associated with the state that corresponds to that particular entry(or index) of the vector. So to satisfy the condition that the total probability of the system should be 1, the sum should be 1.

### Why do we need a probability vector?

We can't always know the current state of the clssical system for sure. There can be some uncertainty. Sometime the state of the classical system can be unknown. For example if your friend is holding a torch light inside a room, then You couldn't know the state of the torch light untill you go inside and see it(or in some way that information should be gathered or measured by you). Untill then we can assign some probability to each possible state of that torch light.

$$ 
|\psi\rangle = 
\begin{pmatrix} \frac{1}{2} \\ \frac{1}{2} \end{pmatrix} = 
\frac{1}{2} |OFF\rangle + 
\frac{1}{2} |ON\rangle
$$


$$ 
Pr(light=OFF)= \frac{1}{2} \;\; and \;\;  
Pr(light=ON) = \frac{1}{2} 
$$

Here note that the probability vector $|\psi\rangle$ is written as linear combination of deterministic state vectors $|ON\rangle$ and $|OFF\rangle$ from standard basis set. 

This way of thinking is very useful, because in a real world there can be hardware or environmental condition which will change the state of the system with some probability. For example take a same example as your friend holding a torch light inside a room. But now you know some extra information that today there is power shortage in that area and it is dark outside and your friend should be studying at this time of the day. Now the probability of torch light being ON will be increased.

The similar kind of thing can happen in our computers also. So when we represent a classical information using state $ |\psi\rangle $ it can have some higer probability of being 0 than 1 or vice versa. When we introduce probabilistic state into our classical information we can easily handle these kind of situations.

### What do we mean by measuring the state of a single system?

In previous section we have seen that we don't know the actual state of a torch light until we go inside room and see it's status. Formally this action of checking the state of a system is called measuring. Untill we mesure the state of the system, the state can be represented by some probabilistic vector based on our knowledge about the system.

As soon as we measure the state of the system, it will go from a probabilistic state to one of the possible deterministic states. Similar to our analogy of as soon as we go inside the room and check the torch light, it will be either **OFF or ON**.

## Operations on single systems

### what is an operation on a single system?

So we have seen what is the classical information and we can represent them either as deterministic vector or probabilistic vector. We also discussed that a state of the system might change over time. How can this change happen? It might be because of the reason that someone interacted with the system.

In our torch light example it might be your friend who is switching OFF or ON the torch light. Formally this particular interaction with a system can be represented by a mathematical operations. There can be two kind of operations namely deterministic operation or probabilistic operation. We will see them one by one now.

### How can we represent this operation mathemtically?

We can represent a operation using a matrix. But before that we have to understand another way of representing operation mathematically is using funcions. Functions will take some input and apply some operations on the input and produce an output. The operation that is computed by a function can be represented by a matrices. 

- For example the operation on a system with two classical states can be represented by a two dimensional square matrix.

When we multiply a matrix with a particular state vector it is kind of applying some logic on each individual elements of a vector based on some mathematical function. Each row of the matrix is applying some weightage to each entry of the input vector and computes output entry that corresponds to the row of that particular matrix.

>**Note:** If you think about it for a second, then you will understand that this is very similar to the idea of Neural Networks.

### What is a deterministic operation?

As the name suggests these operations create a deterministic changes in the system. For example the action of switching on the torch light is a deterministic operation which changes the state of a torch light from OFF to the state ON. 

Suppose there is single push button in the torch light. If you click on the button, it will switch on the light. If you click on it again, then it will switch off the light. This is very common operation on the binary system called `NOT` operation. When you apply this operation it will change current state to the other possible state of the system. If current state is 0 then it will become 1 and vice versa is also true. We can repersent this operation using following matrix.

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

Here $ NOT|0\rangle $ is a matrix multiplication. The NOT operation is applied on a column vector for state 0 of a binary system.

### How can we compute a matrix M that is equivalent of applying a function f(a particular operation)?

We have already seen that matrices in the matrix operation represent some mathematical function applied on a classical state. How can we find this matrix when we know the kind of function we want to apply. $ |f(a)\rangle$ is a function applied to some vector $a$, where the fucntion is $f:\Sigma \rightarrow \Sigma$. This means both input and output of the function is bounded by the classical state set $\Sigma$

When we know the output for each input, then we can do the matrix multiplication of each of the output(as column vector) and input(as a row vector) vectors. After that if we sum all the resulting n dimensional square matrices we will get a matrix M that represent the input output relationship, where n is the number of classical states of the system.

$$ M = \sum_{a ∈ \Sigma} |f(a)\rangle \langle a|$$

For example the following equations compute the matrix for NOT operation on the torch light that we have discussed previously. Here $\Sigma$ = {OFF, ON}. Our function will be f(ON) = OFF and f(OFF) = ON.


$$ 
NOT = \sum_{a ∈ \Sigma} |f(a)\rangle \langle a| = 
|ON\rangle \langle OFF| + 
|OFF\rangle \langle ON| = 
\begin{pmatrix} 0 & 1 \\ 1  & 0 \end{pmatrix}
$$


### What is a probabilistic operation?

Not all operations are deterministic. Some of the operation can change the state of the classical system in a probabilistic way. For example If you take a torch light example. Think of this torch light as a smart torch light. It will change the brightness of the light based on the darkness of the enviroment using some sensors.

So to make this idea simple we will say the torch light is represented by two classical systems. One representing status of torch light $\Sigma = \{ OFF, ON \}$ and another single system representing the brightness of torch light $\Sigma_1 = \{ LOW, HIGH \}$. Now this $\Sigma_1$ depends on the environmental conditions. So the operations applied on this new system $\Sigma_1$ will be probabilistic. 

$$ |LOW\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |HIGH\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$

> Don't think about the relationships between $\Sigma$ and $\Sigma_1$. We will see about their relationship and how we can combine them together in a blog about multiple systems. As of now consider $\Sigma$ and $\Sigma_1$ are two individual single systems.

When probability of darkness is larger, then the probability of state HIGH will be higher. For example $ Pr(HIGH) = \frac{3}{4} $ and $ Pr(LOW) = \frac{1}{4} $.

So now the current classical state is LOW means it is flipped to the state HIGH with probability $ \frac{3}{4} $. We can represent this operation using the folowing matrix. We just assume that if current classical state is HIGH, then the result will be Pr(HIGH) = 1 and Pr(LOW)=0.

$$ \begin{pmatrix} 3/4 & 1 \\ 1/4 & 0 \end{pmatrix} $$

> **Note: Stochastic Matrix**\
The similar rules that we discussed for the probabilistic vector will also apply for the probabilistic operations. 
> * The sum of values in each column of the stochastic matrix should add up to 1. 
> * Each entry of the matrix should be non-negative real numbers.
>
>`Stochastic matrix`: This probability matrix that obeys the above mentioned rules is called a stochastic matrix. These matrices will always represent a operation that maps the input probability vector to another probability vector as an output.

### is there some relationship between deterministic and probabilistic operations?

Another way of thinking about these probability matris is such that they are multiple deterministic operations each applied with some probability. So we can always represent the probabilist operation as a linear combination of deterministic operation with some probability associated with each deterministic operation. For example the previous probabilistic operation example can be written as linear combination of following deterministic operations.

$$ 
\begin{pmatrix} 3/4 & 1 \\ 1/4 & 0 \end{pmatrix} =  
\frac{3}{4}\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} +
\frac{1}{4}\begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix} +
\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}
$$

### composition of matrix operations(Matrix Associative property)

All the properties of a matrix multiplication is valid for the stochastic matrices also. Assume that $M_1$ and $M_2$ are the matrix operations applied on some state vector. The fact that matrix multiplication is associative and but not cummutative results in the following equivalities and inequivalities.

$$ (M_1 M_2)a = M_1 (M_2a)$$

The above is because matrix multiplication is associative. So first applying $M_2$ opeation then applying $M_1$ operation is same as applying the result of the matrix matrix multiplication $M_1 M_2$ to the state $a$.

since the matrix multiplication is not cummutative the following equation is true.

$$ (M_1 M_2)a \neq (M_2 M_1)a$$


## Notes

### What is Orthonormal Basis & Standard Basis?

A subset {v1, v2,...,v(k)} of the vector space V is callled orthonormal if $\langle v(i), v(j) \rangle = 0$ for any i!=j and $1 \leq i, j \leq k$. This means the vectors in the subset are mutually perpendicular to each other and each vector has length 1 ( means $\langle v(i), v(i) \rangle = 1$).

An onthonormal set should contain only linearly independent vectors so that it can be a basis for a vector space it spans. Such a basis is called orthonormal basis. We will discuss about this in further details in future blogs.

### What does linearly independent means?

Here linearly independent means no linear combination of vectors v(j)'s in the basis should form another vector v(i) in the same basis set, where $i \neq j$. The vector basis spans a vector space means we can represent any other vector in the vector space as a linear combination of vectors in the basis set.

Common example of a orthonormal basis is for standard basis e(i) for the Eucliden Vector Space(**$R^n$**) where e(i) is the vector with 1 at the i'th position and 0 in the all other positions. Here n is the dimension of the vector space and i = 1, 2,...,n. Here the notation **$R^n$** tries to explain that each vector in this vector space is a n-tuple of real numbers. We will learn more about this topic in future blogs.

**Standard Basis**: Standard basis is a special case of Orthonormal basis where each vector in the basis has 1 in exactly one position and 0 in all other positions. The example of a standard basis of two dimensional vector space is given below.

$$ |0\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |1\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$

