---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Linear Transformations and Matrices
series: Essence of Linear Algebra
video_url: https://youtu.be/k7RM-ot269g
---

# Linear Transformations and Matrices

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 3)

---

## 1. What is a "Transformation"?

The word **transformation** is essentially a geometric synonym for a **function**. Like any mathematical function, it takes in an input and spits out an output.

- **The Vector Perspective:** In linear algebra, a transformation takes in an input vector, processes it, and outputs a new vector.
- **Visualizing the Shift:** Instead of graphing inputs on an $x$-axis and outputs on a $y$-axis, we visualize transformations by watching vectors _move_. We track how an entire coordinate plane morphs, bends, or stretches as input vectors are mapped to their output destinations.

---

## 2. The Strict Rules of "Linearity"

Not all transformations are linear. A transformation is strictly **linear** if it satisfies two visual properties:

1.  **The origin remains fixed:** The point $(0,0)$ must never move.
2.  **Lines remain straight:** All lines must remain completely straight lines; they cannot bend, curve, or warp.

> [!important] The Core Metric
> A transformation is linear if **grid lines remain parallel and evenly spaced** across the entire coordinate system throughout the entire morphing process.

---

## 3. The Power of Basis Vectors

Because a linear transformation keeps grid lines parallel and evenly spaced, you don't need to track an infinite number of vectors to know where everything lands. You only need to track two: **the basis vectors $\hat{i}$ and $\hat{j}$**.

- Every vector on the plane is a linear combination of those basis vectors: $\vec{v} = x\hat{i} + y\hat{j}$.
- If you know where $\hat{i}$ lands and where $\hat{j}$ lands after the transformation, your original vector $\vec{v}$ will land at that exact same combination ($x$ and $y$) of their new destinations.

$$ \text{Transformed }\vec{v} = x(\text{Transformed }\hat{i}) + y(\text{Transformed }\hat{j}) $$

---

## 4. Packaging Transformations into Matrices

A matrix is not just a random box of numbers. Geometrically, **a matrix is a condensed description of a spatial transformation.**

For a standard $2 \times 2$ matrix:
$$ \begin{bmatrix} a & b \\ c & d \end{bmatrix} $$

> [!tip] How to Read a Matrix Instantly
> Split the matrix vertically into its individual columns:
>
> - **Column 1 ($\begin{bmatrix} a \\ c \end{bmatrix}$):** The exact coordinate destination where **$\hat{i}$** lands.
> - **Column 2 ($\begin{bmatrix} b \\ d \end{bmatrix}$):** The exact coordinate destination where **$\hat{j}$** lands.

### Concrete Example: 90° Counterclockwise Rotation

If you rotate all of space 90 degrees counterclockwise:

- $\hat{i}$ (originally $\begin{bmatrix} 1 \\ 0 \end{bmatrix}$) rotates up onto the y-axis to land at $\begin{bmatrix} 0 \\ 1 \end{bmatrix}$.
- $\hat{j}$ (originally $\begin{bmatrix} 0 \\ 1 \end{bmatrix}$) rotates left onto the negative x-axis to land at $\begin{bmatrix} -1 \\ 0 \end{bmatrix}$.

The matrix capturing a 90° rotation is simply those two landing coordinates stacked together:
$$ \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} $$

---

## 5. Matrix-Vector Multiplication Geometrically

When you multiply a matrix by a vector, you are asking: _"Where does this vector land after the transformation?"_

$$ \begin{bmatrix} a & b \\ c & d \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = x \begin{bmatrix} a \\ c \end{bmatrix} + y \begin{bmatrix} b \\ d \end{bmatrix} = \begin{bmatrix} ax + by \\ cx + dy \end{bmatrix} $$

Instead of memorizing row-by-column dot products mechanics, view it for what it truly is: **scaling the transformed columns of your basis vectors by your input coordinates $x$ and $y$, and adding them together.**
