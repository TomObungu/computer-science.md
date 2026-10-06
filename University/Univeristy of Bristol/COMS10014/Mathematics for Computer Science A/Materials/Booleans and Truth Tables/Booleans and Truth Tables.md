# Propositions and Booleans
A proposition is simply a statment or condition that is either true or false. True and false are Boolean values, they represent the truth value of a proposition or the answer to a propositional question. 

There are various notations for Boolean values such as $1$ for true and $0$ for false and $\top$ for true and $\bot$ for false. You could even do $T$ for true and $F$ for false. 


# Boolean Operators and Truth Tables
Propositions can be comprised of several smaller propositions. It is possible to express various configurations of this application using truth tables. 
Truth tables capture the possible behaviour of a function actingon Boolean values. Truth tables describe the output values for all possible inputs.  

Consider a truth table that express the statement of "The dark mode  option is selected and it is past 5pm". If these statments are both true simulatnously, then night mode is turned on. It is possible to express the various configurations of this application by the table in Figure 1.

| Night Mode Option? | Past 5pm | Night Mode |
| ------------------ | -------- | ---------- |
| $\bot$             | $\bot$   | $\bot$     |
| $\bot$             | $\top$   | $\bot$     |
| $\top$             | $\bot$   | $\bot$     |
| $\top$             | $\top$   | $\top$     |


## Conjunction
The conjunction operator i.e logical "and" encodes the fact that both sub-propositions must be true. It only ever returns true when both inputs are true as in final line of truth. 

## Disjunction
The disjunction operator i.e logical "or" return true if either sub-propositions are true. It is possible to write $p \lor q$ to expression the disjunction of two Booleans or propositions $p$ and $q$, which are reffered to as the disjuncts. 

# Negation
The negation operator i.e logical "not" evaluates to the opposite of its input. Turning true into false and vice versa. It is expressed as $¬p$ . This operation corresponds to the English connective word "not". 

# Implication 
Informally, the implication operator encodes statements of the form "If X then Y". For example, if it is past 5pm then it is time to work. We will write $p\implies q$ to express implication between two Booleans or propositions $p$ and $q$. The first argument of an implication is called the antecedent and the second argument to right of the arrow is called the consequent. 

The behaviour of this function can determine based on the truth values of the antecedent and the consequent. If the antecdent is true, then the implication evaluates to true just if the consequent is also true. Otherwise, if the antecedent is false, the implication evaluates to true regardless of wether the consqeuence it true or not. 

Material implication in propositional logic and the way we naturally understand "if... then..." in ordinary language differs. 

The key is that, in propositional logic "if $p$, then $q$" does not mean "$p$ is the condition that must currently be true". It means  something more like:
	"The is no case where $p$ is true and $q$ is false"



