---
title: Algebra
weight: 2
bookToc: true
katex: true


---

## Books
Algebra - Michael Artin  
Abstract Algebra; An Introduction


## {{<katex>}} Congrunce in \mathbb{Z} {{</katex>}}
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

