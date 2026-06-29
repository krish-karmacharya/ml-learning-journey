---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Abstract Vector Spaces
series: Essence of Linear Algebra
video_url: https://youtu.be/TgKwz5Ikpc8
---

# Abstract Vector Spaces

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 16)

---

## 1. Moving Beyond Geometric Arrows

Throughout this series, we have relied on geometric arrows resting on a grid to build our intuition. However, the true power of linear algebra lies in its ability to generalize to abstract structures that look nothing like arrows or coordinate grids.

To a mathematician, it doesn't matter what a vector _is_ structurally. It only matters that it satisfies a specific set of rules for combining elements.

---

## 2. Functions as Vectors

Consider mathematical functions (e.g., $f(x) = x^2 + 3x$). Can we treat a function as a vector? Let's check if the two foundational linear algebra operations apply cleanly:

- **Function Addition:** You can add two functions together to create a brand new function:
  $$ (f + g)(x) = f(x) + g(x) $$
- **Scalar Multiplication:** You can multiply a function by a regular scaling number:
  $$ (c \cdot f)(x) = c \cdot f(x) $$

Because these operations are well-defined and behave predictably, **functions are valid vectors.**

---

## 3. The Gridless Interpretation of Linear Concepts

Since functions satisfy the basic rules of vectors, we can apply our entire linear algebra toolkit to them:

- **Linear Combinations:** You can scale and add functions together, such as creating polynomials ($a \cdot x^2 + b \cdot x + c$).
- **Basis Functions:** Can we find a basis for a function space? Yes. For example, the infinite set of power functions $\{1, x, x^2, x^3, \dots\}$ acts as a basis for the space of all polynomials. Every individual polynomial is a unique linear combination of these basis elements.
- **Linear Transformations:** A transformation takes an input function and maps it to an output function. For an operation to be strictly linear, it must satisfy our algebraic criteria: $T(\vec{v}+\vec{w}) = T(\vec{v}) + T(\vec{w})$ and $T(c\vec{v}) = cT(\vec{v})$.

> [!tip] Calculus Connection
> The **derivative operator** ($\frac{d}{dx}$) is a linear transformation! It takes an input function and outputs its derivative, and it obeys the core rules of linearity:
> $$ \frac{d}{dx}(f(x) + g(x)) = \frac{d}{dx}f(x) + \frac{d}{dx}g(x) $$
> $$ \frac{d}{dx}(c \cdot f(x)) = c \cdot \frac{d}{dx}f(x) $$

---

## 4. The Formal Axioms of a Vector Space

To ensure that any abstract object can safely use the linear algebra toolkit without breaking, mathematicians established 8 formal rules (**axioms**). Any collection of elements that satisfies these rules under specified addition and scalar multiplication operations is a formal **Vector Space**:

1.  **Associativity of Addition:** $\vec{u} + (\vec{v} + \vec{w}) = (\vec{u} + \vec{v}) + \vec{w}$
2.  **Commutativity of Addition:** $\vec{u} + \vec{v} = \vec{v} + \vec{u}$
3.  **Identity Element of Addition:** There exists a zero vector $\mathbf{0}$ such that $\vec{v} + \mathbf{0} = \vec{v}$
4.  **Inverse Elements of Addition:** For every $\vec{v}$, there exists a $-\vec{v}$ such that $\vec{v} + (-\vec{v}) = \mathbf{0}$
5.  **Compatibility of Scalar Multiplication:** $a(b\vec{v}) = (ab)\vec{v}$
6.  **Identity Element of Scalar Multiplication:** $1 \cdot \vec{v} = \vec{v}$
7.  **Distributive Law for Scalar Addition:** $(a + b)\vec{v} = a\vec{v} + b\vec{v}$
8.  **Distributive Law for Vector Addition:** $a(\vec{u} + \vec{v}) = a\vec{u} + a\vec{v}$

---

## 5. Conclusion: The Power of Abstraction

By stripping away physical arrows and coordinate grids and focusing purely on these underlying axioms, linear algebra becomes a universal language.

The exact same principles used to rotate a 3D graphic in a video game are used by quantum physicists to model subatomic states, by data scientists to analyze high-dimensional arrays, and by calculus professors to solve differential equations. It is the study of structured, linear relationships across any mathematical space.
