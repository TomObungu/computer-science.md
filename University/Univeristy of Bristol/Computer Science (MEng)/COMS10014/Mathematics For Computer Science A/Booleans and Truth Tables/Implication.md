Informally, the implication operator encodes statements of the form "If X then Y". 

For example, if it is past 5pm then it is time to work. We will write $p\implies q$ to express implication between two Booleans or propositions $p$ and $q$. The first argument of an implication is called the antecedent and the second argument to right of the arrow is called the consequent. 

The behaviour of this function can determine based on the truth values of the antecedent and the consequent. If the antecedent is true, then the implication evaluates to true just if the consequent is also true. Otherwise, if the antecedent is false, the implication evaluates to true regardless of wether the consqeuence it true or not. 

Material implication in propositional logic and the way we naturally understand "if... then..." in ordinary language differs. 

The key is that, in propositional logic "if $p$, then $q$" does not mean "$p$ is the condition that must currently be true". It means  something more like:
	"The is no case where $p$ is true and $q$ is false"

Essientially $p\implies q$ makes on promsise: Whenever $p$ occurs, $q$ must also occur. This is why $p\implies q$ is false when $p$ is true and $q$ is false as it breaks the whole premesis of above clause. 

| p      | q      | $p\implies q$ |
| ------ | ------ | ------------- |
| $\top$ | $\top$ | $\top$        |
| $\top$ | $\bot$ | $\bot$        |
| $\bot$ | $\top$ | $\top$        |
| $\bot$ | $\bot$ | $\top$        |

# Vacuous Truth
If the antecedent is always false, then the implication is vacuously true. For example if the statement is "If pigs can fly, then it is time to finish work". As pigs cannot fly the boolean statement always evalutes to true and thus it's time to

| p      | q      | $p\implies q$ |
| ------ | ------ | ------------- |
| $\bot$ | $\top$ | $\top$        |
| $\bot$ | $\bot$ | $\top$        |
## Associativity
Implication is not associative. By convetion $p\implies q\implies r$ is read as
$$
p\implies(q\implies r)
$$
