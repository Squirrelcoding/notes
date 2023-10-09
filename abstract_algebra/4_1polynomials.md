# 4.1 Polynomials
Polynomials have been studied four thousands of years. They are pretty cool.


## Indeterminate

If $R$ is any ring, a symbol $x$ is called an indeterminate over $R$ if
$$
a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n = 0 \space \text{ implies } \space a_0 = 0 \space a_i = 0 \text{ for each } i.
$$.

It's basically a transcedental.

---

- This is like linear independence.

Clearly if the expressiona above makes sense, then $x$ and $a_i$ must belong to ring, so this lemma below constructs such a ring.

## Lemma 1
Given a ring $R$, there exists a ring $S$ with the following properties:
- (1) $R \subseteq S$ is a subring.
- (2) There exists $x \in S$ such that $x$ is an indeterminate over $R$.
- (3) If $a \in R$ then $ax=xa$.

---

- This lemma is pretty weird but it basically says that for any ring $R$ we can construct a larger ring $S$ such that $R \subseteq S$, and that $S$ has an indeterminate over $R$ that commutes with every element in $R$.

- So how does the proof work? Basically we can define $S$ to be the set of sequences of $R$. If you'r reading this you're familiar with sequences and so we can define multiplication as $[a_k) [b_k) = a_0 b_k + a_1 b_{k-1} + \cdots + a_{k-1} b_1 + a_k b_0$. If $a \in R$ and we consider $a = [a, 0, 0, \dots )$ as an element of $R$ we can see that $R$ is a subring of $S$. Then if $x = [0, 1, 0, 0, \dots)$ then using the multiplication defined earlier we have ourselves an undeterminate!!!

- If $x$ is a indeterminate over a ring $R$  and if $S$ is as in Lemma 1 we have
  $$
  R[x] = \{ a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n \mid n \geq 0, a_i \in R \text{ for each } i \}
  $$
  which is a subring of $S$ called the ring of polynomial over $R$. And an element $f \in R[x]$ is called a polynomial. The elements $a_i$ in $R$ are called coefficients which are uniqely determined by $f$.

- Two polynomials are equal if and only if each of their coefficients are equal.

- A root $x$ is an element in $R$ such that $f(x)=0$.

- If $f = a_0 + a_1 x + a_2 x^2 + \cdots$ we call $a_0$ the constant coefficient and it turns out ***THAT $R$ is THE SUBRING OF ALL CONSTANT POLYNOMAILS IN $R[x]!!!$***

## Lemma 2
Let $f = a_0 + a_1 x + a_2 x^2 + \cdots$ and $g = b_0 + b_1 x + b_2 x^2 + \cdots$ be polynomials in $R[x]$ where $R$ is any ring. Then
- (1) $f=g$ if and only if $a_i = b_i$ for each $i$.
- (2) $f + g = (a_0 + b_0) + (a_1 + b_1)x + (a_2 + b_2)x^2 + \cdots$.
- (3) $fg = a_0 b_0  + (a_0 b_1 + a_1 b_0) x + (a_0 b_2 + a_1 b_1 + a_2 b_0)x^2 + \cdots$
- (4) The coefficient of $x^k$ in $fg$ is $\sum_{i+j=k} a_i b_j$.

---

- This lemma is pretty straightforward. It's just the usual properties of polynomials we all know and love, translated into abstract algebra.

 - As an example, in $\mathbb Z [x],$ we have $(x+1)^3 = x^3 + 1$ because $3=0$ in $\mathbb Z [x]$.

 ## Theorem 1
 Let $R$ be a ring and let $x$ be an indeterminate over $R$. Then:
 - (1) $R[x]$ is a ring.
 - (2) $R$ is the subring of all constant polynomials in $R[x]$.
 - (3) If $Z = Z(R)$ denotes the center of $R$, then the center of $R[x]$ is $Z[x]$.
 - (4) In particular, $x$ is in the center of $R[x]$.
 - (5) If $R$ is commutative, then $R[x]$ is commutative.

 ## Lemma 3

Let $\langle x \rangle = \{ xf \mid f \in R[x] \}$ denote the set of all multiples of $x$ in $R[x]$. Then $\langle x \rangle$ is an ideal of $R[x]$, and $R[x] / \langle x \rangle \cong R$.

---

- Like the lemma said, $\langle x \rangle$ is basically the set of all polynomials without a constant term. If you multiply two polynomials without constnat terms, you get another polynomial without a constant term! So it's clearly ideal.

- The way it does the second part is using the isomorphism theorem. The specific cosets used in the isomorphism theorem are the sets where every polynomial starts with the same constant, which can get mapped to $R$. And now its obvious why $\langle x \rangle$, the ideal with the $0$ constant, is the ideal here.

## Theorem 2
let $R$ be a domain. Then:
- (1) $R[x]$ is a domain.
- (2) If $f,g \neq 0$ in $R[x]$, then $\operatorname{deg}(fg) = \operatorname{deg} f + \operatorname{deg} g$.
- (3) The units in $R[x]$ are the units in $R$.

---

- Remember if $R$ is a domain then the product of two nonzero elements is another nonzero element! So the degree of their product is the sum of their degrees, giving (2)!!
- (3) is proven by if $fg=1 = gf$ and since degrees are nonnegative it shows that $f$ and $g$ ar constant polynomials so they are alos units in $R$.

-  If $R$ weren't a domain then if $f=1+2x$ in $\mathbb Z_4[x]$ gives
$$
f^2 = (1+2x)(1+2x) = 1
$$

## Theorem 3
Let $R$ be any ring and let $f \neq 0$ and $g \neq 0$ be polynomals in $R[x]$. If the leading coefficient of either $f$ or $g$ is a unit in $R$, then
- (1) $fg \neq 0$ in $R[x]$.
- (2) $\operatorname{deg} fg = \operatorname{deg} f + \operatorname{deg} g$.

## Division Algorithm

Let $R$ be any ring and let $f$ and $g$ be polynomials in $R[x]$. Assume that $f \neq 0$ and that the leading coefficient of $f$ is a unit in $R$. Then uniquely determined polynomials $q$ and $r$ exist in $R[x]$ such that
- (1) $g = qf + r$.
- (2) Either $r=0$ or $\operatorname{deg} r < \operatorname{deg} f$.

---

- This is a pretty intuitive idea.

- The way the INDUCTION proof on $m=\operatorname{deg} g$ is done is that it first assumes that either $g=0$ or $\operatorname{deg} g < \operatorname{deg} f$, and in this case we can simply write $g=0f+g$, because this satisfies the hypothesis.

- Then it goes on assume not and lets $f = ux^n + ax^{n-1} + \cdots$ and $g = bx^m + cx^{m-1} + \cdots$. Then it constructs a polynomial 
  $$
  g_1 = g - bu^{-1} x^{m-n} f \\
      = (bx^m + cx^{m-1} + \cdots) - bu^{-1} x^{m-n}(ux^n + ax^{n-1} + \cdots)
  $$
  This is where the fact that $u$ is a unit comes into play - it allows us to cancel the largest term of $f$ out (NOW YOU KNOW WHY IT NEEDS IT TO BE A UNIT!!!), to get a polynomial $g_1$ whose degree is $m-1$, allowing us to use the hypothesis!!! So then $g_1 = q f + r$ and thus we can add $bu^{-1} x^{m-n} f$ to the other side to get
  $$
  g = (q + bu^{-1} x^{m-n}) f + r.
  $$

- Then it proves uniqueness by contradicting and starts by assuming that $g = q f + r = q_1 f + r_1$. It uses Theorem 3 to show that $(q_1 - q) f \neq 0$ so theorem 3 tells us that
$$
\operatorname{deg}(r - r_1) = \operatorname{deg} [(q_1 - q)f] = \operatorname{deg}(q_1 - q) + \operatorname{deg} f
$$
but this shows that $\operatorname{deg}(r-r_1) > \operatorname{deg} f$ so it contradicts everything!!!

- The division algorithm is better when $R$ is commutative, because if $f(x) = (x-a)(x+b)$, then if we expand $f$ and plug in $a$ we get $f(a) = ba-ab$, which doesn't make sense if $ba \neq ab$, because $x$ must commute with every $r \in R$, and this is problematic unless $a$ is in the center of $f$. Hence $a$ must be in the center of $R$. 

### **Therefore if $f = a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n$, it need not be the case that $f(a) = a_0 + a_1 a + a_2 a^2 + \cdots + a_n a^n$**

- But we *do* have the following result:

## Theorem 5 (Evaluation Theorem)
Let $R$ be a ring and let $a$ be an element in the center $Z(R)$ of $R$. Define a mapping $\varphi_a: R[x] \to R$ by
$$
\varphi_a(a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n) = a_0 + a_1 a + a_2 a^2 + \cdots + a_n a^n.
$$

Then $\varphi_a$ is an onto ring homomorphism.

---


- This tells us that although it need not be the case that $f(a) \neq a_0 + a_1 a + a_2 a^2 + \cdots + a_n a^n$, we *do* know that there is an (albeit weaker) homomorphic relation between them, whenever $a$ commutes.

- It's onto and preserves the unity cause for all $r \in R$, $\varphi_a(r + 0x + 0x^2 + \cdots) = r$ so $\varphi_a(1) = 1$.

- It's pretty obvious why the mapping preserves operations lol

- **If $a$ commutes**, then we call $f(a) = a_0 + a_1 a + a_2 a^2 + \cdots + a_n a^n$ the evaluation of $f$ at $a$.

- The  map in Theorem 5 is called the evaluation map cause $\varphi_a(f) = f(a)$ for all $f \in R[x]$.

- The gist of this theorem is that $(fg)(a) = f(a) g(a)$ and $(f+g)(a) = f(a) + g(a)$.

- A useful consequence is that if $f=gh$ and if $g(a)=0$ and $a \in Z(R)$, then $f(a)=0$. And if $f=(x-a)h$ then $f(a)=0$ for all $h$.

## Commutative rings

Evaluation is useful when $R$ is commutative, so we assume it ***FOR THE REST OF THIS CHAPTER!!!***. 

If $a \in R$ and $R$ is commutative, then $\langle a \rangle = Ra$ is an ideal of $R$ called the principal ideal generated by $a$.

## Theorem 6
Let $R$ be a commutative ring, let $a \in R$, and let $f \in R[x]$. Then
- (1) ***Factor Theorem.*** $f(a) = 0$ if and only if $f = (x-a)q$ for some $q \in R[x]$; that is, if and only if $f \in \langle x-a \rangle$.
- (2) ***Remainder Theorem*** If $f$ is divided by $x-a$, the remainder is $f(a)$.

---

- First one is pretty obvious.

- The second one stems from the fact that if $f(x)=(x-a)q+r$, then $f(a)$ gives $r=f(a)$.

- The reason we need $R$ to be commutative is that
$$
x^2 + 1 = (x+i)(x-i) = (x+j)(x-j) = (x+k)(x-k)
$$
in $\mathbb H$ (the quaternions), a noncommutative ring. So the argument of plugging in $x$ won't work because not all quaterions are central!!! 

## Corollary

If $R$ is commutative, let $\varphi_a: R[x] \to R$ be evaluation at $a \in R$. Then $\ker \varphi_a = \langle x-a \rangle$ and $R[x] / \langle x-a \rangle \cong R$.

---

- The proof itself is pretty obvious.

- The corollary basically says that if you group together all polynomials whose evaluation at $a$ is the same, you can form a ring! And of course $\ker \varphi_a = \langle x-a \rangle$ gets mapped to $0$, because then $f \in \ker \varphi_a$ implies $f(a) = (x-a)q$ so $f(a)=0$!!!

## Roots

If $f \in R[x]$ where $R$ is commutative then $a \in R$ is called a root of $f$ if it satisfies

- $f(a) = 0$.
- $f = (x-a)q$ for some $q \in R[x]$.
- $f \in \langle x - a \rangle$.

All of these statements are actually equivalent by the factor theorem lol

## Multiplicity

The multiplicity is just the amount of times a root appears in a polynomial factorization. That is, in other words, if $f = (x-a)^m q$ where $q \in R[x]$ and $q(a) \neq 0$, then $a$ has multiplicity $m \geq 1$.

---

Not much can be said about the roots of a commmutative ring. For example $x^2-1$ has no roots in $\mathbb R$ but two in $\mathbb C$ ($\pm i$). BUT WE DO HAVE THEOREM 8!!!!

## Theroem 8
Let $R$ be an integral domain and let $f$ be a nonzero polynomial in $R[x]$ of degree $n$. Then $f$ has at most $n$ roots in $R$.

---

- The proof works by induction, starting with $n=0$ which is obvious. Then it goes on to linear equations and shows that if $a_0 + a a = 0 = a_0 + a b$, then $a=b$ so it really only has up to one root.

- Next, it shows that if $a$ is a root, then $f=(x-a)q$ for some $q$, duh. But if we assume that there exists a $b \neq a$ that is a root, then $f(b) = (b-a)q(b)$ so $q(b) = 0$ cause $R$ is an integral domain. But because $\operatorname{deg} q = n-1$, it has at most $n-1$ roots by induction. so there exist $n-1$ roots distinct from $a$, finishing the proof.

- It's also important for $R$ to be commutative because $x^2+1$ has 8 solutions in $\mathbb H$, the quaternions. ($\pm i, \pm j, \pm k$). And quaterions ARE NOT commutative!!!

## Theorem 9 (Rational Roots Theorem)

Let $f = a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n$ be a polynomial in $\mathbb Z[x]$, where $a_0 \neq 0$ and $a_n \neq 0$. Then every rational root of $f$ has the form $\frac{c}{d}$ where $c \mid a_0$ and $c \mid a_n$.

---

- This proof works by writing taking a rational $c/d$ and assuming that $f(c/d) = a_0 + a_1 \frac{c}{d} + \cdots + a_n \frac{c^n}{d^n} = 0$. Then multiplication by $d^n$ yields
$$
0 = a_0 d^n + a_0 c d^{n-1} + \cdots + a_{n-1} c^{n-1} d + a_n c^n 
$$
Moving $c$ to the left-hand side and factoring shows that $c \mid a_0 d^m$. But $\gcd(c, d^m) = 1$ so $c \mid a_0$. A similar argument works for showing that $d \mid a_n$.

## Corollary
The only rational roots of a monic polynomial in $\mathbb Z [x]$ are integers.

---

- Pretty obvious.

- A pretty cool application of this is to show that if $m \in \mathbb Z$ is not a perfect square, then $\sqrt m$ is irrational.
