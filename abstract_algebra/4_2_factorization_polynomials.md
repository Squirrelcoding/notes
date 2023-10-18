# 4.2 Factorization of polynomials over a field

Every integer $n \geq 2$ can be factored into primes. Similarly, polynomials in the polynomial $F[x]$ where $F$ is a field can be factored into smaller prime-like polynomials. This section is about that theorem and discussing other things along the way

---

### Example 1

Every linear polynomial is irreducible over $F$.



## Irreducible polynomials

If $F$ is a field, a polynomial $p \neq 0$ is called an irreducible polynomial (and we say that $p$ is irreducible over $F$) if:
- (1) $\deg p \geq 1$.
- (2)  If $p = fg$ in $F[x]$, then either $\deg f = 0$ or $\deg g = 0$.

Polynomials that are not irreducible are called reducible.

---

- This definition is analogous to the definition of a prime in $\mathbb Z$. The definition was formed like this:
  - If $p$ is a prime, then if $p=ab$ then either $a = \pm 1$ or $b = \pm 1$. That is, either $a$ or $b$ is a unit. 

  - Here, the factorization of $p$ is called trivial. In general, a factorization in a field $F$ ($ab$) is called trivial if either $a$ or $b$ is a unit.

  - Condition (1) makes sure that $p$ isn't a unit in $f$ because then the trivial factorization would be allowed.

### Example 2

If $F$ is a field and $p$ is irreducible in $F[x]$, and if $0 \neq a \in F$, then $ap$ is also irreducible.

---

Notice that if $f = ap$ where $a \in F$ is irreducible, then $p = a^{-1} f$ is also irreducible by example 2 so we can just work with monic polynomials because it's more convenient.

## Theorem 1
Let $F$ be a field and consider $p$ in $F[x]$ where $\deg p \geq 2$.
- (1) If $p$ is irreducible, then $p$ has no root in $F$.
- (2) If $\deg p$ is $2$ or $3$ then $p$ is irreducible if and only if it has no root in $F$.

---

- The proof for one works like this:
  - Assume $p$ has root.
  - Then since $F$ is field by factor theorem $p=(x-a)q$.
  - Contradiction.

- The proof for (2) works like this:
  - Assume $p$ has no root.
  - Assume $p=fg$.
  - Clearly $f$ and $g$ don't have roots either.
  - Hence $\deg f, \deg g \neq 1$.
  - By hypothesis, $\deg f + \deg g = \deg p$ is $2$ or $3$.
  - Because of addition, this means that the degree of either $f$ or $g$ is $0$.

- Note that this DOES imply that there are reducible polynomials with no roots. For example, in $\mathbb R$ we have $x^4 + 5x^2 + 4 = (x^2+1)(x^2+4)$.

- As an example, we have $x^2 + 1$ not being reducible over $\mathbb R$ because it has no root in $\mathbb R$!!!

- Este teorema no exactamente funciona cuando $\deg p > 3$ porque asi la prueba no funcionaria. Por que? Pues, hay mas opciones! Podemos escojer $\deg f = 3$ y $\deg g = 1$, como un ejemplo.


- NOTE: The phrase "$p$ is irredicible" is MEANINGLESS UNLESS WE SPECIFY A FIELD!!!!!!!!!!!!

## Theorem 2 (***Fundamental Theorem of Algebra***)

If $f \in \mathbb C[x]$ is a nonconstant polynomial, then $f$ has a root in $\mathbb C$.

## Theorem 3
As usual, let $\mathbb C$ denote the field of complex numbers.

- (1) If $\deg f = n \geq 1$, $f \in \mathbb C [x]$, then $f$ factors completely as
  $$
  f = u (x - u_1)(x-u_2) \cdots (x-u_n)
  $$
  where $u$ is the leading coefficient of $f$ and $u_1, u_2, \dots, u_n$ are the (not necessarily distinct) roots of $f$ in $\mathbb C$.
- (2) The only irreducible polynomials in $\mathbb C$ are linear.

---

- This is pretty intuitive.

- (2) is clear from (1) lol

- The proof is by induction, it sarts with $n=1$ by doing $f = ux + b = u(x + u^{-1} b)$. Then for the induction step it proceeds to assume from Theorem 2 that $f$ with degree $n+1$ has at least one root so $f=(x-u_1)q$. But $\deg q = n$ so the inductive hypothesis applies so now $f = (x-u_1)u(x - u_2) \cdots (x - u_n)$.

## Quadratics

The famous quadratic formula we all know and love is
$$
u = \frac{1}{2a} \left[ -b \pm \sqrt{ b^2 -4ac } \right].
$$

Here, the quantity $b^2 - 4ac$ is called the discriminant. If $q$ is irreducible in $\mathbb R[x]$then $b^2 < 4ac$. Notice that then we have the roots

$$
u = \frac{1}{2a} \left[ -b + i\sqrt{ 4ac - b^2 } \right] \qquad \bar u = \frac{1}{2a} \left[ -b - i\sqrt{ 4ac - b^2 } \right].
$$

THIS MEANS THAT COMPLEX ROOTS IN QUADRATICS COME IN PAIRS!!!!!!!!!!!!!

## Theorem 4

Every nonconstant polynomial $f$ in $\mathbb R[x]$ factors as 
$$
f = a(x-r_1)(x - r_2) \cdots (x - r_m) q_1 q_2 \cdots q_k,
$$
where $a$ is the leading coefficient of $f$; $r_1, r_2, \dots, r_m$ are the real roots of $f$ (if any); and $q_1, q_2, \dots, q_k$ are monic irreducible real quadratics (perhaps none).

---

- The way the proof works is that it shows that if $u$ is a complex root in $f$, then so is its conjugate. So by the factor theorem $f = (x-u)(x-\bar u) g$ where $g$ is some polynomial, and so $(x-u)(x- \bar u)$ forms a monic irreducible quadratic in $\mathbb R[x]$ and this is basically the gist of the proof.

## Corollary
The irreducible polynomials in $\mathbb R [x]$ are either linear or quadratic.

---

The reason only linear and quadratics exist here is that if we have anything of degree 3 or higher, we can just factor it!!! But with quadratics and linears, we can't!!!

## Irreducibles over the rationals

Theorems 3 and 4 before completely describe the irreducibles in $\mathbb C[x]$ and $\mathbb R[x]$. Ohh... but not so much in the rationals. Like, what about $x^2 - 2$? If $f$ is in $\mathbb Q[x]$ and $m$ is the lcm of the denominators of the coefficients, entonces $mf \in \mathbb Z[x]$, so lots of questions from the rationals can be answered in the integers.

## Theorem 5 (Gauss' Lemma)

Let $f = gh$ in $\mathbb Z[x]$. If a prime $p \in \mathbb Z$ divides every coefficient of $f$, then either $p$ divides every coefficient of $g$ or $p$ divides every coefficient of $h$.

---

- This is actually a pretty slick proof, and it involves the following concept.
  - If $f = a_0 + a_1 x + \cdots + a_n x^n$ in $\mathbb Z [x]$, the polynomial
  $$
  \bar f = \bar a_0 + \bar a_1 x + \cdots + \bar a_n x^n
  $$
  in $\mathbb Z_p[x]$ is called the reduction of $f$ modulo $p$.

- So if $p$ divides $f$, then $f = 0$ in $\mathbb Z_p[x]$, right? But so is $gh$, so $gh=0$. Since $\mathbb Z_p[x]$ is a field, it is also an integral domain so either $g$ or $h$ is $0$, which implies that $p$ divides one of them.

- The actual proof uses a homomorphism but same idea holds.

## Theorem 6

let $f$ be a nonconstant polynomial in $\mathbb Z[x]$.
1. If $f = gh$ with $g$ and $h$ in $\mathbb Q [x]$, then $f= g_0 h_0$ where $g_0$ and $h_0$ are in $\mathbb Z[x]$.
2. $f$ is irreducible in $\mathbb Q [x]$ if and only if it has no proper factorization in $\mathbb Z [x]$.

---

- The way the proof works is pretty freaky brooo. So it lets $a$ and $b$ be the least common multiples of the denominators of the coefficients of $g$ and $h$, respectively. And then it writes $f_1 = a f$ and $g_1 = b g$. So now we have $abf=g_1 h_1$. Notice now that $g_1,h_1 \in \mathbb Z[x]$.

- Now consider a prime $p$ that divides $ab$. Gauss' lemma says then that $p$ divides either $g_1 = ag$ or $h_1 = bh$. So now we have $\frac{ab}{p} f = g_2 h_2$ where $g_2$ and $h_2$ are new polynomials that are still in $\mathbb Z [x]$.

- Now we repeat this until we just have $f = g_k h_k$!!!

- Basically, we just multiply both sides so we get integers on both sides and then carefully cancel out the integers we don't need on $f$'s side.

---

Notice that $f \in \mathbb Q [x]$ is irreducible if and only if $af \in \mathbb Z [x]$ ($a$ is some integer) is irreducible by example 2. And part (2) of Theorem 6 says that $af$ is irreducible if and only if $af$ has no proper factorization in $\mathbb Z[x]$.

Therefore, to $f \in \mathbb Q [x]$ is irreducible if and only if $af$ has no proper factorization in $\mathbb Z [x]$.

---

## Lemma 1

If $f \in \mathbb Z[x]$ is monic and $f=gh$ in $\mathbb Z[x]$, then we may assume that both $g$ and $h$ are monic.

---

- This is pretty intuitive once you think about the multiplication.

- We can use this test to find out whether a polynomial is irreducible in $\mathbb Q[x]$, and hence proper factorization in $\mathbb Z [x]$. This is used in example 8, but this method is bad for polynomials of higher degree $(> 5)$. But we also have this test:

## Theorem 7 (Modular irreducibility test)

Let $0 \neq f \in \mathbb Z[x]$ and suppose that a prime $p$ exists such that

- (1) $p$ does not divide the leading coefficient of $f$ - for example if $f$ is monic.

- (2) The reduction $\overline f$ of $f$ modulo $p$ is irreducible in $\mathbb Z_p[x]$.

Then $f$ is irreducible in $\mathbb Q [x]$.

---

- The way the proof goes is like this:
  - Since $p$ does not divide the leading coefficient, the coefficient will remain nonzero so $f$ can keep its degree... *for now*.

  - If we assume that $f$ is not irreducible in $\mathbb Q[x]$, then we have $f=gh$ where $g,h \in \mathbb Z[x]$ by Theorem 6. but $\deg \bar g \leq \deg g < \deg f = \deg \bar f$ and similarly $\deg \bar h < \deg \bar f$ so $\overline f = \overline g \overline h$ has a proper factorization in $\mathbb Z_p[x]$, contradicting (2).

- We also have another test!!!! By Ei<u>***se***</u>nstein, not Einstein.

## Theorem 8 (Eisenstein Criterion)

Consider $f = a_0 + a_1 x + \cdots + a_n x^n$ in $\mathbb Z [x]$, where $n \geq 1$ and $a_n = 0$. Suppose that a prime $p \in \mathbb Z[x]$ exists such that

- (1) $p$ divides each of $a_0, a_1, \dots, a_{n-1}$.
- (2) $p$ does not divide $a_n$.
- (3) $p^2$ does not divide $a_0$.

Then $f$ is irreducible in $\mathbb Q[x]$.

---

- The proof works by contradiction. So $f=gh$ is a prop. factorization in $\mathbb Z[x]$.

  - Then write $g = b_0 + b_1 x + \cdots + b_m x^m$ y $h = c_0 + c_1 x + \cdots + c_t x^t$.

  - Because $p$ divides $a_0$, it should divide $b_0 c_0$. But $p^2$ doesn't divide this, so there should only be one $p$ in the prime factorization of $a_0$!!!

  - Hence $p$ divides strictly one of $b_0$ or $c_0$, so WLOG we say $b_0$. ***SO $p$ DOES NOT DIVIDE $c_0$!!!***
  
  - By (2), $p$ does not divide $b_m$.

  - Let $b_k$ be the first integer in the list $b_0, b_1, \dots, b_m$ such that $p$ does <u>***not***</u> divide $b_k$. From the previous statement we know that there should exist such a $b_k$.

  - Because $f$ has a proper factorization, $m < n$ so $k \leq m < n$ so $k < n$ so $p$ should divide every term in the sum $a_k = b_k c_0 + b_{k-1} c_1 + \cdots + b_0 c_k$ by (1).

  - Thus $p$ should also divide $b_k c_0$. So it divides one of $b_k$ or $c_0$. Contradiction!!!

- The cool and interesting thing about these types of proofs (including theorem 7) is that it works for *any* prime $p$!!

- Note thtat $x^n - 2$ is irreducible in $\mathbb Q[x] - 2$ is irreducible in $n \geq 1$ by the Eisenstein criterion. So it contains an irreducible polynomial of every positive degree!!!

- The $p$th cyclotomic polynomoal $\Phi_p = x^{p-1} + x^{p-2} + \cdots p + 1$ is irreducible in $\mathbb Q[x]$!!!

## Unique Factorization

Theorems 3 and 4 say that every polynomial is the product of a constant times some monic irreducible factors in $\mathbb R[x]$ and $\mathbb C[x]$!!! Now we can show that this factorization is unique for <u>***any***</u> field $F[x]$!!!

You know how in $\mathbb Z$ every integer is the product of a unit $(\pm 1)$ and some primes? Well, for a field $F$ we can have the analogue of $F$ being that for every nonconstant polynomial, it can be factored as a unit times some irreducible polynomials. 

But because of the trivial factorization $f = a (a^{-1} f)$ we require that the irreducible polynomials be monic. ***THIS IS ANALOGOUS TO REQUIRING THAT PRIMES BE POSTIIVE!!!*** This works because theorem 9 exists.


### Theorem 9

Let $F$ be a field and let $f$ and $g$ be nonzero monic polynomials in $F[x]$, each of which divides the other. Then $f=g$.

---

- This is kinda intuitive because if $f=qg$ and because $f$ and $g$ are both monoids and stuff.

## Corollary

If $F$ is a field and $p \in F[x]$ is monic, then the following are equivalent:
- (1) $p$ is irreducible.
- (2) If $d$ is a monic divisor of $p$ then either $d=1$ or $d=p$.

## Theorem 10

Let $f$ and $g$ be nonzero polynomials in $F[x]$, where $F$ is a field. Then a uniquely determined polynomial $d$ exists in $F[x]$ satisfying the following conditions.

- (1) $d$ is monic.
- (2) $d$ divides both $f$ and $g$.
- (3) If $h$ divides both $f$ and $g$, then $h$ divides $d$.
- (4) $d=uf + vg$ for some polynomials $u$ and $v$ in $F[x]$.

Finally, $d$ is the unique polynomial satisfying (1), (2), and (3).

---

- The analogy to $\mathbb Z$ here is that $d$ is the greatest common divisor of $f$ and $g$.

- The way it works here is it has a set $X = \{ uv + vg \mid u,v \in F[x] \}$. Then it says "ok bro choose $d=uf+vg$" be the monic polynomial of smallest degree.

- Then (1) and (4) are automatically satisfied!!!

- And (3) is a consequence of (4)!!!

- To prove (2) it uses the division algorithm with and we end up with $f=qd+r$ where either $r=0$ or $\deg r < \deg d$.

- If we let $r \neq 0$ and $a$ is the leading coefficient of $r = (1-qu)f - (qv)g$, then $a^{-1} r$ is a monic member of $X$ WITH DEGREE LESS THAN $d$!!! THIS IS A CONTRADICTION!!! So clearly we have $r=0$!! So $d \mid f$ because $f=qd$.

- Similarly $d$ divides $g$.

- To prove uniquenesss it says that if $d_1$ satisfies the properties then $d$ and $d_1$ divide each other so by the collary to theorem 9 they are obviously equal lollllz.

- Here, $d$ is called the gcd of $f$ and $g$.

- Note that this theorem allows $d=1$. Don't let this fool ya kids arr!!!

## Example 15

This example basically uses the analogy of the euclidian algorithm for integers to polynomials lol

## Theorem 11
Let $p \in F[x]$ be irreducible, $F$ a field. If $p$ divides a product $f_1, f_2, \dots, f_n$ of nonzero polynomial in $F[x]$, then $p$ divides one of the $f_i$.

---

- This is the analogy to Euclid's lemma for the integers. It's also pretty intuitive too lol

- The proof is by induction and the base case is $n=2$, so $p \mid fg$. Then it lets $d = \gcd(p,f)$.

- Since $p$ is irreducible, we have either $\deg d = 0$ or $\deg d = \deg p$. If $\deg d = \deg p$ then $p=ad$, $a \in F$. So $d = a^{-1} p$ and since $d \mid f$ we have $f=qa^{-1}p$ for some $q$ so $p \mid f$.

- If $\deg d = 0$ then $1=up + vf$ and multiplying by $g$ gives $g = upg + vfg = upg + v(qp)$ so $p \mid g$ so done.

- Induction step is pretty easy.

## Theorem 12 (Unique Factorization Theorem)
If $F$ is a field, let $f$ be a nonconstant polynomial in $F[x]$. Then
- (1) $f = a p_1 p_2 \cdots a_m$ where $a \in F$ and $p_i$ is monic and irreducible for all $i$.
- (2) The factorization in (1) is unique except for the order of the factors.

---

- It uses strong induction to prove (1). And it basically requires us to show that $f = q_1 q_2 \cdots q_m$ where each $q_i$ is irreducible.

- If $n=1$ then $f$ is linear and hence irreducible.

- Otherwise $f = gh$, where $0 < \deg g, \deg h < n$. And $g$ and $h$ are factorizable by strong induction!!!

- To prove (2), it writes $f = a p_1 p_2 \cdots p_m = b q_1 q_2 \cdots q_k$ WHICH IS OF MINIMAL DEGREE!!! Since each factor in each side is monic, it follows that $a=b$.

- By Theorem 11, $p_1$ must divide some factor in the other factorization so lets say $q_1$. Since $\deg p_1 \neq 0$ we have $\deg p_1 = \deg q_1$ cause they both irreducible. And since they are both monic they are ***not*** scalar multiples so $p_1 = q_1$. Cancelling leaves us with another polynomial WITH LESSER DEGREE which contradicts the choice of $f$.
