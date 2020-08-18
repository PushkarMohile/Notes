---
output: 
  pdf_document:
    extra_dependencies: ["amsmath", "latexsym","babel", "amssymb","amsfonts"]
---

# Algebraic Topology
### Pushkar Mohile

## 1. General Topology
Topology speaks the language of open sets. We want to see how we can *break down* into constituent open sets and study its properties from those using continous functions.  
***Definition 1.1:*** A **topology** $\tau$ on a set $X$ is a family of subsets of $X$ such that  
1. Both $X$ and $\phi \in \tau$
2. Any union of elements in $\tau$ is in $\tau$
3. Any intersection of finitely many elements of $\tau$ is in $\tau$.  

The set $(X,\tau)$ is called a topological space. Elements of $\tau$ are called open sets. A subset $A$ of $X$ is called closed if $A^C$ the complement of $A$ wrt $X$ is in $\tau$.  
Note that a topology can be defined in general on any set of a space, not just a universal set we can construct.   

***Definition 1.2:*** A **cover** of a $X$ is a collection of sets whose union includes $X$ as a subset.   
If $C = \{U_\alpha: \alpha \in A \}$ is an indexed family of sets ($A$ is indexing set) $U_\alpha$ then $C$ is a cover of $X$ if $X\subseteq\bigcup_{\alpha\in A}U_\alpha$   

***Definition 1.3:*** A topological **basis** of $X$ is a  

***Definition 1.4:*** An **open cover** is a cover where every set in the cover is open. Each $U_\alpha \in \tau$  
Here the idea is that we want to describe the set using a topological basis.   

***Definition 1.5:*** A **refinement** of a cover $C$ of a set $X$ is a new cover $D$ such that every set in $D$ is contained in some set in $C$. $D = \bigcup_{\beta \in A} V_\beta$ where $V_\beta \subseteq U_\alpha$  
The notion of refinement is clearly *refining* the cover in that we are finding a cover that is in some sense smaller than the previous cover and is better able to cover the set with less sets.  

***Definition 1.6:*** A **subcover** of a cover is a refinement of that cover that omits sets contained in other sets of the cover.  
**Finish Subcover later with an example**  

***Definition 1.7:*** A space $X$ is called **Compact** if every open cover of $X$ has a finite subcover.  
This definition is quite abstract. However it reduces to several familiar property in special topological spaces. 
- In a metric space compactness is equivalent to saying that every sequence has a convergent subsequence. 
- A subset of $R^n$ is compact iff it is closed and bounded (Heine - Borel Theorem)  
A closed subset of a compact set is compact. However a compact space need not be closed except in Hausdorff spaces where compact spaces are closed which are more relevent in this document.  

**Theorem 1.1 (Heine Borel) :** A subset of $R^n$ is compact iff it is closed and bounded. This property does not hold in general for metric spaces or even cauchy complete metric spaces (Which is surprising to me). It would be useful to look into the exact machienary of $\mathbb{R}^n$ that makes this property hold. This theorem gives us a set of examples of compact spaces
- The ball $S_n$ given by $x_1^2 +x_2^2..+x_n^2 = 1$ in $R^n$
- The orthogonal group $O(3)$ in $R^9$
- The special unitary group $SU(n)$ in $\mathbb{C}^{n^2}$ or $R^{2n^2}$

***Definition 1.8*** A function $f: X \to Y$ is said to be **continous** if for every open set $A \in Y$ $f^{-1}(A)$ is an open set in $X$. Notice that this definition encompasses the usual definition of continuity I am used to in metric spaces: In that case we have to find an open neighbourhood around a point $x_0$ for every open ball $\rho(f(x),f(x_0)) < \epsilon$ in $Y$

***Definition 1.8*** Homeomorphism  

**Theorem:** If $X$ is a compact topological space, $Y$ is an arbitray Hausdorff space and $f: X \to Y$ is a continous surjection then 
1. $Y$ is compact. 
2. If $A$ is a closed subset of $X$ then $f(A)$ is a closed subset of $Y$. 
3. If $f$ is a bijection then $f$ is a homeomorphism from $X \to Y$  
   
(1) probably follows by making a finite subcover of $Y$ using a subcover of $X$ by using the fact that $f$ is continous (though I am not sure of this). (2) follows from (1) as a consequence of $Y$ being a Hausdorff space. (3) follows by proving $g = f^{-1}$ is a continous function.
The interesting idea that is building here is that we can make classes of spaces having some property if we can find continous maps between them.  

***Definition 1.9*** The **Lebesgue Number** of a cover of a metric space 