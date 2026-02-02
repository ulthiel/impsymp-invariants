# Fundamental invariants of improper symplectic reflection groups

In the classification of symplectic reflection groups by Cohen, the class of "improper" groups is formed by taking an ordinary complex reflection group $W \subset \mathrm{GL}(\mathfrak{h})$ and considering the induced action on $\mathfrak{h} \oplus \mathfrak{h}^*$. The matrix for this action corresponding to $w \in W$ is the block diagonal matrix with blocks $w$ and $(w^t)^{-1}$, where $w^t$ denotes the transpose.

I'm interested in the invariant theory of such groups. By $\mathbb{C} \lbrack \mathfrak{h} \oplus \mathfrak{h}^* \rbrack$ we denote the coordinate ring of the variety $\mathfrak{h} \oplus \mathfrak{h}^*$, i.e. the symmetric algebra $\mathrm{Sym}(\mathfrak{h}^* \oplus \mathfrak{h})$ of the "dual" of $\mathfrak{h} \oplus \mathfrak{h}^*$. If you choose a basis $\{ y_1,\ldots,y_n \}$ of $\mathfrak{h}$ with dual basis $\{ x_1,\ldots,x_n \}$, then $\mathbb{C} \lbrack \mathfrak{h} \oplus \mathfrak{h}^* \rbrack = \mathbb{C} \lbrack x_1,\ldots,x_n,y_1,\ldots,y_n \rbrack$ is the polynomial ring in the $x_i$ and $y_i$. This ring has several gradings:

- the usual $\mathbb{N}$-grading of polynomials;
- an $\mathbb{N} \times \mathbb{N}$-grading with $\deg x_i = (1,0)$ and $\deg y_i = (0,1)$;
- an induced $\mathbb{Z}$-grading which corresponds to putting the $x_i$ in degree +1 and the $y_i$ in degree -1.

The action of $w \in W$ on the $y_i$ is the usual one, and on the $x_i$ it's via $(w^t)^{-1}$. This action is homogeneous with respect to all the gradings above. The invariant ring $\mathbb{C} \lbrack \mathfrak{h} \oplus \mathfrak{h}^* \rbrack^W$ is the coordinate ring of the symplectic singularity $(\mathfrak{h} \oplus \mathfrak{h}^*)/W$. I want to know a system of "fundamental invariants", i.e. a minimal generating system as a $\mathbb{C}$-algebra. We can always find a system of $\mathbb{N} \times \mathbb{N}$-homogeneous invariants, and this what we want.

In contrast to invariants of complex reflections groups (without the doubling), there seems to be not much known about the invariant theory of such groups. For example, from theory I do not even know how many fundamental invariants there are in a system and what their degrees are (this is both independent of the chosen system). Moreover, I do not know how to efficiently compute fundamental invariants. In [CHAMP](https://github.com/ulthiel/Champ) I have implemented the function `SymplecticDoublingFundamentalInvariants` where I'm just using Magma's generic algorithm. I suspect one can cook up algorithms tailored to this specific setting. Also, for applications in rational Cherednik algebras, it would be desirable to compute only the fundamental invariants of $\mathbb{Z}$-degree zero—but I don't know how to do this without computing "all" the invariants first.

**Questions.**

1. In the examples below it seems that if there is an invariant of bidegree $(d,e)$, then there's also one of bidegree $(e,d)$. Can you prove this?
2. How many fundamental invariants are there in total? What are their degrees? How many are there of $ℤ$-degree 0?
3. Is there an efficient algorithm for computing the fundamental invariants (all or of specific degree)?
4. Can you do H4=G30?

**Remark.** In CHAMP, I've flipped the order (but not the meaning) of the $x_i$ and $y_i$ to account for the fact that in Magma all actions are right actions and to make my computations compatible with how I implemented the Cherednik algebra.

## Summary of results for exceptional groups

Below, I'm summarizing what I could compute for exceptional complex reflection groups. When successful, the fundamental invariants are stored in the CHAMP database (in the same order as they were computed). The computation for G29 took 42 hours.
