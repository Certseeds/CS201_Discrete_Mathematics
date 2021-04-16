<!--
 * @Github: https://github.com/Certseeds/CS201_Discrete_Mathematics
 * @Organization: SUSTech
 * @Author: nanoseeds
 * @Date: 2021-04-09 12:08:27
 * @LastEditors: nanoseeds
 * @LastEditTime: 2021-04-16 19:28:31
 * @License: CC-BY-NC-SA_V4_0 or any later version 
 -->

# CS 201: Discrete Math for Computer Science

# 2020 Spring Semester Midterm Exam

## 16:00 – 18:00, Apr. 10th, 2020

### Total number of questions: $9$

#### Total points: $100$

**Note**: The Midterm exam is **closed book**. Please do *NOT* refer to the textbook or any other references. Any misbehavior will be dealt with severely according toour plagiarism regulation. Please upload your solutions to **Blackboard before 18:30**(You have half an hour to upload!)**No extended submission will beaccepted**! Good luck!

##### Q.1 (11 Points) Consider the proposition $((p{\rightarrow}q){\rightarrow}p){\rightarrow}q)$

###### (1) Construct the truth table for this proposition

The truth table is :

|  $p$  |  $q$  | $p{\rightarrow}q$ | $(p{\rightarrow}q){\rightarrow}p$ | $((p{\rightarrow}q){\rightarrow}p){\rightarrow}q)$ |
| :---: | :---: | :---------------: | :-------------------------------: | :------------------------------------------------: |
|   F   |   F   |         T         |                 F                 |                         T                          |
|   F   |   T   |         T         |                 F                 |                         T                          |
|   T   |   F   |         F         |                 T                 |                         F                          |
|   T   |   T   |         T         |                 T                 |                         T                          |

###### (2) Show that this proposition is *not* logically equivalent to $p{\rightarrow}(q{\rightarrow}(p{\rightarrow}q))$

Two ways to do this:

- Using a truth table

|  $p$  |  $q$  | $p{\rightarrow}q$ | $p{\rightarrow}(p{\rightarrow}q)$ | $p{\rightarrow}(q{\rightarrow}(p{\rightarrow}q))$ |
| :---: | :---: | :---------------: | :-------------------------------: | :-----------------------------------------------: |
|   F   |   F   |         T         |                 T                 |                         T                         |
|   F   |   T   |         T         |                 T                 |                         T                         |
|   T   |   F   |         F         |                 T                 |                         T                         |
|   T   |   T   |         T         |                 T                 |                         T                         |

We now can see that the rightmost column doesnotmatch the right-most column in the truth table for $((p{\rightarrow}q){\rightarrow}p){\rightarrow}q)$

- Using logical equivalences:

 $$p{\rightarrow}(q{\rightarrow}(p{\rightarrow}q)) \equiv \neg p \vee (\neg q \vee (\neg p \vee q)) \\  \equiv (\neg p \vee \neg q) \vee (\neg p \vee q) \\ \neg p \vee T \\ \equiv T$$

 By the truth table for $((p{\rightarrow}q){\rightarrow}p){\rightarrow}q)$, they are  *not* logically equivalent.

##### Q.2 (12 Points) For the following argument, explain which rules of inference areused for each step

"All students are hard-working. There is a student who will go to CMU.Therefore, there is a hard-working student who will go to CMU." The universeis "all members in CSE department".

Answer:  
let  
$s(x)$ be "x is a studnet".  
$c(x)$ be "x will go to CMU".  
$h(x)$ be "x is hard-working".  

"All students are hard-working" means $\forall x (s(x) {\rightarrow} h(x))$  
"There is a student who will go to CMU" means $\exists x (s(x) \wedge c(x))$  

Then

| order |                   step                    |               reason                |
| :---: | :---------------------------------------: | :---------------------------------: |
|   1   |      $\exists x (s(x) \wedge c(x))$       |             hypothesis              |
|   2   |            $s(x) \wedge c(x)$             | existential instantiation using 1.  |
|   3   |                  $s(x)$                   |       simplification using 2.       |
|   4   |   $\forall x (s(x) {\rightarrow} h(x))$   |             hypothesis              |
|   5   |         $s(x) {\rightarrow} h(x)$         |  universal instantiation using 4.   |
|   6   |                  $h(x)$                   |    modus ponens using 3. and 5.     |
|   7   |                  $c(x)$                   |       simplification using 2.       |
|   8   |      $c(x) \wedge h(x) \wedge s(x)$       |    conjunction using 3, 6 and 7.    |
|   9   | $\exists x(c(x) \wedge h(x) \wedge s(x))$ | existential generalization using 8. |

##### Q.3 (9 points) If two sets $A$ and $B$ are both *uncountable* sets, then what kindof sets can$A \cap B$ be,*finite*,*countably infinite* or *uncountable*? Give examples to explain your answer

$A \cap B$ can be finite, e.g. A = $\{ x \in \mathbb{R} | x \geq 0 \}$, B = $\{ x \in \mathbb{R} | x \leq 0 \}$

$A \cap B$ can be countably infinite, e.g. A = $\{ x \in \mathbb{R} | 0 < x < 1 \}$, B = $\{ x \in \mathbb{R} | 1 < x < 2 \}$

$A \cap B$ can be uncountable, e.g. A = $\{ x \in \mathbb{R} | 0 < x < 1 \}$, B = $\{ x \in \mathbb{R} | 0 < x < 2 \}$

##### Q.4 (10 points) Consider the functionf : $\mathbb{R}^2{\rightarrow} \mathbb{R}^2$ defined as $(x,y){\mapsto}(2x−y,2y-x)$. Prove or disprove that $f$ is a bijective function

1. show it is one-to-one.
$x,y,u,v \in \mathbb{R}$, $f(x,y) = f(u,v)$ so

$$(2x - y,2y - x) = (2u - v,2v - u)$$
Then

$$\left\{
  \begin{aligned}
    (1)&&&&   2x - y & = & 2u - v \\
    (2)&&&&   2y - x & = & 2v - u \\
  \end{aligned}
\right.$$

Then

$$ 2x - y + 2(2y - x) = 2u - v + 2(2v - u)$$

Then

$$\left\{
  \begin{aligned}
     x = u \\
     y = v \\
  \end{aligned}
\right.$$

so $f$ is one-to-one

2. now show it's onto

for each element $(u,v) \in \mathbb{R}^{2}$. we want to find $(x,y)$ satisfying $f(x,y) = (u,v)$.
so

$$\left\{
  \begin{aligned}
    2x - y & = & u \\
    2y - x & = & v \\
  \end{aligned}
\right.$$

so

$$\left\{
  \begin{aligned}
    x & = & \frac{2}{3}u + \frac{1}{3}v \\
    y & = & \frac{1}{3}u + \frac{2}{3}v \\
  \end{aligned}
\right.$$

so $f$ is onto.

##### Q.5 (12 points)

###### (1) Derive a formula in terms of $n$ for the summation $\sum_{i=1}^{n}{i \cdot 2^{-i}}$

We start from the summation of the first $n$ terms in the geometric progression.

$$\sum_{i=1}^{n}x^{i} = \frac{x(1-x^{n})}{1-x}$$

Taking the discrete derivative for both sides, we have

$$\sum_{i=1}^{n} i \cdot x^{i-1} = \frac{(x- x^{n+1})'(1-x) - (x - x^{n+1})(1-x)'}{(1-x)^2} \\ = \frac{nx^{n+1} - (n+1)x^n+1}{(1-x)^2}$$

So,

$$\sum_{i=1}^{n} i \cdot x^{i} = \frac{nx^{n+2} - (n+1)x^{n+1}+x}{(1-x)^2}$$

so

$$\sum_{i=1}^{n} i \cdot (\frac{1}{2})^{i} = \frac{n(\frac{1}{2})^{n+2} - (n+1)(\frac{1}{2})^{n+1}+(\frac{1}{2})}{(1-(\frac{1}{2}))^2} \\ = 2 - (n+2)2^{-n}$$

###### (2) Give a formula for $\sum_{i \geq 1}{i \cdot 2^{-i}}$

$$\sum_{i \geq 1} i \cdot 2^{-i} = \lim_{n \to \infin} \sum_{i=1}^{n} i \cdot 2^{-i} \\ = \lim_{n \to \infin}(2 - (n+2) \cdot 2^{-n}) \\ = 2$$

##### Q.6 (10 points) For three positive integers $a$,$b$ and $k$, prove or disprove that

$$gcd(ka,kb) = k \cdot gcd(a,b) $$

Answer:

Let $d = gcd(ka,kb)$, $d' = gcd(ka,kb)$. We want to prove that $d' = kd$

Since $d = gcd(ka,kb)$, By Bezout's identity, there exist integers $s$ and $t$ such that $d = sa + tb$.

Then we have $kd = s(ka)+t(kb)$. Thus, $kd$ is a linear combination of $ka$ and $kb$, This means $d'|kd$.

On the other hand, since $d|a$ and $d|b$, we have $kd|ka$ and $kd|kb$. Then $kd$ is a common divisor of $kd|ka$ and $kd|kb$. However, $d' = gcd(ka,kb)$ is the largest one of the common divisors. It follows that $kd \leq d'$

Therefor, We have $d' = kd$, i.e., $gcd(ka,kb) = kgcd(a,b)$

##### Q.7 (12 points) Consider the numbers of the form $n^{13} − 2\cdot n^{7}+n$, wherenis aninteger. Determine for which values of $n$, the number $n^{13} − 2\cdot n^{7}+n$ is divisible by 98

$98 = 2 \cdot 7^{2}$ and $gcd(2,49) = 1$, we need to show $n^{13} − 2\cdot n^{7}+n$ can be divisible by 2 and 49.

$-2 \cdot n^{7}$ is alawys even. the other part $n^{13} + n =(n^{12}+1)n$, if n is even, then it is even, if n is odd, then the first part is even. so $n^{13} − 2\cdot n^{7}+n$ is divisible by 2.

then we need to prove $n^{13} − 2\cdot n^{7}+n$ can be divide by 49.

$$n^{13} − 2\cdot n^{7}+n = n(n^6 -1)^2$$

if $n \  mod \  7 = 0$, then $(n^6 -1)^2$ is not divisible by 7.

if $n \  mod \  7 \neq 0$, then $(n^6 -1)^2$ is divisible by 7 by Fermat's little theorem.

if $n \  mod \  49 = 0$, then the other part is no need.

So, all in all, $n \  mod \  49 = 0$ or $n \  mod \  7 \neq 0$

##### Q.8 (14 points) For a collection of balls, the number is not known

If we count them by 2’s, we have 1 left over;  
by 3, we have nothing left;  
by 4, we have 1 leftover;  
by 5, we have 4 left over;  
by 6, we have 3 left over;  
by 7, we have nothingleft;  
by 8, we have 1 left over;  
by 9, nothing is left.  
How many balls are there?Give the details of your calculation

We have

$$X \equiv 1 (mod \  2)$$
$$X \equiv 0 (mod \  3)$$
$$X \equiv 1 (mod \  4)$$
$$X \equiv 4 (mod \  5)$$
$$X \equiv 3 (mod \  6)$$
$$X \equiv 0 (mod \  7)$$
$$X \equiv 1 (mod \  8)$$
$$X \equiv 0 (mod \  9)$$

$X \equiv 3 (mod \  6)$, so $x = 6k+3$, it make $X \equiv 1 (mod \  2)$ and $X \equiv 0 (mod \  3)$, in other word, we now have

$$X \equiv 1 (mod \  2)$$
$$X \equiv 0 (mod \  3)$$
$$X \equiv 1 (mod \  4)$$
$$X \equiv 4 (mod \  5)$$
$$X \equiv 0 (mod \  7)$$
$$X \equiv 1 (mod \  8)$$
$$X \equiv 0 (mod \  9)$$

$X \equiv 0 (mod \  9)$ make $X \equiv 0 (mod \  3)$ always true, then 

$$X \equiv 1 (mod \  2)$$
$$X \equiv 1 (mod \  4)$$
$$X \equiv 4 (mod \  5)$$
$$X \equiv 0 (mod \  7)$$
$$X \equiv 1 (mod \  8)$$
$$X \equiv 0 (mod \  9)$$

$X \equiv 1 (mod \  8)$ make $X \equiv 1 (mod \  2)$ and $X \equiv 1 (mod \  4)$ always true, then

$$X \equiv 4 (mod \  5)$$
$$X \equiv 0 (mod \  7)$$
$$X \equiv 1 (mod \  8)$$
$$X \equiv 0 (mod \  9)$$

Then $5,7,8,9$ are pairwise relatively prime, we can use Chinese Remainder Theroem or back substitution to solve this system of congruences.

$$m = 5 \cdot 7 \cdot 8 \cdot 9 = 2520$$
$$m_1 = 7 \cdot 8 \cdot 9 = 504$$
$$m_2 = 5 \cdot 8 \cdot 9 = 360$$
$$m_3 = 5 \cdot 7  \cdot 9 = 315$$
$$m_4 = 5 \cdot 7 \cdot 8 = 280$$

By extended Euclidean algorithm, we have $y_1 = 4, y_2 = 5, y_3 = 3, y_4 = 1$.Then by Chinese Remainder Theorem, we have the solution is

$$x \equiv 4 \ast 405 \ast 4 + 1 \ast 315 \ast 3 + 0 \quad (mod \  2520) \equiv 1449 (mod \  2520)$$

##### Q.9 (10 points) Recall the RSA public key cryptosystem:

Bob posts a public key $(n,e)$ and keeps a secret key $d$, where $n$ is the product of two prime numbers. When Alice wants to send a message $0< M < n$ to Bob, she calculates $C=M^{e}$(mod $n$) and sends $C$ to Bob. Bob then decrypts this by calculating $C^{d}$(mod $n$). Given the value of $ \phi (n) = {7070}_8$ in *octal expansion* for $n= {7070}_8$ also in *octal expansion*. Can you factorize $n$, i.e., to find the values of $p$ and $q$? Explain your answer

Answer:

Yes,

$${7070}_8 = {3640}_{10}$$
$${7263}_8 = {3763}_{10}$$

Then By the equation $\phi(n) = (p-1)(q-1) = (n+1) - (p+q)$, we know that $pq = n = 3763$ and $p+q = (n+1) - \phi(n) = 124$. Thus, $p,q$ is two root of a equation

$$x^{2} - 124x + 3763 = 0$$

$$(x-53)(x-71) = 0$$
so $p,q = 53,71$

<style lang="css">
div{
 text-align: center;
}
div>div {
 text-align: center;
 border-bottom: 1px solid #d9d9d9;
 display: inline-block;
 padding: 2px;
}

div>img{
 border-radius: 0.3125em;
 box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);
}
</style>