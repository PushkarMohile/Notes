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

**Theorem 1.1 (Heine Borel) :** A subset of $\R^n$ is compact iff it is closed and bounded. This property does not hold in general for metric spaces or even cauchy complete metric spaces (Which is surprising to me). It would be useful to look into the exact machienary of $\mathbb{R}^n$ that makes this property hold. This theorem gives us a set of examples of compact spaces
- The ball $S_n$ given by $x_1^2 +x_2^2..+x_n^2 = 1$ in $\R^n$
- The orthogonal group $O(3)$ in $\R^9$
- The special unitary group $SU(n)$ in $\mathbb{C}^{n^2}$ or $\R^{2n^2}$

***Definition 1.8*** A function $f: X \to Y$ is said to be **continous** if for every open set $A \in Y$ $f^{-1}(A)$ is an open set in $X$. Notice that this definition encompasses the usual definition of continuity I am used to in metric spaces: In that case we have to find an open neighbourhood around a point $x_0$ for every open ball $\rho(f(x),f(x_0)) < \epsilon$ in $Y$

***Definition 1.8*** A **Homeomorphism** is a function $f$ between 2 topological spaces such that both $f$ and $f^{-1}$ are both continous is a homeomorphism (Not to be confused with homomorphism). Homeomorphisms are isomorphisms in the category of topological spaces **Top**

**Theorem:** If $X$ is a compact topological space, $Y$ is an arbitray Hausdorff space and $f: X \to Y$ is a continous surjection then 
1. $Y$ is compact. 
2. If $A$ is a closed subset of $X$ then $f(A)$ is a closed subset of $Y$. 
3. If $f$ is a bijection then $f$ is a homeomorphism from $X \to Y$  
   
(1) probably follows by making a finite subcover of $Y$ using a subcover of $X$ by using the fact that $f$ is continous (though I am not sure of this). (2) follows from (1) as a consequence of $Y$ being a Hausdorff space. (3) follows by proving $g = f^{-1}$ is a continous function.
The interesting idea that is building here is that we can make classes of spaces having some property if we can find continous maps between them.  

***Definition 1.9*** **(The Lebesgue Number of a cover):** Given an open cover $\{ G_\alpha \}$ of a metric space $X$, the Lebesgue number for the covering is a positive number $\epsilon$ such that every ball of radius $\epsilon$ is contained in some member $G_\alpha$ of the cover.  
Recall that this covering consists of open sets so there is no weird stuff happening at the boundaries of those sets.  

**Theorem:** Every covering of a compact metric space has a Lebesgue number.  
The idea here is that because the set is compact, we can *fit* in balls smaller than a certain radius. The proof involves assuming that there is no Lebesgue number, constructing a sequence of points $\{ x_n\}$ such that a ball of radius $\frac{1}{n}$ isn't contained in any $G_\alpha$. As the set is compact we can find a convergent subsequence to a point $p\in X$. Choose an $\alpha$ so that $p \in G_\alpha$. Further choose a $\delta$ such that the ball of radius $\delta$ around $p$ is contained in $G_\alpha$. Take $n$ large enough so that $\frac{1}{n} < \frac{\delta}{3}$ We then find a point $y_n$ which belongs to the ball around $x_n$ that doesn't belong to any $G_\alpha$ (Since the ball isn't contained in $G_\alpha$ there must be one element of the ball not in any $G_\alpha$). Now, because $X$ is a metric space,
$$ d(p,y_n) \leq d(p,x_n) + d(x_n,y_n) < \frac{2\delta}{3} < \delta $$ 
Hence $y_n$ belongs to the ball around $p$ and is hence contained in $G_\alpha$ contradicting our earlier assumption.  

***Definition 1.10*** A limit point $p$ of a set $A$ in a topological space $X$ is a point such that every neighbourhood of that point has a nonempty intersection with $A - \{p\}$. Eg: In a $\R^n$ the surface $x_1^2 + x_2^2 + ... +x_n^2 = 1$ consists of limit points of the open ball $x_1^2 + x_2^2 + ... +x_n^2 < 1$  

***Definition 1.11*** The closure of a set is the union of a set with all of it's limit points. 

***Definition 1.12*** A Hausdorff space $X$ is said to be **locally compact** if each point in $X$ has a neighbourhood whose clousure is compact.  
Each point in $X$ has a local base consisting of compact neighbourhoods.  
- Open sets of $R^n$ are locally compact. The closure of any set is just the set plus it's boundaries and so this it is closed. 
- $\mathbb{Q}$ is not locally compact.  

***Definition 1.13*** **One Point Complexification:** Let $X$ be a locally compact, non compact Hausdorff space and $\hat{X} = X \cup \{ \infty\}$ be the point union of $X$ with an additional point $\infty$. The topology $\tau$ consists of all open subsets of $X$ as well as subsets of the form $\{\infty\} \cup X- K$ where $K$ ranges over all compact subsets of $X$      



