# Quantum Circuits

### What is Circuit model?

- In the classical world one of the fundamental ways of representing classical computation is using boolean circuits model. There are some other theoretical models for classical computation such as Turing machine model. 

- Due to the fact that the circuit model is more close to how we implement these logics using hardware, the circuit model is more fundamental than turing machine model.

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

Quantum circuits can be implemented using quantum gates(Similar to boolean gates). For example the Hadamard gate is a quantum gate that can compute the Hadamard operation on a quantum state. 


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

We say that two vectors are orthogonal when they are right angle to each other or equivalently perpendicular to each other. Suppos the vectors $|\psi_1\rangle$ and $|\psi_2\rangle$ are orthogonal then their inner product will be 0. That means $\langle \psi_1||\psi_2\rangle = 0$.

We say that the set of vectors are orthogonal set when all the vector are mutually orthogonal to each other. In other word for any two vectors $|\psi_i\rangle$ and $|\psi_j\rangle$ where $i \neq j$, the inner product $\langle \psi_i||\psi_j\rangle = 0$.


### What is orthonormal sets?

The set of vectors is called orthonormal set, when the set is orthogonal and each vector in the set is a unit vector. In other word for any two vectors $|\psi_i\rangle$ and $|\psi_j\rangle$,if $i \neq j$, then the inner product $\langle \psi_i||\psi_j\rangle = 0$. If $i=j$, then $\langle \psi_i||\psi_i\rangle = 1$.


### What is orthonormal basis?

Suppose we have a orthonormal set of vectors S and vectors in the set S has been drawn from the vector space V of dimension n. if vectors in the set S spans the vector space V, then the set S is called orthonormal basis. The given below sets $S_1$ and $S_2$ are orthonormal basis of dimension 2 and 4 respectively.

$$
S_1 = \{ |+\rangle, |-\rangle \} \\
S_2 = \{ |\phi^+\rangle, |\phi^-\rangle, |\psi^+\rangle, |\psi^-\rangle \}
$$

Remember that the standard basis set of any dimension n is also a orthonormal basis of the vector space of dimension n.


### What is projection?




### How can we do the projective measurement?




# Limitations on quantum information


