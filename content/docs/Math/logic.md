---
title: Logic
weight: 2
bookToc: true
katex: true


---
Notes from Logic: The Laws of truth  

# Propositional Logic Notes

- A word token is a physical thing , a string of pencil marks, illuminated pixels, etc.  
- A word type is an abstract object with no size or duration. Its istances are word tokens and have some length but the type itself does not. An example of this is the sentence "Alice's word is smudged" the word that is smudged is an example of a word token while the word being produced is a word type.  
- Similarly a sentence type are abstract objects. There instances are sentence tokens which do have length and size and are made of an arragnment of information in some physical context  
- One sentence type can be used to express different propositions, depending on the context of utterance. Generally, Identify propositions with sentence type.  
- Proposition:a claim about how things are; it represent the world in some way. It is true if things are the way it represents.  
- Propositions are claims about the word; expressed by setences uttered in context but are not identical with sentence types or tokens.  
- Argument: a sequence of propositions. We call the last proposition in an argument the conclusion.  
- We identify the conclusion as the proposition that the speaker is trying to establish -- to give reason for -- and the premises as the reason given to support the conlsuion.  
- Conclusions in ordinary reasoning incude "therefore", "hence", "thus", "so" and "it follows". Phrases that commonly indicate premises include "because", "since" and "given that".  
- We count any sequence of one or more propositions as an argument. 
- When it is impossible for the premises to be true and the conclusion false we call this necessary truth preservation (NTP) and we can call an a- rgument with this property property necessarily truth preserving (NTP).  
- If an argument is NTP by virtue of its form or structure we call it valid and we say that the conlsuion is a logical consequence of the premises. There are two aspects to validity:  
1. Premises cannot be true while the conclusion is false (NTP)  
2. The form or structure of the argument guarantees that it is NTP.  
- Truth of premises does not guarantee the truth of the conclusion. It only makes the conclusion highly probable.
- An argument is valid if it is NTP by virtue of its form and the goal of finding a method of assesing arguments for validity that can be applied to any argument, no matter what its subject matter.  
- We say an argument is sound if it is valid and in addition has premises that are in fact true. (sound = valid + all premises true).  
- We say an argument is valid if its strcture guarantees that it is a NTP.  
- We divide propositions into two kinds:
1. Basic propositions: propositions having no parts that are themselves propositions.  
2. compound propositions: propositions made up from other proposition and connectives.  
### Connectives: Negation, Conjunctions, Disjunctions, Conditional, Biconditional 
- a connective is truth functional if it has the property that the truth or falsity of a compound proposition formed from the connective and some other propositions is completed determined by the truth of falsity  of those component propositions.
- negation: if the negand is true, the negation is false and vise versa.  
- negation is a truth-functional connective.  
- conjunction and disjunction are both truth functional connectives: to know whether a disjunction/conjunction is true or false you need only know whether the disjucts are true or false.  
- A conditional proposition of this form has two components and claims that if one is true then the other is true too. We call the formed the antecedent and the latter component the consequent. The compound proposition is known as a conditional.  
- The consequent is the component that might be true even if the other component is not true; the antecedent is the component that cannt be true without the other components also being true. 
## Language of Propositional Logic 
- Glossarys can be used to denote between PL and English. Though this glossary does not have to be use in forever but can be changed. 
- The sentences of PL are called Wffs (Well Formed Formulas).   
- Wffs of PL are defined as follows:  
1. Any basic proposition  is a wff  
2. If a and B are wffs then so are (\neg A, A and B, A or B, if A then B, iff A then B  
3. Nothing else is a wff  
- If a given string of symbols is a wff, it must be constructible in accordance with the recursive definition given above.  
Polish notion is another way to write wffs, instead of A ^(and) B becomes ^(and)A B.  
Note: In certain areas of logic you may want a finite set of basic symbols, this is considered an alphabet.  
## Connectives  
- Maxims of Quantity:  
1. Make your contribution as informative as required  
2. Do not make your contributions more informative than required
- Maxim of Quality:  
1. Try to make your contribution one that is true
- Maxim of Relation:  
1. Be Relevant  
- Maxim of Manner:  
1. Be Persciuos  
2. Be Orderly  
3. Be brief  
4. avoid ambiguity  
5. avoid obscurity  
- What is said; We try to capture what is said when translating english to PL.  
- What is implied; The logical consequences from the propsotions expressed.  
- What is implicated; roughly speaking the implicatures are the things that follow from the assumpetion that the utterance is correct.  
- Non-classical logic that includes nontruth functional connectives (Look into!)  
- "A and B" and "A but B" while both translating into a conjunction connective, "A but B" has an implicature that "A and B" lacks.   
- The "then conditional"/ \arrow / conditional connective is know as the material connective.  
- If someone utters "if A then B" then it follows that she is not confident that A is true nor that B is true  
- "P unless Q" means that if Q is not true, P is true  
### If without conditional
- "There are biscuits on the sideboard if you want them" is an exampe of a biscuit conditional, which is not translated from english into PL as a material conditional. 
- "or" in english is ambiguous; sometimes it expresses inclusive disjunction and sometimes exclusive disjunction:
1. Inclusive disjunction is "A or B" is true iff at least one.  
2. Exclusive disjunction is "A or B" is true iff exactly one.  
Note: Some books seperate Inclusive and Exclusive disjunction through different symbols but this is not common.  
- An argument is valid iff there is no row in their joint truth table in which the propositions are true and the outcome is false.  
- A formula a is a tautology or logical truth iff it is true on every row of its truth table.  
- a formula is satisfiable iff it is true that on some row of its truth table.    
- Truth tables are one way to test for validity another method for doing this is trees  
- Truth tables provide an analysis -- a fundamental definition of logic contions as well as provide a method of testing for - 
each of these notions.  
## Trees
- Models provide analyses of central logic notions bet they do not provie test for these notions.  
- The basic purpose of a tree is to tell us whether a given set of propositions is satisfiable; that is whether all propositions in the set can be true.  
- Each rule takes one proposition as input and gives one or more propositions as output.  
1. The output propositions are simpler than the input proposition; in particular the main connective of the input is eliminated.  
2. The out put proposition must be true, assuming that the input proposition is true.  
- To test whether an argument is valid:  
1. Start the tree with the premises and the negation of the conclusion
2. If all paths close, the argument is valid  
3. If a path remains open the argument is invalid. Read off from an open path a scenario in which the premises are turth and the conclusion is false.  
(Note Path is one branch of the tree)  
- To test whether a proposition a is a tautology:  
1. Start with the negation not A  
2. If all paths close, A is a tautology  
3. If a path reminas open a is not a tautology. Read off from an open path a scenario in which A if false.   
- To test whether two propositions a and b are equivalent:  
1. Start the tree with the negate bicondition
2. If all paths close a and b are equivalent  
3. If a path remains open a and b are not equivalent . Read off from an open path a scenario where a and b have different truth values.  
- To test whether a proposition is satisfiable  or a contradiction:  
1. Start the tree with the proposition  
2. If all paths close, the proposition is a contradiction  
3. If a path remains open, the proposition is satisfiable  
- To test whether a set of propositions is satisfiable:
1. Start the tree with the propositions in the set.
2. If all paths close the set is unsatisfiable.
3. If a path remains open, the set is satisfible.
# Predicate Logic  



 


