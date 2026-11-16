In the essence, the mathematical discipline of probability is about how uncertainty in the world around is interpreted. It is as the heart of statistic, AI, machine learning, quantum physics and modern theory of algorithms. 

As with much of mathematics, probability relies heavily on the art of translating real-world situations into mathematical models.

# Sample Spaces  & Events
Consider the notion of sample spaces and events. These are not new concepts but simply names we use when working in the context of probability. 

A sample space $\Omega$ is simply a set. The elements of a sample space are referred to as it's outcome. For example consider the sample space of rolling a dice:
$$
\Omega = \{1,2,3,4,5,6\}
$$
An event is a collection of outcomes. Consider the event of rolling only odd numbers.
$$
E_{1} = \{1,3,5\}
$$
Consider another event of rolling even numbers only:
$$
E_{2} = \{2,4,6\}
$$
An event is a subset of the sample space, i.e $E \subseteq \Omega$. We can use probability notation to describe the outcomes:

- $E_{1} \cap E_{2}$ means both events occured simulatenously
- $E_{1} \cup E_{2}$ means either events occurs
- $E_{1} \setminus E_{2}$ means $E_{1}$ occured but $E_{2}$ did not

If $E_{1} \cup E = \phi$, then it means $E_{1}$ and $E_{2}$ are mutually exclusive and cannot occur at the same time. 


# Probability Space
The probability space is subset of outcomes. The probability space sums into one $P(\Omega)=1$. Thus, $P : P(\Omega) \to|[0,1]$. For example consider the probability of tossing a coin: $\Omega = \{H,T\}$,

- $\Omega = P(\{H\} + \{T\})$
- $P(\{H\})=1$ would be impossible and  $P(\{T\})=1$ would be impossible. As they are mutually exclusive events. Showing this would mean $\Omega = P(\{H\} + \{T\}) = 1+1 = 2 \neq 1$ which is a contradiction as $P(\Omega)=1$.


# Uniform Distribution 
All outcomes are equally likely. This would mean $(\Omega, P)$ where $P : P(\Omega)\to [0,1]$ such that $P(\{x_{1}, x_{2}\})= P(\{x_{1}\}) + P(\{x_{2}\})=P+P$. 

This would mean $P(E)=\frac{|E|}{|\Omega|}$.  Dividing by $|\Omega|$ is like a normalisation factor. Think of it finding the outcome out of a total space. 

## Example 
Consider two dices that are 6-sided $2d6$. Let's consider the probability that they sum to 4. 

The probability space would be $\Omega= \{1,\dots,6\}\times\{1,\dots,6\}$. 
The event $E$ would be $E=\{(x,y) | x + y = 4\}$. This would be $\{(1,2), (2,2),(3,1)\}$.

Thus the probability of $E$ would be $P(E)=\frac{|E|}{|\Omega|} = \frac{3}{36}=\frac{1}{12}$.

### Indistinguishable Dice 
Consider the case of when the dice are unlabelled. This would mean $\Omega = \{X \subseteq \{1, \dots, 6\} |1 \leq |X| \leq 2\}$. The case 

