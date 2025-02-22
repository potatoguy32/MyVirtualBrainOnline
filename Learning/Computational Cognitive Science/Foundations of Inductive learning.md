## Questions
- What forms does our knowledge of the world take?
- What is intelligence?
	- Learn to repeat after observation - Currently what ML/AI does
	- Set the understanding of a universe from a set of observations - What humans do
- What are the inductive principles leading to new knowledge from interactions with observed data?
- What kind of data must be available for learning and what kind of innate knowledge (if any) must they have?

## Deduction and Induction
- Deductive reasoning:
	- Conclusions made based on known information with certainty.
	- Arguments are objective evaluations and independent from other variables
- Inductive reasoning:
	- Conclusions generalizing from the available (limited) information with certain probability
	- Arguments are subjective, evaluations depend on other knowledge.
	- Induction relies on prior subjective knowledge

## Notes on induction
- We rely in [[uniformity of nature]], after additional knowledge is added, we might change our postures.
- Check [[the problem of induction]] for a cool explanation on induction.
- We can’t learn abstractions from data if in some sense we didn’t already know what to look for. 
- All inductive learning seems to require the constraints of a hypothesis space
- Fodors' critique:
	- "This isn’t really concept learning, it’s just belief fixation".
	- Since we are starting from assumptions and hypotheses the learner already has the concept, and is just forming a new belief about how to respond on particular situations.

## Causal theories
- "Good" hypotheses are based on entrenched predicates.
- A predicate becomes more entrenched as it supports more and more successful inductions in the past
- Theories come from hypotheses supported by experience 
- What is a theory, formally?
- How often are theories learned?

## [[Marr's three levels]]
1. Computational theory:
	- What is the goal of the computation? What is the logic by it is carried out?
1. Representation and algorithm
	- How is information represented and processed to achieve the computation's goal?
2. Hardware implementation
	- How is the computation realized in physical or biological hardware?

## Probably Approximately Correct (PAC)
Main ideas:
- We don't need to wait until infinity happen to be sure something is true, we just need to be confident enough and approximate as much as possible to the true value.
- Does learning succeed under weaker conditions? 

What we get from [[PAC theorem]]:
- As allowable error decreases, N increases
- As desired confidence increases, N increases
- As the space of hypothesis space increases, N increases

The role of [[Inductive bias]]:
- Inductive bias = constrains on hypotheses.
- Learning without bias is impossible
- Inductive bias lead to simpler arguments by induction -> PAC result
- Learning naturally happens with conjunctions better than with disjunctions.

