# Lec 16

## ==Closures of Relations==

1. The set S is called the reflexive closure of R if it:

   - contains R
   - is reflexive
   - is minimal (is contained in every reflexive relation Q that contains R (R $\subseteq$ Q), i.e. , S $\subseteq$ Q)

2. **Definition:**  Let R be a relation on a set A. A relation S on A with property P is called the closure of R with respect to P if S is subset of every relation Q (S $\subseteq$ Q) with property P that contains R (R $\subseteq$ Q). 

3. *Find Transitive Closure* 

   - Finding a transitive closure corresponds to finding all pairs
     of elements that are connected with a directed path

   - **Method**: Path in Directed Graphs

     - Let R be relation on a set A. There is a path of length n from a to b ==***if and only***== if (a, b) $\,\in \, R^n$ .

       - proof : (by induction)

         i.h. there is a path of length n from a to b if and only if (x,b)$\;\; \in\; R^n$

         i.s. there is a path of length n+1

         iff (a,x) $\in $ R; iff (a,b) $\in\,R^n$

         

     -  

4. 

## ==Connectivity Relation==

1. **Lemma:** Let A be a set with n elements, and R a relation on A. If there is a path from a to b with a $\neq$ b, then there exists a path of length $\le$ n $-$ 1.
   $$
   R^* = \bigcup\limits_{k=1}^n R^k\Longrightarrow R^* = \bigcup\limits_{k=1}^n R^k
   $$
   For upper is n is a = b;

   We also can use 0 1 Matrix
   $$
   M_{R^*} = M_R \vee M_R^{[2]} \vee M_R^{[3]} \vee\cdots M_R^{[n]}
   $$
   **Procedure :** 

   - transClosure ($M_R$: zero-one n $\times$ n matrix)
     // computes $R^*$ with zero-one matrices
     A := B := $M_R$;
     for i := 2 to n
     A := A$\;\odot\; M_R$
     B := B $\vee$ A
     return B
     // B is the zero-one matrix for $R^*$ 

   - O($n^4$)

   - improve algorithm

     - **procedure **

       Warshall (MR: zero-one n $\times$ n matrix)
       // computes $R^*$ with zero-one matrices
       W := $M_R$;
       for k := 1 to n

       ​	for i := 1 to n

       ​		for j := 1 to n

       ​			$w_{ij} := w_{ij} \vee (w_{ik} \wedge w_{kj} )$
       return W

     - Time Complex: $O(n^3)$ 

     - $w_{ij}$ = 1 means there is a path from i to j going only through nodes $\le$ k.
       $$
       W_{ij}^{[k]} = W_{ij}^{[k-1]}\vee(W_{ik}^{[k-1]}\wedge W_{kj}^{[k-1]})
       $$
       

2. **Lemma:** The transitive closure of a relation R equals the connectivity relation $R^*$.

3. **Theorem:** The transitive closure of a relation R equals the connectivity relation $R^*$.

   **Proof:**

   - $R^*$ is transitive

   - $R^* \,\subseteq\, S$  whenever S is a transitive relation containing R

     - If (a, b) $\in\,R^*$  and (b, c) $\in\,R^*$, then there are paths from a to b and from b to c in R. Thus, there is a path from a to c in R. This means that (a, c) $\in\,R^*$.

     - Suppose that S is a transitive relation containing R

       Then $S^n$ is also transitive and $S^n \,\subseteq \,S$ . 

       We have $S^*\,\subseteq\,S$ . Thus, $R^*\,\subseteq\,S^*\,\subseteq\,S$ 

       - $S^* = \bigcup\limits_{k=1}^nS^k\\R\,\subseteq\,S\to R^*\,\subseteq\,S^*$ 

## ==Equivalence Relation==

1. **Definition:** A relation R on a set A is called an ***<u>equivalence relation</u>*** if it is *$\color{#FF0000}{reflexive}$* , *$\color{#FF0000}{symmetric}$*, and  *$\color{#FF0000}{transitive}$*.

2. ### Equivalence Class

   1. **Definition:** Let R be an equivalence relation on a set A. The set of all elements that are related to an element a of A is called the equivalence class of a, denoted by $[a]_R$. When only one relation is considered, we use the notation [a].
      $$
      [a]_R = {b :(a,b)\in R}
      $$
      $\color{#0000FF}Example:$ 

      - A = {0, 1, 2, 3, 4, 5, 6}
        R = {(a, b) : a $\equiv$ b mod 3}
        [0] = [3] = [6] = {0, 3, 6}
        [1] = [4] = {1, 4}
        [2] = [5] = {2, 5}

      - "Strings a and b have the same length."

        [a] = the set of all strings of the same length as a

      - "Integers a and b have the same absolute value."

        [a] = the set {a, $-$a}

      - "Real numbers a and b have the same fractional part (i.e.,
        a $-$ b $\in$ **Z**)."

        [a] = the set $\{\dots,a-2,a-1,a,a+1,a+2,\dots\}$ 

   2. **Theorem :**  Let R be an equivalence relation on a set A. The following statements are equivalent:

      (i) a R b
      (ii) [a] = [b]
      (iii) [a] $\cap$ [b] $\neq \empty$ ;

      (i) $\to$ (ii) $\to$ (iii) $\to$ (i)

      $\color{#FF0000}(i)\to(ii)$

      a R b  (a,b) $\in$ R	$[a]\subseteq [b]\quad[b]\subseteq [a]$

      $x \in [a]$  $(a,x)\in R \quad (b,a)\in R \Rightarrow ((b,x)\in R\quad x \in [b])$

      $\color{#FF0000}(ii)\to(iii)$

      $[a]=[b]\quad[a]\cap[b]\quad[a]\neq\empty\\(a,a)\in R\quad a\in[a]\quad[a]\cap[b]\neq\empty$

      $\color{#FF0000}(iii)\to(i)$

      $Suppose\quad [a]\cap[b]\neq\empty\quad c\in[a]\cap[b]\\(a,c)\in R\quad and \quad(b,c)\in R\\from\;\;(b,c)\in R\;\;by\;\;symmetric\;\;we\;\;have\;\;(c,b)\in R\\by\;\;transitive\;\;we\;\;have\;\;(a,b)\in R$

      

## ==Partition of a Set S==

1. **Definition:** Let S be a set. A collection of nonempty subsets of S $A_1,A_2,A_3,\dots,A_k$ is called a partition of S if:
   $$
   A_i\cap A_j=\empty,\quad i\neq j\;\;and\;\;S=\bigcup\limits_{i=1}^kA_i
   $$
   ![Theorem Let R be an equivalence relation on a set A.
   Then union of all the equivalence classes of R is A:](C:\Users\30556\AppData\Roaming\Typora\typora-user-images\image-20200525130622079.png)

2. $\color{#0000FF}Example:$

   $A=\{0,1,2,3,4,5,6\}\\A_1=\{0,3,6\},A_2=\{1,4\},A_3=\{2,5\}$

## ==Equivalence Classes and Partitions==

1. **Theorem :**  Let R be an equivalence relation on a set A. Then union of all the equivalence classes of R is A:
   $$
   A=\bigcup\limits_{a\in A}[a]_R
   $$

2. **Theorem:** The equivalence classes form a partition of A.

3. **Theorem:** Let ${A_1,A_2,A_3,\dots,A_i,\dots}$ be a partition of S. Then there is an equivalence relation R on S, that has the sets $A_i$ as its equivalence classes.

   $\color{#FF0000}{Equivalence\;\;relation\longrightarrow Equivalence\;\;classes\longrightarrow partition\;\;of\;\;A\longrightarrow\\ Equivalence\;\;relation}$



