# 5.1 Irreducibles and unique factorization

This short chapter is about generalizing the factorization theorems discussed so far, namely the fundamental theorem of arithmetic and the polynomial one. We will characterize the integral domains for which we can factor, and they're called unique factorization domains (UFDs).

---

We say that an element $a$ of $R$ is factored in an integral domain $R$ if it's the product of two or more elements of $R$. Some trivial factorizations include $a=1a$ and $a= u(u^{-1}a)$ if $u$ is a unit, and if $a = u b$ where $u$ is a unit. We really don't care about these.


If $R$ is an integral domain we write $a \mid b$ if $b=ac$ for some $c$. The following properties hold and their verification is easy:

- (1) $a \mid a$ for all $a \in R$.
- (2) If $a \mid b$ and $b \mid c$ then $a \mid c$.
- (3) If $a \mid b$ and $a \mid c$ then $a \mid (rb+sc)$ fo all $r,s \in R$.

## Theorem 1
If $R$ is an integral domain, the following are equivalent for $a,b \in R$:
- (1) $a \mid b$ and $b \mid a$.
- (2) $a=ub$ for some unit $u$ in $R$.
- (3) $\langle a \rangle = \langle b \rangle$.

---

- Remmeber in $\mathbb Z$ that these properties hold. Yeah the proofs are kinda like that:

- For (1) implies (2) if $a=0$ then $b=0$ so $a=1b$. Otherwise if $a=ub$ and $b=va$ then we have $a=u(va) = uv(a)$ so $uv=1$ so $u$ and $v$ are units.
- For (2) implies (3) if $a=ub$ then $a \in Rb$ so $Ra \subseteq Rb$. If we write $b=u^{-1} a$ we get similar results. BOOM!
- For (3) implies (1) if $\langle a \rangle = \langle b \rangle$ then $a \in \langle a \rangle = \langle b \rangle = Rb$. Hence $b \mid a$ and similarly $a \mid b$.

---

if $R$ is an integral domain we write $a \sim b$ if and only if $a \mid b$ and $b \mid a$. Condition (3) of Theorem 1 immediately implies that $\sim$ is an equivalence relation!!! We can think of it as a looser sense of equality basically.

- (1) $a \sim a$ for all $a \in R$.
- (2) If $a \sim b$ then $b \sim a$.
- (3) If $a \sim b$ and $b \sim c$ then $a \sim c$.

And we can write the equivalence class like:

$$
[a] = \{ ua \mid u \text{ is a unit in } R \} = R^* a
$$

This relation can be divided and multipled in this sense:

- If $a \sim a'$ and $b \sim b'$ then $a \mid b$ iff $a' \mid b'$.
- If $a \sim a'$ and $b \sim b'$ then $ab \sim a'b'$.

---

In this section we're interested in factorizations that are unique up to associattes of the factors. This means excluding $0$ and units because they have trivial factorizations. So we only consider nonzero nonunits. In particular we're interested in nonzero nonunits that don't factor into any more nontrivial factorizations, like the primes in $\mathbb Z$!!!

## Irreducibles

If $R$ is an integral domain, $p \in R$ is called an irreducible element if it satisfies the following conditions:
- (1) $p \neq 0$ is not a unit.
- (2) If $p=ab$ in $R$, then $a$ or $b$ is a unit in $R$.

An element that is not irreducible is called reducible.

Fields cant have irreducibles because they have no nonzero nonunits.

### ***NOTE: Then is there a similar theorem for fields???***

## Theorem 2
If $R$ is an integral domain, the following conditions are equivalent for a nonzero nonunit $p$ in $R$:
- (1) $p$ is irreducible.
- (2) If $d \mid p$ then $d \sim 1$ or $d \sim p$.
- (3) If $p \sim ab$ in $R$ then $p \sim a$ or $p \sim b$.
- (4) If $p = ab$ in $R$, then $p \sim a$ or $p \sim b$.

---

- For (1) implies (2) if we have $p=ad$ then either $a$ or $d$ is a unit and if its $a$ then we have $d = a^{-1} p$ so $p \sim d$ and if its $d$ then we have $d \sim 1$.
  -  Intuition for (2): Basically definition of a prime, either you're a lil unit or just a version $p$ itself.

- For (2) implies (3) if $p \sim ab$ then $b \sim p$ so either $b \sim 1$ or $b \sim p$. In the first case we have $p = ab$ and $a = b^{-1} p$ so $a \sim p$!
  - Intuition for (3): If $p$ is a product of some two elements, then one of the two elements has to be a version of $p$ and the other is just a lil unit.

- For (3) implies (4) this is obvious cause $p=ab$ implies $p \sim ab$.
  -  Intuition for (4): Same as (3) lol

- For (4) implies (1) if $p=ab$ then $p \sim a$ or $p \sim b$ by (4). If $p \sim a$ then $a=up$ where $u$ is a unit so $p = upb$ and thus $ub=1$ and thus $b$ is a unit. Similarly $p \sim b$ implies $a$ is a unit!


- An immediate consequence is that if $p$ is irreducible then $p \sim q$ implies $p$ is irreducible if and only if $q$ is irreducible.

---

- Ok, so now we need to find integral domains where we *can* factor elements into irreducibles. 

- To do this we simply find the integral domains where a nonzero nonunit *cannot* be written as a product of irreducibles.

- Call such an element $a \in R$ "bad." Then $a = x_1 a_1$ and $a \not\sim x_1$ and $a \not\sim a_1$, by Theorem 2. Now, we know that either $x_1$ or $a_1$ is "bad," and suppose that it's $a_1$. Then, as before, we have $a_1 = x_2 a_2$ and $a_1 \not\sim x_2$ and $a_1 \not\sim a_2$.

- We clearly have $a \in R a_1$ and in general $a_n \in R a_{n+1}$ so
$$
\langle a_1 \rangle \subseteq \langle a_2 \rangle \subseteq \langle a_3 \rangle \subseteq \cdots
$$

- And since $a \not\sim a_1 \not\sim a_2 \not\sim \cdots$ we have 
$$
\langle a_1 \rangle \subset \langle a_2 \rangle \subset \langle a_3 \rangle \subset \cdots
$$

- An integral domain (which I'll be calling ID from now on) $R$ is said to satisfy the ***ascending chain condition on principal ideals (ACCP)*** if $R$ contains no strictly increasing infinite ascending chain $\langle a_1 \rangle \subset \langle a_2 \rangle \subset \langle a_3 \rangle \subset \cdots$.

- This leads to the next theorem!!!

## Theorem 3
Let $R$ be an integral domain that satisfies the ACCP. Then every nonzero nonunit in $R$ is a product of irreducibles.

---

- The intuiton for this guy is that if there existed an element that didn't satisfy the property, then there would be an infinite strictly increasing chain of ascending ideals!!! (I think idk there's too many words in that phrase lol)


- Theorem 3 is cool because the ACCP condition is pretty easy to work with so:

## Lemma 1
The following conditions are equivalent for an integral domain $R$.
- (1) $R$ satisfies the ACCP.
- (2) For any ascending chain $\langle a_1 \rangle \subseteq \langle a_2 \rangle \subseteq \cdots$ of principal ideals in $R$, an integer $n \geq 1$ exists such that $\langle a_n \rangle = \langle a_{n+1} \rangle = \cdots$.

---

- The proof for (1) implies (2) is literal contradiction. It assumes that if there exists no $n \geq 1$ such that $\langle a_n \rangle = \langle a_{n+k} \rangle$ for all $k > 0$ then we also have $\langle a_1 \rangle \subset \langle a_2 \rangle \subset \cdots$, contradicting (1).

- The proof for (2) implies (1) is an exercise so i cant give intuition lol


- The intuition for the proof is that (2) says that if theres a "ceiling" for any chain, then there is no infinite chain, so the ACCP works and vice versa.

## Theorem 4
If $R$ is an integral domain that satisfies the ACCP, then the ring $R[x]$ of polynomials over $R$ also satisfies the ACCP.

---

- The proof is pretty neat. It starts by letting $\langle f_1 \rangle \subset \langle f_2 \rangle \subset \cdots$ be a strictly increasing chain in $R[x]$. 

- If $a_i$ is the leading coefficient of $f_i$ is $a_i$ then $\langle a_1 \rangle \subseteq \langle a_2 \rangle \subseteq \cdots$.

- By hypothesis there exists an $n$ such that $\langle a_n \rangle = \langle a_{n+1} \rangle = \cdots$.

- If $m \geq n$ let $f_m = g f_{m+1}$ for some $g$, and let $b$ be its leading coefficient, so $a_m = b a_{m+1}$. Since $a_m \sim a_{m+1}$ it follows that $b$ is a unit.

- But $g$ isn't a unit so $\deg g \geq 1$ because $\langle f_m \rangle \neq \langle f_{m+1} \rangle$.

- Hence $\deg f_n > \deg f_{n+1} > \deg f_{n+2} > \cdots$ but this is impossible because $\deg f_m$ is a nonnegative integer for each $m$!!

## Unique factorization domain

Factorizations into irreducibles are useful when the factorizations are unique up to the associates of the irreducibles!!! An integral domain $R$ is called a unique factorization domain (UFD) if it satisfies the following conditions

- (1) Every nonzero nonunit in $R$ is a product of irreducibles.
- (2) If $p_1 p_2 \cdots p_r \sim q_1 q_2 \cdots q_s$, where the $p_i$ and $q_j$ are irreducibles, then $r = s$ and (after possible relabeling) $p_i \sim q_i$ for each $i$.

---

- From the definition above any field $F$ is a UFD but vacuously!!

- If $R = \mathbb Z$ then we see that the proof of Theorem 1.2.7 relies heavily on the fact that if $p$ is a prime and $p \mid ab$, then $p \mid a$ or $p \mid b$. Not every irreducible has this property!!!! 

## Primes

So we define an element $p$ of a ring $R$ to be a prime element if:
  1. $p \neq 0$ and $p$ is not a unit.
  2. If $p \mid ab$ then $p \mid a$ or $p \mid b$.

Primes are also compatible with the $\sim$ relation because if $p \sim q$ then $p$ is prime if and only if $q$ is prime.

## Theorem 5

Every prime in an integral domain is irreducible in $R$, but the converse fails for some integral domains $R$.

## ***Note: <u>Which</u> fields?***

---

- Let $p=ab$ be a prime in an integral domain $R$.
- Then either $p \mid a$ or $p \mid b$.
- WLOG, let $p \mid a$.
- Also $a \mid p$.
- So $p \sim a$.
- (3) of tHeorem 2.

## Lemma 2

Let $p$ be a prime in an integral domain $R$. If $p \mid a_1 a_2 \cdots a_n$ in $R$, then $p \mid a_i$ for some $i = 1,2,\dots,n$.

---

- This is a generalization of Euclid's Lemma.

## Lemma 3

If $R$ is a UFD, then every irreducible in $R$ is prime.

---

- Let $p \mid ab$ be a prime, and let $ab = pd$. Factor $a,b,d$ into primes so $a = \Pi^m p_i, b = \Pi^l q_i,$ and $c = a = \Pi^k r_i$. Then we have
$$
p r_1 \cdots r_k = p_1 \cdots p_m q_1 \cdots q_l.
$$

Because of the uniqueness cause $R$ is a UFD, it follows that $p \mid p_i$ or $p \mid q_i$ for some $i$ so $p \mid a$ or $p \mid d$. BOOM!!

- Intuition: UFD says that every factor divides another factor when $a \sim b$ so $p$ must divide some factor!!!

- In a UFD, this lemma says that an element is prime if and only if it is irreducible.


## Properties of $\mathbb Z$ being generalized

- First up, we got the factorization of any $a$ into primes: $a = p_1^{a_1} p_2^{a_2} \cdots p_r^{a_r}$. Here, $a_i$ and $r$ are uniquely determined by $a$.

### ***NOTE: By identifying every element by some tuple $(a_1, a_2, \cdots, a_r)$ or actually sequence for my infinite rings out there, can we make every ring isomorphic to like a sequence???***

- Now we claim that the divisors $d$ of $a$ are also uniquely determined up to associates:

  <center> $d \mid a$ if and only if $d \sim p_1^{d_1} p_2^{a_2} \cdots p_r^{d_r}$ where $0 \leq d_i \leq a_i$ for each $i$. </center>


- An element $d$ of $R$ is called a greatest common divisor of $s_1, \dots, s_n$, denoted $\gcd(s_1, \dots, s_n)$, if it satisfies the following conditions:

  1. $d \mid s_i$ for each $i = 1,2, \dots, n$.
  2. If $r \in R$ and $r \mid s_i$ for each $i = 1, \dots, n$, then $r \mid d$.

- And the least common multiple of $s_1, \dots, s_n$ is denoted by $\operatorname{lcm}(s_1, \dots, s_n)$ if it satisfies
  1. $s_i \mid m$ for each $i = 1, \dots, n$.
  2. If $r \in R$ and $s_i \mid r$ for each $i = 1, \dots, n$, then $m \mid r$.


- These definitions agree with $\mathbb Z$ and $F[x]$, but in those UFDs we had the extra conditions that the factors were positive and monic, respectively. We can't have this in every UFD, but the GCD and LCM are both uniquely determined up to associates!!!

  -  Thus, if $s_i \sim s_i'$ the then $\gcd(s_1, \dots, s_i) \sim \gcd(s_1', \dots, s_n')$.
- And a similar condition goes for least common multiples

- We typically just ignore the distinction between associates so we just write $\gcd(s_1, \dots, s_n)$ and $\operatorname{lcm}(s_1, \dots, s_n)$.

- The next theorem guarantees the existence of GCDs and LCMs in UFDs.

## Theorem 6

Let $R$ be a UFD, and let $a, b, c, \dots$ be a finite list of nonzero elements in $R$. If $p_1, p_2, \dots, p_r$ are the nonassociated primes dividing one of $a,b,c, \dots,$ write
$$
a \sim p_1^{a_1} p_2^{a_2} \cdots p_r^{a_r} \quad a_i \geq 0 \text{ in } \mathbb Z \\
b \sim p_1^{b_1} p_2^{b_2} \cdots p_r^{b_r} \quad a_i \geq 0 \text{ in } \mathbb Z \\
c \sim p_1^{c_1} p_2^{c_2} \cdots p_r^{c_r} \quad c_i \geq 0 \text{ in } \mathbb Z \\
$$

where an exponent is zero if the corresponding prime does not appear. If we define $d_i = \min(a_i, b_i, c_i, \dots)$ and $m_i = \operatorname{lcm}(a_i, b_i, c_i, \dots)$ for each $i = 1, 2, \dots, r,$ then
$$
\gcd(a,b,c, \dots) \sim p_1^{d_1} p_2^{d_2} \cdots p_r^{d_r}
$$
and
$$
\operatorname{lcm}(a, b, c, \dots) \sim p_1^{m_1} p_2^{m_2} \cdots p_r^{m_r}.
$$

---

- The proof is literally just the proof of Theorem 1.2.9, besides, it's pretty easy to see why.

- Note that it's not possible to express $d$ in the fomr $d = xa+yb$ for some $x$ and $y$ in $R$. This is true for $R = \mathbb Z$ and $R = F[x]$, but not in general. However PIDs do have this property! Nonetheless, many faimilar properties still hold for GCDs.


## Lemma 4

Let $R$ be an integral domain and let $a,b,c$ be nonzero elements of $R$. If $\gcd(a,b)$ and $\operatorname{gcd}(ca, cb)$ both exist in $R$, then $\gcd(ca,cb) \sim c \gcd(a,b)$.

---

- The proof goes like this:
-  Let $d = \gcd(a,b)$ and $d' = gcd(ca,cb)$.
- Then $d \mid a$ and $d \mid b$, so $cd \mid ca$ and $cd \mid cb$. Thus $cd \mid d'$
- Write $d' = u cd$, and now we show that $u$ is a unit!!
- Write $ca = d' x$ for some $x$. Then $ca = ucd x$, so $a = udx$ cause $R$ is a domain so $ud \mid a$.
- Similarly $ud \mid b$, so $ud$ divides $d$. If $d = uvd$ then $uv=1$ so $u$ is a unit.

## Theorem 7

The following are equivalent for an integral domain $R$:

- (1) $R$ is a UFD.
- (2) $R$ satisfies the ACCP, and $\gcd(a,b)$ exists for all nonzero $a,b \in R$.
- (3)  $R$ satisfies the ACCP, and every irreducible element in $R$ is prime

---

- For (1) implies (2) the proof goes like this:
  - Suppose that $\langle a_i \rangle \subset \langle a_2 \rangle \subset \cdots$ in $R$.
  - We have $a_1$ not being a unit because $a_1 \neq R$.
  - Let $a = p_1^{a_1} p_2^{a_2} \cdots p_r^{a_r}$ where $p_i \neq p_j$ if $i \neq j$. In other words, they are non associates. Also, we have $a_i \geq 1$ for all $i$.
  - We have $a_i \mid a_1$, so $a_i = p_1^{d_1} p_2^{d_2} \cdots p_r^{d_r}$ for $0 \leq d_j \leq k_j$.
  - But there's only a finite number of such divisors, so for some $m \neq n$ we must have $\langle a_m \rangle = \langle a_n \rangle$!!! CONTRADICTION!!!

- For (2) implies (3) we have:
  - Let $p \mid ab$ and $p$ is irreducible.
  - By (2) we have $d = \gcd(a,p)$ existing so $d \mid p$ and because $p$ is irreducible, either $d \sim p$ or $d \sim 1$.
    - If $d \mid p$ then $p \mid a$ because $d \mid a$.
    - If $d \mid 1$ then $\gcd(ab, pb) \sim b$. Because $p \mid ab$ and $p \mid pb$ we have $p \mid \gcd(ab, pb)$ so thus $p \mid b$.

- For (3) implies (1) by Theorem 3 we already have every nonzero nonunit being a product of irreducibles. So we acn just show that factorizations are unique!!
  - Let $p_1 \cdots p_r \sim q_1 \cdots q_s$.
  - Every $p_i$ and $q_i$ is irreducible and $r+s$ is minimal (e.g. if it were smaller than it would imply common factors, which are found in this contradiction proof!)
  - If $r = 1$ we have $p_1 = q_1 \cdots q_s$, a contradiction unless $s = 1$ which would mean that they are the same.
  - So assume $r,s \geq 2$. Then $p_1 \mid q_1 \cdots q_m$.
  - By lemma 2, and relabeling, write $p_1 \mid q_1$. Since $q_1$ is irreducible we have $p_1 \sim q_1$.
  - THEN $p_2 \cdots p_r \sim q_2 \cdots q_s$, a CONTRADICTION OF MINIMALITYYY!!!

## Unique Factorization in $R[x]$

This section finishes with proving that if $R$ is a UFD, then so is $R[x]$.
- By Theorem 7, $R$ satisfies the ACCP. By Theorem 4, so does $R[x]$. Thus by Theorem 7, it suffices to show that the irreducible polynomials in $R[x]$ are primes. 


### Content and primitives

If $R$ is a UFD and $f$ is a nonzero polynomial, the greatest common divisor of the coefficients of $f$ is called the content of $f$, denoted $c(f)$. $f$ is called a primitive polynomial if $c(f) \sim 1$.

## Lemma 5
Let $R$ be a UFD and let $f \neq 0$ be a polynomial in $R[x]$.

- (1) $f$ can be written as $f = c(f) f_1$, where $f_1 \in R[x]$ is primitive.
- (2) If $0 \neq a \in R$, then $c(af) \sim a c(f)$.

---

- The first part is pretty intuitive cause we just factor out the content.

- The second idk

## Lemma 6
If $R$ is a UFD and $p \in R[x]$ is irreducible with $\deg p \geq 1$, then $p$ is primitive.

---

- Intuitive to understand as a lemma.

- Write $p = c(p) p_1$. Then because $p$ is irreducible we know that either $c$ or $p_1$ is a unit, but $\deg p_1 \geq 1$ so $c \sim 1$. Thus $p$ is primitive.

## Theorem 8 (Gauss' Lemma)

Let $R$ be a UFD. If $f \neq 0$ and $g \neq 0$ in $R[x]$, then
$$
c(fg) \sim c(f) c(g).
$$

In particular, the product of primitive polynomials is primitive.

---

- The first part of the proof is pretty easy to undersand. Because if $f = c(f) f_1$ and $g = c(g) g_1$, where $f_1$ and $g_1$ are primitive then
$$
c(fg) \sim c[ c(f) c(g) f_1 g_1 ] \sim c(f) c(g) c( f_1 g_1 ).
$$

Now we have to show that the result holds when $f$ and $g$ are primitive!!

- Assume $c(f) \sim c(g) \sim 1$, and suppose that $fg$ isn't primitive.
- Then there exists a prime $p$ that divides each coefficient of $fg$.
- Write $f = a_0 + a_1 x + \cdots$ and $g = b_0 + b_1 x + \cdots$.
- $f$ and $g$ are primitive, so $p$ doesn't divide *every* $a_i$ and $b_i$.
- Thus there exist $m, n \geq 0$ such that
  - $p$ doesn't divide $a_n$ but $p \mid a_i$ for $0 \leq i < n$.
  - $p$ doesn't divide $b_m$ but $p \mid b_j$ for $0 \leq j < m$.
- Coefficient of $x^{m+n}$ is $\Sigma_{i+j=m+n} a_i b_j$. So $p \mid c$ because $c$ is a coefficient of $fg$, and $p$ divides every term $a_i b_j$ EXCEPT possible $a_n b_m$.
- If it does, then $p \mid a_n b_m$ so either $p \mid a_n$ or $p \mid b_m$. CONTRADICTION!!! Therefore it can't divide $a_n b_m$ so $fg$ is primitive.

## Theorem 9
Let $R$ be a UFD with field of quotients $F$. Regard $R \subseteq F$ as a subring of $F$ as usual. If $p \in R[x]$ is irreducible in $R[x]$, then $p$ is irreducible in $F[x]$.

---

- Proof goes like this: Let $p$ be an irreducible in $R[x]$ with $\deg p \geq 1$, and let $p = gh$. Let $a$ and $b$ be the products of all the denominators of the coefficients of $g$ and $h$.

- Write $g_1 = a g$ and $h_1 = b h$. Thus $abp = g_1 h_1$. Because $p$ is primitive Gauss' Lemma gives
$$
ab \sim ab c(p) \sim c(abp) = c(g_1 h_1) \sim c(g_1) c(h_1).
$$

- Write $g_1 = c(g_1) g_2$ and $h_2 = c(h_1) g_2$ where $g_2$ and $h_2$ are primitive.
- so $abp = g_1 h_1 = c(g_1) c(h_1) h_2 g_2$, so the equation above implies $p \sim h_2 g_2$.
- Thus either $h_2$ or $g_2$ is a unit.
- If $g_2 = u$ then $bg = g_1 = c(g_1) g_2 = c(g_1) u$ so $g = b^{-1} c(g_1) u$ is a unit!!! Similarly if $h_2 \in R^*$ then $h$ is a unit in $F[x]$. This shows that $p$ is irreducible.
