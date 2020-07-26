# Lec 15

## Properties of Relations

### 1. Reflexive Relation

1. A relation R on a set A is called reflexive if (a,a) $ \in$ R for every element $ a \in A $
2. `A relation R is reflexive` <u>if and only if</u> MR(Matrix of R) has 1 in every position on its ==main diagonal==.

### 2. Irreflexive Relation

1. A relation R on a set A is called irreflexive if (a,a)  $ \notin $ R for ==every== element a $\in$ A.
2. Irreflexive  $\neq$  not reflexive
3. A relation R is irreflexive if and only if MR has ==0== in **every position on its main diagonal**.

### 3. Symmetric Relation

1. A relation R on a set A is called symmetric if (b, a) $\in$ R whenever (a, b) $\in$ R for all a, b $\in$ A.

2. A relation R is symmetric ==<u>if and only if</u>== MR is **symmetric**.

   **$MR^T = MR$**

### 4. Antisymmetric Relation

1. A relation R on a set A is called antisymmetric if (b, a) $\in$ R and (a, b) $\in$ R implies a = b for all a, b $\in$ A. 
2. Antisymmetric $\neq$ not Symmetric
3. if have (b, a) $\in$ R and (a, b) $\in$ R. a ==must equal== to b;

### 5. Transitive Relation

1. A relation R on a set A is called transitive if (a, b) $\in$ R and (b, c) $\in$ R implies (a, c) $\in$ R for
   all a, b, c $\in$ A.

## Combining Relations

1. **Definition: **  Let A and B be two sets. A binary relation from A to B is a subset of a Cartesian product A $\times$ B.

2. **Definition:** Let R be a relation from a set A to a set B and S be a relation from B to C. The composite of R and S is the relation consisting of the ordered pairs (a; c) where a $\in$ A and c $\in$ C and for which there is a b $\in$ B such that (a; b) $\in$ R and (b, c) $\in$ S. We denote the composite of **R and S** by S $\circ$ R.

3. Combining Relation same as Matrix multiplication.

4. **Power Relation** :

   Let R be a relation on A. The powers $R^n$ , for n = 1, 2, 3, ... , is defined inductively by
   $$
   R^1 = R  \quad and \quad R^{n+1} = R^n \circ R
   $$
   **Theorem **:  The relation R on a set A is transitive if and only if Rn $\circ$ R for n = 1, 2, 3, ...

   ​	**Proof: **  

   ​			if: $ R^n \subseteq R$ for n = 1,2,3... $\to$ R is transitive

   ​				Let n = 2 , $R^2 \subseteq R \, \, (a,b),(b,c) \in R \quad R^2 = R \circ R \\ (a,c) \in R^2 \subseteq R \Rightarrow R\quad is \quad transitive $

   ​			only if :  

   ​					R is transitive $\to \quad R^n \subseteq R \quad for \quad n=1,2,3\dots$

   ​					Mathematical  Induction 1: base case: n = 1, $R^1 \subseteq R$

   ​																 2: i.h. n = k, $ R^k \subseteq R$

   ​																 3: i.s.  n = k+1 $R^{k+1} = R^k\circ R$

   ​					$(a,b) \in R^{k+1} \quad (x,b)\in R^k \subseteq R \quad (a,b)\in R\\R^{k+1}\subseteq R$

   ​																 4:  by .....

##  Number of Reflexive Relations

1.  The number of reflexive relations on a set A with|A| = n is $2^{n(n-1)}$.	

## n-ary Relations

### Relational Databases ==$??\bigstar \bigstar$==

1. primary key
2. composite key
3. E-R Diagram
4. Selection Operator
5. Projection Operators
6. Join Operator

## Some special ways to represent binary relations:

![image-20200524184427584](C:\Users\30556\AppData\Roaming\Typora\typora-user-images\image-20200524184427584.png)



