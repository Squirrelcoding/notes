# 4.3 Factor rings of polynomials over a field

In the previous section we saw how similar $\mathbb Z$ and $F[x]$ are when it comes to factoring. Here, we see that there are even more similarities! In particular, factor groups. In the integers every ideal is in the form $\langle n \rangle$ and in $F[x]$ every ideal $A$ is in the form $A = \langle h \rangle$, so they are all multiples of a polynomial $h \in F[x]$!! Like the integers the integer $n$ in the ideal is uniquely determined if $n \geq 0$ so if we are given that $h$ is monic, we can uniquely determine it!

## Theorem 1

If $F$ is a field every ideal $A$ of $F[x]$ is principal. In fact, if $A \neq 0$, a uniquely determined monic polynomial $h$ exists in $F[x]$ such that $A = \langle h \rangle$.

---

- The case is obvious for $A=0,$ ya just have $\langle 0 \rangle$. So if $A \neq 0$ it must contain nonzero polynomials, and since it's an ideal we also have monic polynomials. Because for $f \in A$ if $a$ is its leading coefficient we also have $a^{-1} f \in A$.

  - Then the proof chooses a polynomial $h$ of minimal degree. Clearly $\langle h \rangle \subseteq A$. So now its goal is to show that its equality!

  - By division algorithm we have $f = qh+r$. If $r=0$ this leads to $a^{-1} r \in A$ where $a$ is its leading coefficient, and since $\deg r < \deg h$ we have $r$ contradicting the minimality of $h$. So $r=0$ and so $f=qh$! 

  - The uniqueness part is pretty straightforward, if we have $\langle k \rangle = \langle h \rangle$ then $k$ and $h$ divide each other so they are equal because they're monic!!!

- The intuition for this theorem is pretty similar for $\mathbb Z$. If we have a collection of integers that when added we still have it in that same subgroup, then clearly the only logical choice for determining this subgroup is that they must all be multiples of some integer. Same thing here.

  - Furthermore, the proof requires $h$ to be minimal because it's small enough to fit inside all of the factorizations of the polynomials!

- Here, $F[x]$ and $\mathbb Z$ are both called ***principal ideal domains*** because every ideal is principal!

- This theorem suggests that $h \leftrightarrow  \langle h \rangle$ is a bijection for monic polynomials $h$!!

## Example 1

This example shows that the factor ring $R = \mathbb R[x] / A$ where $A = \langle x^2 + 1 \rangle$ is isomorphic to $\mathbb C$! 

- To start, it defines some operations like in ***Notation*** below.

- If $f \in \mathbb R[x]$ then the division algorithm gives $f = q(x^2 + 1) + (a+bx)$.

- Because $f - q(x^2 + 1) \in A$, we have $\overline f = \overline{a+bx}$.

- So $R$ can now be described as $R = \{ \overline a + \overline{b} \overline x \mid a,b \in \mathbb R  \}$.

- Addition is easy to define using this new description. But multiplication yields
$$
(\overline a + \overline b \overline x)(\overline c + \overline d \overline x) = \overline{ac} + (\overline{ad} + \overline{bc}) \overline x + \overline{bd} \overline{x}^2.
$$

- Now it looks like $R$ isn't closed because of $\overline{x}^2$! But we have $x^2 + 1 \in A$ so $\overline {x^2 + 1} =  \overline 0$, so $\overline{x}^2 = - \overline 1$. So we can rewrite it as

$$
(\overline a + \overline b \overline x)(\overline c + \overline d \overline x) = (\overline{ac} - \overline{bd}) + (\overline{ad} + \overline{bc}) \overline x.
$$

- If we denote $\overline x$ as $i$ and writing $a$ for $\overline a$ using the one-to-one ring homomorphism $a \mapsto \overline a$. Then we may identify $\mathbb R$ using this relationa nd identify $\mathbb R$ as a subring of $R$!! So finally $R$ takes the form $R = \{ a+bi \mid a,b \in \mathbb R, i^2 = -1 \}$. The COMPLEXES!!!

The general argument is generalized into a series of lemmas that follows now. They are basically showing how a factor ring is equivalent to another ring.

## Notation
- We write $A = \langle h \rangle = \{ qh \mid q \in F[x] \}$ to if $h$ is a monic nonconstant polynomial.

- $R = F[x]/A$

- $\overline a = a + A$ and $t = \overline x = x+A$.

- Operations in $R$ are $\overline f + \overline g = \overline{f+g}$ and $\overline f \overline g = \overline{fg}$.

## Lemma 1
$R = \{ \overline a_0 + \overline a_1 t + \cdots + \overline a_{m-1} t^{m-1} \mid a_i \in F \}$.

---

- The proof supposes that by the division algorithm $f = qh + (a_0 + a_1 x + \cdots a_{m-1} x^{m-1})$.

- Now consider $\overline f$. Since $\overline h =0$ we have $\overline f = \overline a_0 + \overline a_1 t + \cdots + \overline a_{m-1} t^{m-1}$.

## Lemma 2
The map $\theta: F \to R$ given by $\theta(a) = \overline a$ is a one-to-one ring homomorphism.

---

- The homomorphism part is obvious so I'm just gonna summarize the proof part for one-to-one-ness.

- Let $\theta(a) = \overline 0$. Then $a + A = 0 + A$ so $a \in A$. If $a \neq 0$ then since $a$ is unit in $F$ it follows that $A=F[x]$ by Theorem 3.3.2. Hence $F[x] = \langle h \rangle$ so since $1 \in F$ we have $1=hf$ for some $f$ so $\deg h = 0$, CONTRADICTION!!! Hence $a = 0$ and one-to-one.

- Notice that $\theta(F) \cong F$ so we can identify $F$ as a subring of $R$! Hence lemma 1 takes the form $R = \{ a_0 + a_1 t + \cdots +  t^{m-1} \mid a_i \in F \}$.

## Lemma 3
If $a_0 + a_1 t + \cdots a_{m-1} t^{m-1} = b_0 + b_1 t + \cdots b_{m-1} t^{m-1}$ in $R$, then $a_i = b_i$ for all $i$.

- This is basically showing that the set $\{ 1, t, t^2, \dots \}$ is linearly independent so it is a basis of $R$ as an $m$-dimensional vector space over $F$.

## Lemma 4

In the ring $R$, we have $h(t)=0$.

---

- In example 1 we had $h(x) = x^2 + 1$ and $t = i$, so $h(t) = 0$. This lemma is a generalization of that, so this basically allows multiplication to be defined, because it involves higher powers of $t$!

## Theorem 2

Let $F$ be a field and let $h$ be a monic polynomial in $F[x]$ of degree $m \geq 1$. Then the factor ring $F[x] / \langle h \rangle$ is given by
$$
\frac{F[x]}{\langle h \rangle} = \{ a_0 + a_1 t + \cdots + a_{m-1} t^{m-1} \mid a_i \in F, h(t) = 0 \}.
$$

Moreover, this representation of the elements of $F[x] / \langle h \rangle$ is unique:
$$
a_0 + a_1 t + \cdots + a_{m-1} t^{m-1} = b_0 + b_1 t + \cdots b_{m-1} t^{m-1} 
$$
if and only if $a_i = b_i$ for each $i$.

---

- It's actually the case that this theorem works for *any commutative ring!*

- This theorem is basically a compliation of all our previous results; a summary.

- This theorem also completely describes the ring $F[x] / \langle h \rangle$.

- Theorem allows us to describe higher powers of $t$ in terms of lower powers.

- Multiplication REALLY depends on $h$.

## Example 3

This is example describes the ring $\mathbb Z_2[x] / \langle x^2 - 1 \rangle$. And it's described as $\mathbb Z_2[x] / \langle x^2 - 1 \rangle = \{ a + bt \mid a,b \in \mathbb Z_2[x], g^2 = 1 \}$. Notice that if we write $t=g$ because $t^2 = g^2 = 1$ we get the cyclic group $G = \{ 1,g \}$. Basically it's a linear combination of elements of $G$ with coefficients from $\mathbb Z_2$. Hence we call it the ***<u> FACTOR RING!!!! </u>*** and denote it as so:
$$
\mathbb Z_2 G = \{ a+bg \mid a,b \in \mathbb Z_2, g^2 = 1 \}.
$$


This can be generalized with any field $F$ and if $g^n = 1$ we write it as so:
$$
FG = \{ a_0 + a_1 g + \cdots + a_{n-1} g^{n-1} \mid a_i \in F, g^n = 1 \}.
$$

## Example 5

Here, the example shows that $R = \mathbb Q [x] / \langle x^2 - 2 \rangle$ is *isomorphic* to $\mathbb Q(\sqrt 2)$!!! This is pretty cool because it allows us to construct cool looking fields. This leads us to our next theorem: !!!

## Theorem 3

Let $h$ be a monic polynomial of degree $m \geq 1$ in $F[x]$, where $F$ is a field. The following conditions are equivalent:

- (1) $F[x] / \langle h \rangle$ is a field.
- (2) $F[x] / \langle h \rangle$ is an integral domain.
- (3) $h$ is irreducible over $F$.

---

- The proof starts by saying that (1) obiously implies (2). For the second part it assumes for a contradiction that $h=fg$ so $0 + \langle h \rangle = h + \langle h \rangle = (f+\langle h \rangle)(g+\langle h \rangle)$. Thus either $f + \langle h \rangle$ or $g + \langle h \rangle$ is $0$. If we suppose the former then $f \in \langle h \rangle$ so $f=qh$ for some $q$ and so $h = qh g$ so $qg=1$ so $\deg g = 0$, CONTRADICTION!!!

- Then for the final one it goes a little bit like this:
  - Let $f + A \neq 0$, so $f \not\in A$ so $h \nmid f$. Let $d = \gcd(f,h)$. Because $h$ is irreducible and both polynomials are monic, we have either $d=1$ or $d=h$. If $d=h$ then by definition $d \mid f$, a contradiction! So $d=1$, so by Theorem 4.2.10 we know there exist $u,v$ such that $1=uh + vf$, so $vf = uh-1 = 1$ in $F[x] / \langle h \rangle$, so $(v+ \langle h \rangle)(f+ \langle h \rangle) = 1 + \langle h \rangle$ so $f$ DOES have an inverse!!! So now we know that $F[x]/\langle h \rangle$ IS a field!!!

- Ok, now here's the intuiton:
  -  1 and 2 are basically the same statement (definetely not irl though lol) but how do they relate to hte idea that $h$ is irreducible? Well if we remember why $\mathbb Z / \mathbb Z_p$ inverse, it's because $\mathbb Z_p$ is prime!!! Same thing here but with polynomials.

### SUPER COOL THING

In example 6 it is shown that if $p$ is prime and $p \equiv 3 \pmod 4$, then a field off $p^2$ elements exists. Generalizing, if $h$ is monic and irreducible of degree $m$, then the field $F[x] /\langle h \rangle$ has exactly $p^m$ elements. So we can construct a field of order $p^m$ for all primes $p$ and integers $m \geq 1$. This cool idea is discussed more in section 6.4.

## Kronecker's Theorem
If $F$ is a field and $f$ is any polynomial in $F[x]$ of positive degree, there is an extension field of $F$ in which $f$ has a root.
