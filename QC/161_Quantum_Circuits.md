# Quantum Circuits

This notes only contains the short notes of important facts and some additional information that is not in the [original blog](https://learning.quantum.ibm.com/course/basics-of-quantum-information/quantum-circuits). So always use the original blog as the main source and this notes as addition source.

### What is Circuit model?

- There are several ways to represent the classical computation theoretically like boolean circuit model and Turing machine model. Since the circuit model resembles the actual hardware, it is more intutive than turing machine model.

### What is a boolean circuit?

A boolean circuit is made up of boolean gates and wires. The most commonly used boolean gates are AND($\land$), OR($\lor$) and NOT($\lnot$). Here the word circuit doesn't mean the closed path. The feedback loops and closed paths are not allowed in the boolean circuit model. A boolean circuit operates on a classical state set called Bit(0 or 1 practically 0 or 5 voltage).

### Can circuit model have non boolean inputs?

In general ciruit model can also operate on non boolean inputs(though not used in practical sense). One example is arithematical circuit which uses arithematic operations instead of boolean operations. The given below is a arithmetical equivalent of XOR gate.
```math
a \lor b = 1 - (1-a)(1-b) \\
a \land b = a \times b  \\
\lnot a = 1-a
```

### What is a Quantum circuit?

A quantum circuit is similar to the boolean circuit, but it will operate on a quantum states set instead of classical states set. Similar to how we use the boolean circuits to represent a classical system we can use a quantum circuit to represent a quantum system.

A quantum circuits can be implemented using quantum gates(Similar to boolean gates). 
Here wires in the circuit will represent qubits and gates will represent unitary operations or standard basis measurement. For example the Hadamard gate is a quantum gate that can compute the Hadamard operation on a particular quantum state. Keep in mind that the specific order is maintained to draw a circuit in the Qiskit environment. 


#### Order of the qubits in the circuit diagram:

- If you consider the tuple $(X_1,X_2,…,X_n)$. Then the leftmost qubit $X_1$ in the tuple will be the bottom most qubit in the circuit diagram, second qubit from the left $X_2$ will be the second to the bottom most qubit in the circuit and so on. Finally the rightmost qubit $X_n$ will be the topmost qubit in the circuit diagram. 

- Remember that even though we are representing the qubits in the circuit from bottom to the top, the cartesian product state set of the joint system will follow the same order as the one that we have defined in the tuple. Also the product state of the joint system is still represented based on the order mentioned in the tuple.

- We know that the joint operation on the joint system is represented by the tensor product of the matrices that are representing the individual operations on the individual systems. The order of this tensor product also follows the same order as the qubit tuple. 

#### Order of the operations in the circuit diagram:

- If you consider the operation $(M_1 M_2 … M_n) (X_1 X_2 … X_2)$,  here the rightmost operation $M_n$ is applied first on the system, then second to the right and so on. At the last the leftmost operation $M_1$ is applied. So this order should be maintained in the circuit diagram also. 

- In the circuit the initial values of the qubits are defined in the left side of the circuit. So the sequence of operations are defined from the left to the right side of the diagram. The first operation $M_n$ (the rightmost operation in the equation) will be placed at the first position(the leftmost operation in the diagram). The second operation $M_n-1$ (the second to the last in the equation) will be placed at the second position(the second from the left) and so on. 

- The last operation $M_1$ (first from the left in the equation) will be placed at the rightmost position in the diagram. When we want to aggregate all these operations into a single matrice, then we should follow the same order as we defined in the equation for the matrix multiplication of these unitary matrices. $M = M_1 M_2 … M_n$

Suppose we have a two qubit system $(X, Y)$. First we apply the Hadamard operation on the Y and then apply the controlled NOT operation on the X where the control bit is Y. Here the order of the operations and qubits in the circuit diagram are as follows.

![Alt text](./images/quantum_cir_ex1.png "a simple qunatum circuit")

Remember the measurement is also a kind of operation. So the measurements are defined using the measurement gates. The following diagram shows the measurement of the state of the qubits $X$ and $Y$. The action of measuring will measure the state of the qubits and save them into the classical bits $A$ and $B$.

![Alt text](./images/quantum_cir_ex2.png "a simple qunatum circuit with measurement gates")


Note: In circuit diagram some times we could choose to show the different operations applied on different inputs individually. These operations will be shown in the same vertical line. That means these individual operation can be joined together using the tensor product. If some input is only having a empty line, then we could use the identity matrix.

### is density matrix formulation in quantum computing more general than quantum circuit model?

The density matrix formulation in quantum computing is more general than the quantum circuit model. The density matrix formalism allows for the description of mixed states, which are quantum states that cannot be described by a single pure state vector. This is important because in many practical scenarios, quantum systems are not in pure states due to interactions with the environment or measurement errors.

On the other hand, the quantum circuit model deals primarily with pure states and describes quantum computation as a sequence of unitary operations on these states. While the quantum circuit model is extremely useful for understanding and designing quantum algorithms, the density matrix formulation provides a more general and flexible framework for describing quantum states and operations, especially in the presence of noise and decoherence. 

> ***Extra:*** The term decoherence is the process by which a system's behavior changes from quantum mechanics to classical mechanics. It occurs when a complex object interacts with its surroundings, causing quantum properties to disappear quickly, which leads to a loss of quantum coherence.
>
> Quantum coherence is a fundamental concept in quantum physics that describes a quantum mechanical system's ability to maintain its quantum states and generate interference patterns. It's based on the superposition principle, which states that a single quantum state can simultaneously exist in multiple states. For example, if an object's wave-like nature is split in two, the two waves can interfere with each other to form a single state that's a superposition of the two. In a coherent state, quantum states are precisely defined and exhibit regular and predictable behavior. 
>
> Quantum coherence is a necessary condition for entanglement and other types of quantum correlations. It's also an important resource in quantum computation and quantum information processing. For example, a qubit's coherence time, or how long it retains its information, can be used to compare the quality of qubits.


## Inner products, Orthonormal sets

### What is inner product?

If we multiply a row vector with a column vector using the same rules as matrix multiplication, then it is called inner product. This is important because the inner product of a vector with itself will give us a square of Euclidean norm of that vector.

```math
\begin{equation}\tag{1}
\begin{split}
|\psi\rangle &= 
\begin{pmatrix}
\alpha_1 \\ \alpha_2 \\ \vdots \\ \alpha_n
\end{pmatrix} \\

\langle \psi| &= (|\psi\rangle)^{\dagger}= 
\begin{pmatrix}
\overline{\alpha_1} & \overline{\alpha_2} & \cdots & \overline{\alpha_n}
\end{pmatrix} \\

Inner\ product &= \langle \psi||\psi\rangle
= \overline{\alpha_1}\alpha_1 + 
\overline{\alpha_2}\alpha_2 + 
\cdots + 
\overline{\alpha_n}\alpha_n

\end{split}
\end{equation}
```


todo: Add small example equations for each of these.
### Properties of inner product

- The Euclidean norm relationship: The Euclidean norm of a vector is the square root of the inner product of the vector with itself. This value will always be a non negative real number.

- Conjugate symmetry: Inner product of two vectors is equal to the complex conjugate of the inner product of the same two vectors in the reverse order.

- Inner product has the property of linearity in the first argument and conjugate linearity in the second argument.

- The Cauchy Schwarz inequality: the absolute value of the inner product of two vectors is always less than or equal to the product of the Euclidean norm of the individual vectors.



### What is othogonal set?

We say that two vectors are orthogonal when they are at right angle to each other or equivalently perpendicular to each other. For example if vectors $|\psi_1\rangle$ and $|\psi_2\rangle$ are orthogonal, then their inner product will be 0($\langle \psi_1||\psi_2\rangle = 0$).

An orthogonal set is a set of vectors where all the vectors are mutually orthogonal to each other. In other words for any two vectors $|\psi_i\rangle$ and $|\psi_j\rangle$ where $i \neq j$, the inner product $\langle \psi_i||\psi_j\rangle = 0$.


### What is orthonormal sets?

The set of vectors is called an orthonormal set, if the set is orthogonal and each vector in the set is a unit vector. In other words for any two vectors $|\psi_i\rangle$ and $|\psi_j\rangle$ from the set, if $i \neq j$, then the inner product $\langle \psi_i||\psi_j\rangle = 0$. If $i=j$, then $\langle \psi_i||\psi_i\rangle = 1$.


### Properties of orthonormal sets 

- Suppose we have a set of m orthonormal vectors that are pulled from the n dimensional vector space. If these vectors span the subspace of dimension m, then we can always add remaining n-m vectors to this set and compute the set of orthonormal vectors that span the n dimensional vector space. To do this we can use the Gram Schmitt orthogonalization process.

- Unitary matrices and orthonormal sets are strongly linked to each other. If you form the set of vectors using the columns of the unitary matrix, then that set will be an orthonormal set. Similarly if you form a set of vectors using the rows of the unitary matrix, then that also will be an orthonormal set. 

- We can prove both of the above mentioned properties mathematically. We are stating these properties because this will be helpful in defining projection matrices and projections using orthonormal sets and unitary matrices.


### What is orthonormal basis?

Suppose we have an orthonormal set S and vectors in the set S have been drawn from the vector space V of dimension n. if vectors in the set S spans the vector space V, then the set S is called orthonormal basis. For example the given below sets $S_1$ and $S_2$ are orthonormal basis of dimension 2 and 4 respectively.

```math
S_1 = \{ |+\rangle, |-\rangle \} \\
S_2 = \{ |\phi^+\rangle, |\phi^-\rangle, |\psi^+\rangle, |\psi^-\rangle \}
```

Remember that the standard basis set of any dimension n is also a orthonormal basis of the vector space of dimension n.

### How to compute an orthonormal basis for any vector space V?

- We can use the Graham-Schmidt orthogonalization process to compute the orthonormal basis for any arbitrary vector space. The Graham-Schmidt orthogonalization process is a method used to compute an orthogonal (or orthonormal) basis for a subspace of a vector space. Given a set of linearly independent vectors that span a subspace, the process constructs an orthogonal (or orthonormal) set of vectors that also span the same subspace.

- For a vector space, the process can be applied to a set of linearly independent vectors that span the entire space to compute an orthogonal (or orthonormal) basis for that space.

- Note that input to this process will be set of n linearly independent vectors that span the vector space V and output will be the set of orthogonal vectors that span the vector space V.

- In a vector space of dimension n, any set of n linearly independent vectors will span the entire vector space. This is because a set of n linearly independent vectors in an n-dimensional space forms a basis for that space, and any vector in the space can be expressed as a linear combination of these basis vectors.

- The output of the Grahm-Schmidt orthogonalization process is the set of orthogonal vector. To get the orthonormal basis we have convert all the vectors in the set to the unit vectors. This can be easily done by dividing each vector in the set by it's Euclidean norm value.


## Projective measurements

#### Projection matrices

In our definition the projection matrix is the square matrix with the following two properties.

> - Complex conjugate of the square matrix should result in the same square matrix. $\Pi^{\dagger} = \Pi$
> - The square matrix raised to the power 2 should result in the same square matrix. $\Pi^{2} = \Pi$

Note that if you multiply a unit vector with itself($|\psi\rangle \langle\psi|$), then you will get a projection matrix. This can be easily proved just using the Diarac notation. lets take an example of $|\pi\rangle = |\psi\rangle \langle\psi|$.

```math
\Pi^{\dagger} = (|\psi\rangle \langle\psi|)^{\dagger} = (\langle\psi|)^{\dagger} (|\psi\rangle)^{\dagger} =  |\psi\rangle \langle\psi| = \Pi \\

\Pi^2 = (|\psi\rangle \langle\psi|)^2 = |\psi\rangle \langle\psi| |\psi\rangle \langle\psi| =  |\psi\rangle \langle\psi| = \Pi
```

In the first equation we use the property of transpose of the matrix $(AB)^{\dagger} = B^{\dagger} A^{\dagger}$. 
In the second equation we use the property of unit vector that $\langle \psi||\psi \rangle = 1$

This idea can be used for any set of unit vecotr $\{ \psi_1 , \psi_2 \dots \psi_k \}$.

```math
\Pi^{\dagger} = \left( \right) = \Pi \\

\Pi^2 = (|\psi\rangle \langle\psi|)^2 = |\psi\rangle \langle\psi| |\psi\rangle \langle\psi| =  |\psi\rangle \langle\psi| = \Pi
```



### What is a projective measurement?

Projective measurement is a more general way of defining the measurement of a quantum system than the standard basis measurement. We will see that standard basis measurement is a special case of projective measurement. But keep in mind that we could implement any projective measurement using unitary operations, standard basis measurement and some extra workspace system(like extra qubits for the process). So the projective measurement uses the standard basis measurement and unitary operations to express the more general way of measuring quantum systems.

Projective measurement is described by a collection of projection matrices, where the sum of these projection matrices result in an identity matrix. This directly corresponds to the fact that probability associated with the different outcome of the measurement should sum upto 1.

To understand the projective measurement you can think in terms of the meaning of the workd 'projection'.It means projecting something onto the some other thing. Here will will be projecting a particular quantum state vector onto the set of possible measurement results. In the standard basis measurement the measurement result set is a standard basis set. In the case of projective measurement the measurement result set can be defined by us based on our set of projection matrices.


## Limitations on quantum information

### Irrelevance of global phase


### No cloning theorem


### non orthogonal states cannot be perfectly discriminated