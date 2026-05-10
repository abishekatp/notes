## How does the partial operations and measurements affects the entangled systems?

> - Remember that a measurement is also a kind of operation. Also be noted that as soon as we measure one of the entangled systems the whole system will collapse into the resulting outcome. After that any number of measurements on the system will result in a same outcome.
> - We know that the measurement could not in any way affect the probability outcome of the system. The measurement outcome only depends on the quantum state. By simulating the same state and measuring it multiple times will give us some intution towards the probability outcome of that state.
> - Applying some operation to just one part of the entangled systems will alter the probability outcome of the the whole entangled system, but no operation can be applied to just one part of the entangled systems to always(100 percent of the times) get the same outcome for the whole entangled system without destroying the entanglement. We will see one example for each of these cases below.  


### If we apply some operation to just one(or proper subset) of the entangled systems and do nothing to the remaing system, then what will happen?

It will affect the probability outcome of the whole system as long as that operation does not destroy the entanglement itself.

> - Assume that there are two qubits that are in an entangled state like $|\phi_+ \rangle$ state. Alice has one qubit and Bob has another qubit in a far away location. If Alice applies the following unitary operation $U$ on her qubit. This operation will maximise the probability outcome of $|1\rangle$ to be more than 99 percent. will it affect the probability outcome of Bob's qubit?

When two qubits are entangled in a state such as $|\phi^+\rangle$, the entanglement implies a strong correlation between their states. The $|\phi^+\rangle$ Bell state is given by:

$$ 
|\phi^+\rangle = \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle) 
$$

$$
U = \begin{pmatrix}
\sqrt{\frac{1}{200}} & 0 \\ \\
\sqrt{\frac{199}{200}} & 1
\end{pmatrix}
$$

In this state, if Alice and Bob each have one qubit, and they are far apart, their joint state is described as being either both in $|0\rangle$ or both in $|1\rangle$, with equal probability. Now, let's consider what happens when Alice applies a $U$ operation to her qubit.

1. The original state is $|\phi^+\rangle = \frac{1}{\sqrt{2}} (|00\rangle + |11\rangle)$.

2. Alice applies a unitary operation $U$ to her qubit:
   
$$
\begin{equation}\tag{Ex-18}
\begin{split}

U|\phi_+ \rangle 
&= \begin{pmatrix}
\sqrt{\frac{1}{200}} & 0 \\ \\
\sqrt{\frac{199}{200}} & 1
\end{pmatrix}
\left(
\begin{pmatrix} 
    \frac{1}{\sqrt{2}} \\ 0 
\end{pmatrix} +
\begin{pmatrix} 
    0 \\ \frac{1}{\sqrt{2}} 
\end{pmatrix}
\right) \\

&= \left(
 \begin{pmatrix} \sqrt{\frac{1}{400}} \\ \sqrt{\frac{199}{200}} \end{pmatrix} +
 \begin{pmatrix} 0 \\ \sqrt{\frac{1}{2}} \end{pmatrix}
\right) \\

&= \left(
 \begin{pmatrix} \sqrt{\frac{1}{400}} \\ \sqrt{\frac{199}{200}} \end{pmatrix}
\right) \\


\end{split}
\end{equation}
$$


>***Important:*** The property of changing probabilities in one part of an entangled(or correlated) system affecting another part due to quantum entanglement is unique to quantum mechanics and does not have a direct analog in classical, non-quantum correlated systems. So if there are two classical bits that are correlated and we apply some operation on the first classical bit, then that doesn't change the probability outcome of the other classical bit. But in case of quantum bit(qubit) applying some operation on the first qubit will change the probability outcome of the second qubit.