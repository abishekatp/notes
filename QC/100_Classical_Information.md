# Classical Information

## What is Classical Information?

Before we start learning about Quantum information we have to first understand the concept of classical information. Why should we do that? We have lived in classical world for some time now. So First we will clearly define what we know about classical information. Then later we can easily take the analogies from the classical world to the quantum world.

> Classical information is a knowledge about the classical sytems which can be in one of their possible classical states.

### What is Classical Sytems and Clasical States?

* Classical system is any system we see in our day to day life which can be in one of it's possible states. For example the fan is a classical system which is in one of following states at any moment of time: Σ = {HIGH, MEDIUM, LOW and OFF}. The torch light is a classical system which can be in one of the following states: Σ = {OFF, ON}. Our digital systems are very similar to this torch light analogy. In a digital computer the information is stored and processed in the form of Bits which can be either in a state 0 or a state 1. We use the symbol Σ to represent the set of possible states.

* You can think of classical states as a behaviour of classical system. Classical state can be represented by a non-empty finite set. Some systems can have infinitely many classical states but we will focus on system with finitely many states now. We will be mainly focussing on a Bits since we will use them represent the classical information in our digital systems.

### Why do we use Bits(Binary digits or {0, 1}) to represent them?

* The first thing that come to my mind when we say classical information is bits. Bits is a fundamental way we represent and process the classical information in our computers. All the numbers, charactors and everything you see in the computer is represented by a bits under the wood. 

* Why do we use binary system? The digital world we see today is made up of transistors and logical gates. These components can efficiently store and process the electrical signals of HIGH and LOW voltages. So the best way we can represent them in the mathematical world is using binary numbers.

* At any moment of time a bit can be in one of the two classical states. Either in a state 0(OFF) or in a state 1(ON).

* Eg. You can think of single system of classical world as a classical torch light example which can be in either ON or OFF state. This can be represented by a binary numbers 1(ON) and 0(OFF) correspondingly.

### How can we represent state of a system mathematically?

* We can think of some different ways to represent classical states of a classical system. For example each state of a system can be represented by some characters like {a,b,c,...}. We may try to represent each character by numbers like {1,2,3,...}. But will these approaches be helpful for mathematically processing classical information. Not every way we think of can be a optimal or scalable answer to this problem.

* One good solution we have found out for this problems is representing each state of the system by a vector. We can represent a vector by a single dimensional row or column matrix(specifically called a vector). This way of representing states seems intutive and scalable in terms of our mathematical thinking.

* The first way we are going see is representing each classical state of a system by a column vector(another way representing is a row vector). If particular system has n states then we will create a column vector of length n to represent a state. The position i of the column vector will be 1 and all the other position will contain 0 to represent a classical state s(i) where 1 <= i <= n. 

### What is a column vector and Dirac notation for it?

* We are going to introduce a notation called dirac notation to give some label to each state of the classical system for example If you take our torch light example it can be in one of two states OFF or ON. Then we will represent these to state as given below using column vector. These notations are specifically useful in clearly differentiating row and column vectors. 

$$ |OFF\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |ON\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$


* Here the weiredly looking label for **OFF or ON** is spelled like `ket OFF` or `ket ON` respectively. This is a part of Dirac notation. Here **OFF** is represented by a first position of a vector and ON is represented by a second position of a vector. This will give us direct analogy for representing binary system using similar notations.

### What is a row vector and Dirac notation for it?

* Soon we will use the row vectors also to represent a state in some scenarios. We will use another part of Dirac notation for that. The given below another weiredly looking label for **OFF or ON** is spelled like `bra OFF` or `bra ON` respectively. 

$$ \langle OFF| = \begin{pmatrix} 0 & 1\end{pmatrix} $$
$$ \langle ON| = \begin{pmatrix} 1 & 0\end{pmatrix} $$

* Together when we join them together they will form a word `braket`. The following way of notation is called an inner product of states ON(represented as row vector) and OFF(represented as column vector). This operation will give you scalar value as a result(That's what you will expect when you are mulplying row vector with a column vector). 

$$ \langle ON||OFF\rangle$$
or simpley 
$$ \langle ON|OFF\rangle$$

* Similary we define a state of binary sytem using simlar notations. Here state OFF of system corresponds to a binary state 0 and ON coresponds to a state ON. I am only giving examples of column vectors here. So this way of representing a state is called deterministic state. Where there can only two possible state with definite answer.

$$ |0\rangle = \begin{pmatrix} 1 \\ 0\end{pmatrix} $$
$$ |1\rangle = \begin{pmatrix} 0 \\ 1\end{pmatrix} $$

* This is called the standar basis vector for binary system. Using these two vectors we can represent any deterministic or probabilistic state of system. We can write any other vector of this form as linear combination of these two vectors.

### Where does the probabilty comes into the picture?

* We don't always know the current state of the clssical system for sure. Sometime the state of the classical system can be unknown. If your friend is holding a torch light inside a room. You won't know the state of the torch light untill you go and see inside the room. Untill then the probabilty of torch being ON will be 1/2 and being OFF can be 1/2. Then you can represent the state of the torch light using following column vector. 

$$ |state\rangle = \begin{pmatrix} \frac{1}{2} \\ \frac{1}{2} \end{pmatrix} = \frac{1}{2} |OFF\rangle + \frac{1}{2} |ON\rangle$$

* This is because we don't always know the state of some classical system with confident. We can represent these uncertainty using a probabilistic vectors. Here we associate some probability for system being in each of the classical state. For example in the above state 

$ Pr(light=OFF)= \frac{1}{2} $ and  $ Pr(light=ON) = \frac{1}{2} $

* Here you can also see that some probabilistic state of the classical system is represented by a linear combination of column vectors from the standard basis set. This is what I was trying to explain about standard basis vectors previously.

* This way of thinking is very useful, because in real world there can be hardware or environmental condition which will change the state of the system with some probability. For example take a same example as your friend holding torch light inside room. But now you know some extra information that today there is power shortage in that area and it is dark outside. Now the probability of torch light being ON will be increased.

* The similar kind of thing can happen in our computers also. So when we represent a classical information using state $ |state\rangle $ it can have some higer probability of being 0 than 1 or vice versa. When we introduce probabilic state into our classical information we can easily handle these kind of situations.

* **One important thing about representing a probabilistic state by a column vector is: when we some all the values in the vector it should give the sum 1. This is because the total probability of a system can be at most one. All the entries of the column vector should contain non-negative real numbers.**


## What do we mean by measuring the state of a system?

* In previous section we have seen that we don't know the actual state of a torch light until we go inside room and see it's status. This action of checking the state of a system is called measuring the state of the system formally. Untill we mesure the state of the system, the state can be represented by some probabilistic vector based on our knowledge about the system.

* As soon as we go and measure the state of the system the state will go from a probabilistic state to one of the possible deterministic states. As soon as we go inside the room and check the torch light, it will be either **OFF or ON**.

### What is matrix operation and why do we use it?
  So we have seen what is classical information and we can represent them either as deterministic vector or probabilistic vector. We also discussed that the state of the system might change over time. How can the state of the system will change. It might be because of the reason that someone interacted with the system.
* In our torch light example it might be you friend who is switching OFF or ON the torch light. This particular interaction with a system can be represented by a mathematical operations formally. There can be two kind of operations namely deterministic operation or probabilistic operation. We will see them one by one now.

* Before we get into that we have to understand that another way of representing operation mathematically is using funcions. Functions will take some input and apply some operations on the input and produce an output. Here we are going to represent these operations using two dimensional matrices. 

* When we multiply some matrix with a particular state vector it is kind of applying some logic on each individual elements of a vector based on some mathematical function. So in a broad thinking these matrices are representing some operation of a particular function.

### What is deterministic operation?

* As name suggests these operations create a deterministic changes in the system. For example the action of switching on the torch light is a deterministic operation which changes the state of a torch light from OFF to the state ON. 

* Suppose there is single push button in the torch. If you click on it, it will It will switch on the light. If you again click on it, it will switch off the torch light. This is very common operation on any classical system called `NOT` operation formally.




## Notes

### What is Unitary Matrix?

Unitary matrix is a square matrix with complext numbers as its entries, wehere the invers of the unitary matrix is equal to the conjugate transpose of a matrix. When you multiply a unitary matix with its conjugate transpose matrix you will get a identity matrix as a result(what you would have expected when multiplying a matrix with its inverse).

### What is Conjugate Transpose? 

Conjugate transpose of a matrix is a normal transpose operation on a matrix together with computing the complex conjugate of each complex number in the matrix.

### What is Orthonormal Basis & Standard Basis?

* A subset {v1, v2,...,v(k)} of the Vector Space V with a inner product <,> is callled orthonormal if < v(i), v(j) > = 0 for any i!=j and 1<= i,j <= k. This means the vectors in the subset are mutually perpendicular to each other and each vector has length 1 ( means < v(i), v(i) > = 1).

* An onthonormal set should contain only linearly independent vectors so that it can be a vector basis for a vector space it spans. Such a basis is called orthonormal basis. 

* Here linearly independent means no linear combination of vectors v(j)'s in the basis should form another vector v(i) in the same basis set where i!=j. The vector basis spans a vector space means we can represent any vector in the vector space as a linear combination of vectors in the basis set.

* Common example of a orthonormal basis is for standard basis e(i) for the Eucliden Vector Space(**R**^n) where e(i) is the vector with 1 at the i'th position and 0 in the all other positions. Here n is the dimension of the vector space and i = 1,2,...,n. Here the notation **R** tries to explain that each vector in this vector space is a n-tuple of real numbers.

* **Standard Basis**: Standard basis is a special case of Orthonormal basis where each vector in the basis has 1 in exactly one position and 0 in all other positions.

