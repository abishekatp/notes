# Quantum Circuits

### What is Circuit model?

- One of the ways to represent classical computation is using boolean circuits model and also there are some other ways like Turing machine model. Since the circuit model is more close to how hardware works, it is more intutive than turing machine model.

### What is boolean circuits?

The boolean circuits are made up of boolean gates and wires. The commonly used boolean gates are AND($\land$), OR($\lor$) and NOT($\lnot$). Here the word circuit doesn't mean the closed path. The feedback loops and closed paths are not allowed in the boolean circuit model. The boolean circuits operate on classical state set called Bit(0 or 1 practically 0 or 5 voltage).

### Can circuit model have non boolean inputs?

In general ciruit model can also operate on non boolean inputs(though not used in practical sense). One example is arithematical circuit which uses arithematic operations instead of boolean operations. The given below is arithmetical equivalent of XOR gate.
$$
a \lor b = 1 - (1-a)(1-b) \\
a \land b = a \times b  \\
\lnot a = 1-a
$$

### What is a Quantum circuit?

Quantum circuit will operate on quantum states instead of classical states. Similar to how we use the boolean circuits to represent a classical system we use a quantum circuit to represent a quantum system.

Quantum circuits can be implemented using quantum gates(Similar to boolean gates). 
Here wires in the circuit represent qubits and gates represent quantum unitary operations or standard basis measurement. As we learn new types of measurements and other concepts we can extend this basic idea of quantum circuits. In the Qiskit specific order is maintained to draw a circuit. 
For example the Hadamard gate is a quantum gate that can compute the Hadamard operation on a quantum state. 


#### Order of the qubits in the circuit diagram:

- If you consider the tuple $(X_1,X_2,…,X_n)$. Then the leftmost qubit $X_1$ in the tuple will be the bottom most qubit in the circuit diagram, second qubit from the left $X_2$ will be the second to the bottom most qubit in the circuit and so on. Finally the rightmost qubit $X_n$ will be the topmost qubit in the circuit diagram. 

- Remember that even though we are representing the qubits in the circuit from bottom to the top, the cartesian product state set of the joint system will follow the same order as the order defined in the tuple. Also the tensor product state of the joint system is still represented by the same order as the tuple.

- We know that the joint operation on the joint system is represented by the tensor product of the matrices that are representing the individual operations on the individual systems. The order of this tensor product also follows the same order as the qubit tuple. 

#### Order of the operations in the circuit diagram:

- If you consider the operation $(M_1 M_2 … M_n) (X_1 X_2 … X_2)$,  here the rightmost operation $M_n$ is applied first on the system, then second to the right and so on. At the last the leftmost operation $M_1$ is applied. So this order should be maintained in the circuit diagram also. 

- In the circuit the initial values of the qubits are defined in the left side of the circuit. So the sequence of operations are defined from the left to the right of the diagram. The first operation $M_n$ (the rightmost operation in the equation) is defined at the first position(the leftmost operation in the diagram). The second operation $M_n-1$ (the second to the last in the equation) is defined at the second position(the second from the left) and so on. 

- The last operation $M_1$ (first from the left in the equation) is defined at the rightmost position in the diagram. When we want to aggregate all these operations into a single matrice, then we should follow the same order as we defined in the equation for the matrix multiplication of these unitary matrices. $M = M_1 M_2 … M_n$

Suppose we have a two qubit system $(X, Y)$. First we apply the Hadamard operation on the Y and then apply the controlled NOT operation on the X where the control bit is Y. Here the order of the operations and qubits in the circuit diagram are as follows.

![Alt text](./images/quantum_cir_ex1.png "a simple qunatum circuit")

Remember the measurement is also a kind of operation. So the measurements are defined using the measurement gates. The following diagram shows the measurement of the state of the qubits $X$ and $Y$. The action of measuring will measure the state of the qubits and save them into the classical bits $A$ and $B$.

![Alt text](./images/quantum_cir_ex2.png "a simple qunatum circuit with measurement gates")


### is density matrix formulation in quantum computing more general than quantum circuit model?

The density matrix formulation in quantum computing is more general than the quantum circuit model. The density matrix formalism allows for the description of mixed states, which are quantum states that cannot be described by a single pure state vector. This is important because in many practical scenarios, quantum systems are not in pure states due to interactions with the environment or measurement errors.

On the other hand, the quantum circuit model deals primarily with pure states and describes quantum computation as a sequence of unitary operations on these states. While the quantum circuit model is extremely useful for understanding and designing quantum algorithms, the density matrix formulation provides a more general and flexible framework for describing quantum states and operations, especially in the presence of noise and decoherence.


# Inner products, Orthonormal sets and Projective measurements

### What is inner product?

If we multiply a row vector with a column vector using the same rules as matrix multiplication, then it is called inner product. This is important because the inner product of a vector with itself will give us a square of Euclidean norm of that vector.

$$
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
$$


### What is othogonal set?

We say that two vectors are orthogonal when they are at right angle to each other or equivalently perpendicular to each other. For example if vectors $|\psi_1\rangle$ and $|\psi_2\rangle$ are orthogonal, then their inner product will be 0($\langle \psi_1||\psi_2\rangle = 0$).

An orthogonal set is a set of vectors where all the vectors are mutually orthogonal to each other. In other words for any two vectors $|\psi_i\rangle$ and $|\psi_j\rangle$ where $i \neq j$, the inner product $\langle \psi_i||\psi_j\rangle = 0$.


### What is orthonormal sets?

The set of vectors is called an orthonormal set, if the set is orthogonal and each vector in the set is a unit vector. In other words for any two vectors $|\psi_i\rangle$ and $|\psi_j\rangle$ from the set, if $i \neq j$, then the inner product $\langle \psi_i||\psi_j\rangle = 0$. If $i=j$, then $\langle \psi_i||\psi_i\rangle = 1$.


### What is orthonormal basis?

Suppose we have an orthonormal set S and vectors in the set S have been drawn from the vector space V of dimension n. if vectors in the set S spans the vector space V, then the set S is called orthonormal basis. For example the given below sets $S_1$ and $S_2$ are orthonormal basis of dimension 2 and 4 respectively.

$$
S_1 = \{ |+\rangle, |-\rangle \} \\
S_2 = \{ |\phi^+\rangle, |\phi^-\rangle, |\psi^+\rangle, |\psi^-\rangle \}
$$

Remember that the standard basis set of any dimension n is also a orthonormal basis of the vector space of dimension n.

### How to compute an orthonormal basis for any vector space V?

- We can use the Graham-Schmidt orthogonalization process to compute the orthonormal basis for any arbitrary vector space. The Graham-Schmidt orthogonalization process is a method used to compute an orthogonal (or orthonormal) basis for a subspace of a vector space. Given a set of linearly independent vectors that span a subspace, the process constructs an orthogonal (or orthonormal) set of vectors that also span the same subspace.

- For a vector space, the process can be applied to a set of linearly independent vectors that span the entire space to compute an orthogonal (or orthonormal) basis for that space.

- Note that input to this process will be set of n linearly independent vectors that span the vector space V and output will be the set of orthogonal vectors that span the vector space V.

- In a vector space of dimension n, any set of n linearly independent vectors will span the entire vector space. This is because a set of n linearly independent vectors in an n-dimensional space forms a basis for that space, and any vector in the space can be expressed as a linear combination of these basis vectors.

- The output of the Grahm-Schmidt orthogonalization process is the set of orthogonal vector. To get the orthonormal basis we have convert all the vectors in the set to the unit vectors. This can be easily done by dividing each vector in the set by it's Euclidean norm value.


### What is projection?




### How can we do the projective measurement?




# Limitations on quantum information


