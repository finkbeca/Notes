---
title: Algebra
weight: 2
bookToc: true
katex: true


---

## Books
Algebra - Michael Artin  
Abstract Algebra; An Introduction


## Congrunce in {{<katex>}}  \mathbb{Z} {{</katex>}}
- {{<katex>}} a \equiv c (mod n) \implies [a] = [c] {{</katex>}}  
- Let  {{<katex>}} n > 1 {{</katex>}} be an integer and consider the congruence modulo n then it follows that if a is any integer and r is any remainder when a is divided by n then {{<katex>}} [a] = [r] {{</katex>}} furthermore there are n distinct congruence classes {{<katex>}} [0], [1],... [n-1] {{</katex>}}  
- The sum of two classes is the class containing both classes {{<katex>}} [a] \oplus [c] = [a + c] {{</katex>}}  
### Class Properties
- If {{<katex>}} [a] \in \mathbb{Z}_n ^ [b] \in \mathbb{Z}_n \implies [a] \oplus [b] \in \mathbb{Z}_n {{</katex>}}  
-  {{<katex>}}[a] \oplus ([b] \oplus [c]) = ([a] \oplus [b]) \oplus [c]   {{</katex>}}  
-  {{<katex>}} [a] \oplus [b] = [b] \oplus [a] {{</katex>}}  
- {{<katex>}} [a] \oplus [0] = [a] = [0] \oplus [a]  {{</katex>}}   
- {{<katex>}} \forall [a] \in \mathbb{Z}_n  {{</katex>}} the equation {{<katex>}} [a] \oplus X = [0] {{</katex>}} has a solution  
- If {{<katex>}} [a] \in \mathbb{Z}_n ^ [b] \in \mathbb{Z}_n \implies [a] \odot [b] \in \mathbb{Z}_n {{</katex>}}  
-  {{<katex>}}[a] \odot ([b] \odot [c]) = ([a] \odot [b]) \odot [c]   {{</katex>}}  
-  {{<katex>}} [a] \odot [b] = [b] \odot [a] {{</katex>}}   
- {{<katex>}} [a] \odot [1] = [a] = [1] \odot [a]  {{</katex>}}   
- {{<katex>}} [a] {{</katex>}} is a unit in {{<katex>}} \mathbb{Z}_n {{</katex>}} iff {{<katex>}} (a,n) = 1 \in \mathbb{Z} {{</katex>}}  

## Rings
- A ring is a nonempty set R equipped with two operations usually written as addition and multiplication that satisfy the following:
- {{<katex>}} a \in R \land b \in R \implies a + b \in R {{</katex>}}  
- a + (b+c) = (a+b)+ c  
- a+ b = b + a  
- There is {{<katex>}} 0_R \in R | a + 0_R = a = 0_R + a{{</katex>}}  
- {{<katex>}} \forall a \in R, a + x = 0_R{{</katex>}} has a solution  
- If {{<katex>}} a \in R ^ b \in R \implies ab \in R {{</katex>}}  
- a(bc) = ab(c)  
- a(b+c) = ab+ac ^ (a+b)c = ac+bc
A ring without identity is known as a rng. 
- **An Integral domain** is a commutative ring R with identity {{<katex>}} 1_R \neq 0_R{{</katex>}} where given {{<katex>}} a,b\in R ab - 0_R \implies a = 0_R \lor b = 0_R{{</katex>}}  
- **A field** is a commutative ring R  {{<katex>}} 1_R \neq 0_R{{</katex>}} where each {{<katex>}} a \neq 0_R  {{</katex>}} the equation ax =1 has a solution in R  
- (r,s) + (r', s' ) = (r + r' , s + s') and (r,s)(r', s') = (rr', ss')   
-  {{<katex>}} \mathbb{Z} {{</katex>}} is a subring of the ring  {{<katex>}} \mathbb{Q} {{</katex>}} of rational numbers and  {{<katex>}} \mathbb{Q} {{</katex>}} is a subring and subfield and of the field  {{<katex>}} \mathbb{R} {{</katex>}} as  {{<katex>}} \mathbb{Q} {{</katex>}} itself is a field. Simiarly  {{<katex>}} \mathbb{R} {{</katex>}} is a subfield and subring of the field  {{<katex>}} \mathbb{C} {{</katex>}}  
- Suppose that R is a ring and that S is subset of R then S is closed under addition and multiplication, it contains a zero element and  given an a element in S, a + x = 0 has a solutuion that is in S. Thus S is a **Subring**.  
- Another definition is let S be a nonempty subset of a ring R if S is closed under subtraction and multiplication then S is a subring of R.  
- An integral domain contains no zero divisors. 
- Every field is an integral domain  
- Every finite integral domain R is a field  
- A ring R is isomorphic to a ring S if there exists a bijective function between the two and if {{<katex>}} f(a+b) = f(a) + f(b) {{</katex>}} and  {{<katex>}} f(ab) = f(a)f(b) {{</katex>}}  
- Let R and S be rings then a function is said to be a homomorphism if  {{<katex>}} f(a+b) = f(a) + f(b) {{</katex>}} and  {{<katex>}} f(ab) = f(a)f(b) {{</katex>}}    
- If F: R to S is a homomorphism of rings then {{<katex>}} f(0_R) = 0_S {{</katex>}}, {{<katex>}}f(-a) = f(a) \forall a \in R {{</katex>}}, {{<katex>}} f(a-b) = f(a) - f(b) \forall a \in R {{</katex>}}  
- If R is a ring with identity and f is surjective then S is a ring with identity f(1) whenever u is a unit in R then f(u) is a unit in S and {{<katex>}} f(u)^{-1} = f(u^{-1}) {{</katex>}}  
- The property of being a commutative ring is preserved by isomorphism. Therefore no commutative ring can be isomorphic to a noncommutative ring.   

## Groups

A group is a nonempty set G equipped with a binary operation * that satisfies the following axioms:  
- Closure   
- Associativity  
- There exists an element in a group G known as the identity such that {<katex>}} a \dot e = a = e \dot a {{</katex>}}  
- There exists an inverse for a group st {<katex>}} a * d = e  {{</katex>}} and {<katex>}} d * a = e{{</katex>}}  
A group is abelian if it is commutative (a * b = b * a) 
- A group G has a unique identity element, a unique inverse, and cancelation holds.
- if G is a group then {<katex>}} (ab)^{-1} = b^{-1}a^{-1} {{</katex>}}  and (a^{-1})^{-1} = a
- A subset H of a group G is a subgroup of G if H itself a group under the operation in G  
- Let G and H be groups with the group operation by *. G is isomorphic to a group H if there exists a bijective function from G to H that also preserves the property  {<katex>}} f(a * b) = f(a) * f(b) {{</katex>}}   
- Let G and H be groups, a function is said to be a homorphism if {<katex>}} f(a * b) = f(a) * f(b) {{</katex>}}   
- Let K be a subgroup of a group G. Then the relation of congruence modulo K is reflexive, symmetric, and transitivity.     
- Let K be a subgroup of a group G then {<katex>}} a \equiv c (mod K)  {{</katex>}} iff {<katex>}} Ka = kc{{</katex>}}   
- If G has a n order then G is isomorphic to {<katex>}} \mathbb{Z}_2 {{</katex>}} this follows all the way to when G has an order of 7  
- a subgroup N of a group G is said to be normal if Na = aN for every a in G.   
- Let N be a normal subgroup of a group G then if Na = nc and Nb = Nd in G/N then Nab = Ncd.  
- Let N be a normal subgroup of a group G then G/N is a group under the operation defined by (Na)(Nc) = Nac  
- If G is finite then the order of G/N is |G|/|N|  
- If G is abelian group then so is G/N  
The group G/N is called the quotient group or factor group of G by N.  
- Ka + Kb = K(a+b) is the same as [a]+[b] = [a + b]  
- Let {<katex>}}f: G \rightarrow H{{</katex>}} be a homomorphism of groups. Then the kernel of F is the set {<katex>}} {{</katex>}}   
- Let {<katex>}}f: G \rightarrow H {{</katex>}} be a homomorphism of groups with kernel K. Then K is normal subgroup of G.  
- The kernel of a homomorphism f measures how far f is from being injective.   
- Let {<katex>}}f: G \rightarrow H {{</katex>}} be a group homomorphism with kernel K. Then f(a) = f(b) iff Ka = Kb.  
-Let {<katex>}} f: G \rightarrow H {{</katex>}} be a surjective homomorphism of groups with kernel K. Then the quotient group G/K is isomorphic to H.  

