
# Classical Information(Multiple systems)

* As in a classical single system, In the multiple systems case also we will first see about the classical information and then go onto the quantum information in the next blog.


## What does the multiple systems mean?

* We have seen previously that the single system can represent some information using its classical states. For example we have seen torch light example with the classical states $\Sigma$ = {OFF, ON} and more formal single system was a Bit with classical states $\Sigma$ = {0, 1}.

* These single systems can have finite non empty set of classical states. This means using any particular classical system we can only represent finite amount information. And also If you think about our world, it is made up of many complex systems. So how can we mathematically reprsent these complext systems so that we can process those information using devices like computers.

* For example, in the blog about single system and specifically in the torch light example, we have used  classical systems with the following classical state sets individually:
 $$\Sigma _1 = \{ OFF, ON \}$$  
 $$\Sigma _2 = \{ LOW, HIGH \}$$ 

* In this blog we will see how we represent the torch light as the combination these two individual systems. Here $\Sigma _1$ represents the on-off state of the torch light and $\Sigma _2$ represents the brightness of the torch light. So we need way of mathematically representing these single systems together.

* Practically these individual systems together represents a complex system torch light. In the above case this complex system is formed by two individual systems $\Sigma _1$ and $\Sigma _2$. But in general the complex or multiple systems can be formed by any number individual systems.

* So the multiple system is a combination of single systems together representing the complex system. Here multiple single systems comes together to represent the complex information about the complext systems.

> Remember that any particular complex system can be considered as a single system itself. Later which can be part of more complex system. So at the end the terms Single or Mulitple is differtiated by only how do we think about a particular system. For example think of this torch light attached to more complex system like motor bike(like an head light). Now we can think of the torch light as a single system that is part of the more complex system like motor bike.


## How do we represent multiple systems mathematically?

* So we have said that multiple system is formed by two or more individual systems. If each individual system has its own associated classical states, then the multiple system is represented by a cartesian product of classical state sets of these individual systems.

* For example In our torch light example we had two individual $\Sigma _1$ and $\Sigma _2$. We can represent a classical states of a torch light using the cartesian product of these individual system as follows. 

$$\Sigma = \Sigma _1 \times \Sigma _2 = \{ (OFF, LOW), (OFF, HIGH), (ON, LOW), (ON, HIGH)\}$$

* If you think that torch ligh has two switches one switch to make the torch light and ON or OFF and another one to make brightness HIGH or LOW, then here (ON, LOW) is one of the possible classical state of the torch light, where torch light is ON and its brightness is set to LOW. 

#### Cartesian Product

* If you think more formally the cartesian product takes each element of any set $\Sigma _1$ and pair it with each element of another set $\Sigma _2$. We can formally define this as follows,

$$\Sigma_1 \times \Sigma_2 = \{ (a,b) : a \in \Sigma_1 \; and \; b \in \Sigma_2 \}$$

* We can generalize this idea to n number of classical systems each associated with finite non empty classical state sets as follows.

$$\Sigma_1 \times \Sigma_2 \times ... \times \Sigma_n = 
\{ (a_1, a_2,...,a_n) :  a_1 \in \Sigma_1 ,\; a_2  \in \Sigma_2 ...a_n \in \Sigma_n \}$$

* We got the all possible combination of classical states of multiple systems. We used column vector to represent a state of the single system similarly here also we will use a column vector to represent a classical state of the complex sytem. For example the classical state of the torch light that is ON and with LOW brightness can be represented by the following column vector(the entry that corresponds to each classical state is labeled side by side).

$$ |light\rangle = 
\begin{pmatrix} 0 \\ 0 \\ 1 \\ 0\end{pmatrix} 
\begin{matrix} \rightarrow (OFF, LOW) 
\\  \rightarrow (OFF, HIGH) \\ \rightarrow(ON, LOW) \\ \rightarrow(ON, HIGH)\end{matrix}$$

* Here each entry corresponds to one of the classical state of the multiple system.


## How do we reprsent the probabilistic state of the classical system?

* Similar to the classical state of the multiple system we also represent probabilistic state of the multiple system using the column vector. Here each eantry in the probability associated with the classical state that corresponds to that particular entry. 

* Here instead again taking the same example as torch light we will take an classical system Bit.




### What is Tensor Product?