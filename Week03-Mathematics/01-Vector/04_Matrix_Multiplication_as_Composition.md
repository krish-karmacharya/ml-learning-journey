---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Matrix Multiplication as Composition
series: Essence of Linear Algebra
video_url: https://youtu.be/XkY2DOUCWMU
---

# Matrix Multiplication as Composition

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 4)

---

## 1. Geometric Intuition of "Composition"

Often, we want to apply one linear transformation to space and then apply another one right after it. For example, you might want to rotate space 90 degrees counterclockwise, and then apply a shear transformation.

- **The Net Effect:** The sequential combination of these two separate operations results in a single, distinct linear transformation all on its own.
- **Composition:** This "effects-on-top-of-effects" process is called **composition**.
- **The Single Matrix Goal:** Instead of tracking two separate steps, we want to find a single $2 \times 2$ matrix that captures this overall combined transformation directly from start to finish.

---

## 2. Reading Matrix Multiplication: Right to Left

In mathematical notation, when you apply a rotation matrix $R$ and then a shear matrix $S$ to a vector $\vec{v}$, it is written like this:

$$ S R \vec{v} $$

> [!important] The Right-to-Left Rule
> You must always read matrix compositions from **right to left**. This directly mirrors function notation $f(g(x))$, where you evaluate the inner function $g(x)$ first, and then apply the outer function $f$ to that result.
>
> - Step 1: Apply the transformation on the right ($R$).
> - Step 2: Apply the transformation on the left ($S$).

---

## 3. Computing the Composition Matrix

To find the combined matrix for $SR$, we use our core rule from Chapter 3: **just track where the basis vectors $\hat{i}$ and $\hat{j}$ ultimately land after both steps are completed.**

### Step-by-Step Walkthrough

Suppose:

- Matrix $R$ (Rotation): $\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix}$
- Matrix $S$ (Shear): $\begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix}$

To compute $M = S \times R$:

1.  **Track $\hat{i}$:**
    - First, apply $R$: $\hat{i}$ lands at $\begin{bmatrix} 0 \\ 1 \end{bmatrix}$.
    - Next, apply $S$ to that intermediate result:
      $$ \begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix} \begin{bmatrix} 0 \\ 1 \end{bmatrix} = 0\begin{bmatrix} 1 \\ 0 \end{bmatrix} + 1\begin{bmatrix} 1 \\ 1 \end{bmatrix} = \begin{bmatrix} 1 \\ 1 \end{bmatrix} $$
    - This final destination becomes **Column 1** of our composition matrix.

2.  **Track $\hat{j}$:**
    - First, apply $R$: $\hat{j}$ lands at $\begin{bmatrix} -1 \\ 0 \end{bmatrix}$.
    - Next, apply $S$ to that intermediate result:
      $$ \begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix} \begin{bmatrix} -1 \\ 0 \end{bmatrix} = -1\begin{bmatrix} 1 \\ 0 \end{bmatrix} + 0\begin{bmatrix} 1 \\ 1 \end{bmatrix} = \begin{bmatrix} -1 \\ 0 \end{bmatrix} $$
    - This final destination becomes **Column 2** of our composition matrix.

The final composition matrix is:
$$ M = \begin{bmatrix} 1 & -1 \\ 1 & 0 \end{bmatrix} $$

---

## 4. The General Matrix Multiplication Formula

If you have two abstract matrices and multiply them, you are just performing this exact basis-tracking process algebraically:

$$ \begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} e & f \\ g & h \end{bmatrix} = \begin{bmatrix} a(e)+b(g) & a(f)+b(h) \\ c(e)+d(g) & c(f)+d(h) \end{bmatrix} $$

> [!tip] Visualizing the Algebra
> Don't memorize this formula mechanically. Notice that the first column of the result is simply the left matrix multiplied by the first column of the right matrix: $\begin{bmatrix} e \\ g \end{bmatrix}$. The second column is the left matrix multiplied by $\begin{bmatrix} f \\ h \end{bmatrix}$.

---

## 5. Non-Commutativity ($AB \neq BA$)

Does the order in which you apply transformations matter? **Yes, absolutely.**

- **Geometric proof:** Take a book. Rotate it 90 degrees, then flip it vertically. Now try it in reverse: flip it vertically first, then rotate it 90 degrees. The final orientation is completely different.
- Because spatial transformations care about order, **matrix multiplication is non-commutative**:
  $$ AB \neq BA $$

---

## 6. Associativity ($A(BC) = (AB)C$)

While order matters, grouping does not. If you have three transformations to apply sequentially ($C$, then $B$, then $A$):

$$ A(BC) = (AB)C $$

- **Why this is obvious geometrically:** Both sides of the equation mean exactly the same physical thing: "Apply transformation $C$, then $B$, then $A$ in that exact sequence." You are just choosing whether to pre-compute the combined effect of $BC$ first or $AB$ first.
