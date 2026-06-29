---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Inverse Matrices, Column Space, and Null Space
series: Essence of Linear Algebra
video_url: https://youtu.be/uQhTuRlWMxA
---

# Inverse Matrices, Column Space, and Null Space

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 7)

---

## 1. Systems of Linear Equations as Space Transformations

A classic algebraic system of linear equations looks like this:

$$ A\vec{x} = \vec{v} $$

Where $A$ is a known matrix, $\vec{v}$ is a known target vector, and $\vec{x}$ is the unknown mystery vector we need to find.

- **The Geometric Re-framing:** Stop thinking about this as intersecting lines. Instead, read it as a question: **"What vector $\vec{x}$ can I choose so that after applying transformation $A$, it lands exactly on top of our target vector $\vec{v}$?"**

---

## 2. The Inverse Matrix ($A^{-1}$)

If the transformation $A$ does not collapse space (meaning $\det(A) \neq 0$), you can find your way backward by playing the transformation in reverse. This reverse operation is called the **inverse transformation**, represented by the matrix **$A^{-1}$**.

- **Undoing the Action:** If $A$ rotates space 90 degrees counterclockwise, $A^{-1}$ rotates space 90 degrees clockwise.
- **The Identity Core:** If you apply a transformation and then immediately apply its inverse, you end up doing nothing at all. This net "do nothing" matrix is called the **Identity Matrix ($I$)**:
  $$ A^{-1}A = I = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} $$

### Solving the System Algebraically

To find our unknown vector $\vec{x}$, we multiply both sides by the inverse matrix from the left:
$$ \vec{x} = A^{-1}\vec{v} $$

---

## 3. When the Determinant is Zero ($\det(A) = 0$)

If $\det(A) = 0$, space collapses. You **cannot** un-squish a line back into a full 2D plane, because a single point on that line would have to map to an infinite number of original points. You cannot divide by zero, and **an inverse matrix $A^{-1}$ does not exist**.

- **Can we still find solutions?** Yes, sometimes. If your target vector $\vec{v}$ happens to sit perfectly on the line that space was squished onto, solutions exist. If $\vec{v}$ is off that line, a solution is completely impossible.

---

## 4. Column Space and Rank

To deal with these dimensionality collapses rigorously, we use two key terms:

### Column Space

The set of all possible output vectors $\vec{v}$ that a transformation $A$ can reach is called the **column space** of the matrix.

- **Why columns?** Remember, the columns of a matrix tell you where the basis vectors land. The set of all possible linear combinations of those columns (their **span**) is exactly what defines all reachable outputs. Therefore, **Column Space is simply the span of the columns of the matrix.**

### Rank

The number of dimensions in your column space is called the **rank** of the matrix.

- If a 2D transformation keeps space full and expansive, its column space is 2D, so its rank is **$2$**.
- If a 2D transformation collapses space down onto a line, its column space is 1D, so its rank is **$1$**.

---

## 5. The Null Space (Kernel)

When a transformation squishes space into a lower dimension, a large batch of vectors is inevitably slammed directly into the origin $(0,0)$.

> [!important] Definition: Null Space
> The collection of all vectors in your domain that land exactly on the origin after the transformation is applied is called the **null space** or the **kernel** of the matrix.

$$ A\vec{x} = \begin{bmatrix} 0 \\ 0 \end{bmatrix} $$

If a matrix keeps space fully intact (rank is maximized, $\det \neq 0$), the _only_ vector that lands on the origin is the origin itself, meaning the null space is just the single vector $\begin{bmatrix} 0 \\ 0 \end{bmatrix}$. But if space collapses, the null space expands into an entire line or plane of valid answers.
