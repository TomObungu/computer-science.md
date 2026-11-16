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
