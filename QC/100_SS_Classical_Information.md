# Classical Information(Single System)
 In this blog we are going to see about classical information about some classical system. Here by single system I mean single classical system as a separate entityt. We are not going to see about interaction betweeen multiple systems. But about the classical states of a single classical system. We will see a Bit as an individual classsical system in this blog.

## What is Classical Information?

Before we start learning about Quantum information we have to first understand the concept of classical information. Why should we do that? We have lived in classical world for some time now. So First we will clearly define what we know about classical information. Then later we can easily take the analogies from the classical world to the quantum world.

> Classical information is a knowledge about the classical sytems which can be in one of their possible classical states.

## What is Classical Sytems and Clasical States?

* Classical system is any system we see in our day to day life which can be in one of it's possible states. For example the fan is a classical system which is in one of following states at any moment of time: Σ = {HIGH, MEDIUM, LOW and OFF}. The torch light is a classical system which can be in one of the following states: Σ = {OFF, ON}. Our digital systems are very similar to this torch light analogy. In a digital computer the information is stored and processed in the form of Bits which can be either in a state 0 or a state 1. We use the symbol Σ to represent the set of possible states.

* You can think of classical states as a behaviour of classical system. Classical state can be represented by a non-empty finite set. Some systems can have infinitely many classical states but we will focus on system with finitely many states now. We will be mainly focussing on a Bits since we will use them represent the classical information in our digital systems.

## Why do we use Bits(Binary digits or {0, 1}) to represent them?

* The first thing that come to my mind when we say classical information is bits. Bits is a fundamental way we represent and process the classical information in our computers. All the numbers, charactors and everything you see in the computer is represented by a bits under the wood. 

* Why do we use binary system? The digital world we see today is made up of transistors and logical gates. These components can efficiently store and process the electrical signals of HIGH and LOW voltages. So the best way we can represent them in the mathematical world is using binary numbers.

* At any moment of time a bit can be in one of the two classical states. Either in a state 0(OFF) or in a state 1(ON).

* Eg. You can think of single system of classical world as a classical torch light example which can be in either ON or OFF state. This can be represented by a binary numbers 1(ON) and 0(OFF) correspondingly.

## How can we represent state of a system mathematically?

* We can think of some different ways to represent classical states of a classical system. For example each state of a system can be represented by some characters like {a,b,c,...}. We may try to represent each character by numbers like {1,2,3,...}. But will these approaches be helpful for mathematically processing classical information. Not every way we think of can be a optimal or scalable answer to this problem.

* One good solution we have found out for this problems is representing each state of the system by a vector. We can represent a vector by a single dimensional row or column matrix(specifically called a vector). This way of representing states seems intutive and scalable in terms of our mathematical thinking.

* The first way we are going see is representing each classical state of a system by a column vector(another way representing is a row vector). If particular system has n states then we will create a column vector of length n to represent a state. The position i of the column vector will be 1 and all the other position will contain 0 to represent a classical state s(i) where 1 <= i <= n. 

## What is a column vector and Dirac notation for it?

* We are going to introduce a notation called dirac notation to give some label to each state of the classical system for example If you take our torch light example it can be in one of two states OFF or ON. Then we will represent these to state as given below using column vector. These notations are specifically useful in clearly differentiating row and column vectors. 

$$ |OFF\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |ON\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$


* Here the weiredly looking label for **OFF or ON** is spelled like `ket OFF` or `ket ON` respectively. This is a part of Dirac notation. Here **OFF** is represented by a first position of a vector and ON is represented by a second position of a vector. This will give us direct analogy for representing binary system using similar notations.

## What is a row vector and Dirac notation for it?

* Soon we will use the row vectors also to represent a state in some scenarios. We will use another part of Dirac notation for that. The given below another weiredly looking label for **OFF or ON** is spelled like `bra OFF` or `bra ON` respectively. 

$$ \langle OFF| = \begin{pmatrix} 0 & 1\end{pmatrix} $$
$$ \langle ON| = \begin{pmatrix} 1 & 0\end{pmatrix} $$

* Similary we define a state of binary sytem using simlar notations. Here state OFF of system corresponds to a binary state 0 and ON coresponds to a state 1. I am only giving examples of column vectors here. This way of representing a state is called deterministic state. Where there can only two possible state with definite answer for a binary system.

* This following vectors called the standar basis vector for binary system. Using these two vectors we can represent any deterministic or probabilistic state of system. We can write any other vector of this form as linear combination of these two vectors. We can stadard basis vecor for any classical state set in similar way.

$$ |0\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |1\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$

### what does the combination of the `bra` and `ket` represent?

* Together when we join them together they will form a word `braket`. The following way of notation is called an inner product of states ON(represented as row vector) and OFF(represented as column vector). This operation will give you scalar value as a result(That's what you will expect when you are mulplying row vector with a column vector). 

$$ \langle ON||OFF\rangle$$

or simply

$$ 
\langle ON|OFF\rangle = 
\begin{pmatrix} 0 & 1\end{pmatrix} \begin{pmatrix} 1 \\ 0\end{pmatrix} = 0 
$$

* Another combination can be `ketbra` notation(This name may be made up by me). where we multiply a column vector by a row vector. This way when we multiply two states in the binary system we will get a two dimensional matrix representing some connection between these two states.

$$ 
|ON\rangle \langle OFF| = 
\begin{pmatrix} 1 \\ 0\end{pmatrix} 
\begin{pmatrix} 0 & 1\end{pmatrix} = 
\begin{pmatrix} 0 & 1\\ 0 & 0\end{pmatrix}
$$

* If you notice here the resultant matrix has 1 at the `row= 1 and column = 2`. It represents that column vector contains 1 at the row 1 and row vector contains 1 at the column 2. We will explore this logic further in the matrix operations section of this blog. 




## Where does the probabilty comes into the picture?

* We don't always know the current state of the clssical system for sure. Sometime the state of the classical system can be unknown. If your friend is holding a torch light inside a room. You won't know the state of the torch light untill you go and see inside the room. Untill then the probabilty of torch being ON will be 1/2 and being OFF can be 1/2. Then you can represent the state of the torch light using following column vector. 

$$ 
|state\rangle = 
\begin{pmatrix} \frac{1}{2} \\ \frac{1}{2} \end{pmatrix} = 
\frac{1}{2} |OFF\rangle + 
\frac{1}{2} |ON\rangle
$$

* This is because we don't always know the state of some classical system with confident. We can represent these uncertainty using a probabilistic vectors. Here we associate some probability for system being in each of the classical state. For example in the above state 

$ Pr(light=OFF)= \frac{1}{2} $ and  
$ Pr(light=ON) = \frac{1}{2} $

* Here you can also see that some probabilistic state of the classical system is represented by a linear combination of column vectors from the standard basis set. This is what I was trying to explain about standard basis vectors previously.

* This way of thinking is very useful, because in real world there can be hardware or environmental condition which will change the state of the system with some probability. For example take a same example as your friend holding torch light inside room. But now you know some extra information that today there is power shortage in that area and it is dark outside. Now the probability of torch light being ON will be increased.

* The similar kind of thing can happen in our computers also. So when we represent a classical information using state $ |state\rangle $ it can have some higer probability of being 0 than 1 or vice versa. When we introduce probabilic state into our classical information we can easily handle these kind of situations.

* **Note: One important thing about representing a probabilistic state by a column vector is: when we some all the values in the vector it should give the sum 1. This is because the total probability of a system can be at most one. All the entries of the column vector should contain non-negative real numbers.**


## What do we mean by measuring the state of a system?

* In previous section we have seen that we don't know the actual state of a torch light until we go inside room and see it's status. This action of checking the state of a system is called measuring the state of the system formally. Untill we mesure the state of the system, the state can be represented by some probabilistic vector based on our knowledge about the system.

* As soon as we go and measure the state of the system the state will go from a probabilistic state to one of the possible deterministic states. As soon as we go inside the room and check the torch light, it will be either **OFF or ON**.

## What is matrix operation and why do we use it?
  So we have seen what is classical information and we can represent them either as deterministic vector or probabilistic vector. We also discussed that the state of the system might change over time. How can the state of the system will change. It might be because of the reason that someone interacted with the system.
* In our torch light example it might be you friend who is switching OFF or ON the torch light. This particular interaction with a system can be represented by a mathematical operations formally. There can be two kind of operations namely deterministic operation or probabilistic operation. We will see them one by one now.

* Before we get into that we have to understand that another way of representing operation mathematically is using funcions. Functions will take some input and apply some operations on the input and produce an output. Here we are going to represent these operations using two dimensional matrices. 

* When we multiply some matrix with a particular state vector it is kind of applying some logic on each individual elements of a vector based on some mathematical function. So in a broad thinking these matrices are representing some operation of a particular function.

### What is deterministic operation?

* As name suggests these operations create a deterministic changes in the system. For example the action of switching on the torch light is a deterministic operation which changes the state of a torch light from OFF to the state ON. 

* Suppose there is single push button in the torch light. If you click on the button, it will switch on the light. If you click on it again, then it will switch off the light. This is very common operation on classical binary system called `NOT` operation formally. When you apply this operation it will change current state to the other possible state in a set. If current state is 0 then it will become 1 and vice versa. We can repersent this operation using following matrix.

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

* Here $ NOT|0\rangle $ is matrix multiplication NOT applied on a column vector for state 0 of a binary system.

#### How can we compute some matrix M that is equivalent of applying function f?

* We have seen that the matrices in the matrix operation represent some mathematical function applied on some classical state. How can we find this matrix when we know the kind of function we want to apply. $ |f(a)\rangle$ is a function applied to some vector a, where the fucntion is `f:Σ->Σ`.

* We have seen about `ketbra` operation in dirac notation section. When we know what is the output for each input, then we can apply the `ketbra` opertion for each of these output(as column vector) and input(as a row vector) vectors. After that if we sum all the resultant 2 dimensional matrices we will get a matrix M that represent the input output relationship that we need.

$$ M = \sum_{a ∈ Σ} |f(a)\rangle \langle a|$$


* For example the following equations compute the matrix for NOT operation on the torch light that we have discussed previously. Here Σ = {OFF, ON} or you can think of equivalent binary operation. Our function will be f(ON) = OFF and f(OFF) = ON.


$$ 
NOT = \sum_{a ∈ Σ} |f(a)\rangle \langle a| = 
|ON\rangle \langle OFF| + 
|OFF\rangle \langle ON| = 
\begin{pmatrix} 0 & 1 \\ 1  & 0 \end{pmatrix}
$$


### What is probabilistic operation?

* Not all operations are deterministic. Some of the operation can change the state of the classical system in a probabilistic way. For example If you take a torch light example. Think of this torch light as a smart torch light. It will change the brightness of the light based on the darkness of the enviroment using some sensors.

* So to make this idea simple we will say the torch light is represented by two classical system. One representing status of torch light `Σ = {OFF, ON}` and another system representing the brightness of torch light `Σ1 = {LOW, HIGH}`. Now this `Σ1` depends on the environmental conditions. So the operations applied on this system will be probabilistic.

$$ |LOW\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |HIGH\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$

* When probability of darkness is larger, then the probability of state HIGH will be higher. For example $ Pr(HIGH) = \frac{3}{4} $ and $ Pr(LOW) = \frac{1}{4} $.

* So now the current classical state is LOW means it is flipped to the state HIGH with probability $ \frac{3}{4} $. We can represent this operation using the folowing matrix. We just assume that if current classical state is HIGH, then the result will be Pr(HIGH) = 1 and Pr(LOW)=0.

$$ \begin{pmatrix} 3/4 & 1 \\ 1/4 & 0 \end{pmatrix} $$

* **Note: Similar rules as we discussed in the probabilistic vector applies to probabilistic operations alos. The sum of values in each column of the matrix should add up to 1. Each entry of the matrix should be non-negative real numbers**

* Stochastic matrix: This probability matrix that obeys the above mentioned rules is called stochastic matrix. These matrices will always map the probability vector to another probability vector as an output.

* Another way of thinking about these probability matris is such that they are multiple determinist matrix operation each appliede with some probability. So we can always represent the probabilist operation as a linear combination of deterministic operation with some probability associated with each deterministic operation. For example the previous probabilistic operation can be written as linear combination of following deterministic operations.

$$ 
\begin{pmatrix} 3/4 & 1 \\ 1/4 & 0 \end{pmatrix} =  
\frac{3}{4}\begin{pmatrix} 1 & 0 \\ 0 & 0 \end{pmatrix} +
\frac{1}{4}\begin{pmatrix} 0 & 0 \\ 1 & 0 \end{pmatrix} +
\begin{pmatrix} 0 & 1 \\ 0 & 0 \end{pmatrix}
$$

### composition of matrix operations(Matrix Associative property)

* All the properties of matrix multiplication is valid here. Assume that $M_1$ and $M_2$ are the matrix operations applied on some state vector. The fact that matrix multiplication is associative and but not cummutative results in following equivalities and inequivalities.

$$ (M_1 M_2)a = M_1 (M_2a)$$
because matrix multiplication is associative. So first applying $M_2$ opeation then applying $M_1$ operation is same as applying the result matrix matrix multiplication $M_1 M_2$ to the state a.

$$ (M_1 M_2)a \neq (M_2 M_1)a$$
because matrix multiplication is not cummutative.


## Notes

### What is Orthonormal Basis & Standard Basis?

* A subset {v1, v2,...,v(k)} of the Vector Space V with a inner product <,> is callled orthonormal if < v(i), v(j) > = 0 for any i!=j and 1<= i,j <= k. This means the vectors in the subset are mutually perpendicular to each other and each vector has length 1 ( means < v(i), v(i) > = 1).

* An onthonormal set should contain only linearly independent vectors so that it can be a vector basis for a vector space it spans. Such a basis is called orthonormal basis. 

* Here linearly independent means no linear combination of vectors v(j)'s in the basis should form another vector v(i) in the same basis set where i!=j. The vector basis spans a vector space means we can represent any vector in the vector space as a linear combination of vectors in the basis set.

* Common example of a orthonormal basis is for standard basis e(i) for the Eucliden Vector Space(**R**^n) where e(i) is the vector with 1 at the i'th position and 0 in the all other positions. Here n is the dimension of the vector space and i = 1,2,...,n. Here the notation **R** tries to explain that each vector in this vector space is a n-tuple of real numbers.

* **Standard Basis**: Standard basis is a special case of Orthonormal basis where each vector in the basis has 1 in exactly one position and 0 in all other positions.

