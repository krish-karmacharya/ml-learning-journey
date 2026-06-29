---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Dot Products and Duality
series: Essence of Linear Algebra
video_url: https://youtu.be/LyGKycYT2v0
---

# Dot Products and Duality

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 9)

---

## 1. The Standard Geometric View

The standard textbook definition of a dot product between two vectors $\vec{v}$ and $\vec{w}$ involves projection:

1.  Project vector $\vec{w}$ orthogonally onto the line spanned by vector $\vec{v}$.
2.  Measure the length of that projected segment.
3.  Multiply the length of the projection by the total length of $\vec{v}$.

- **Direction Dynamics:** If the projection points in the opposite direction of $\vec{v}$, the dot product is **negative**. If they are perpendicular, the projection length is zero, so the dot product is **zero**.
- **The Mystery of Symmetry:** Why does this operation exhibit perfect symmetry? Projecting $\vec{w}$ onto $\vec{v}$ yields the exact same numeric result as projecting $\vec{v}$ onto $\vec{w}$, even if their lengths are wildy different.

---

## 2. The Numerical View

Numerically, computing a dot product is incredibly straightforward. You multiply matching components together and sum the results:

$$ \begin{bmatrix} v_x \\ v_y \end{bmatrix} \cdot \begin{bmatrix} w_x \\ w_y \end{bmatrix} = v_x w_x + v_y w_y $$

The real question is: **Why does this algebraic component-matching process map perfectly to the physical action of spatial projection?**

---

## 3. The Structural Bridge: Duality

To explain this symmetry, we must look at a $1 \times 2$ matrix. A transformation that maps 2D space down onto a 1D number line is completely defined by where $\hat{i}$ and $\hat{j}$ land on that number line.

If $\hat{i}$ lands at number $a$ and $\hat{j}$ lands at number $b$, the transformation matrix is:
$$ L = \begin{bmatrix} a & b \end{bmatrix} $$

Multiplying an arbitrary vector by this matrix yields:
$$ \begin{bmatrix} a & b \end{bmatrix} \begin{bmatrix} x \\ y \end{bmatrix} = ax + by $$

> [!important] The Overlap
> Notice that the algebra for this 1D linear transformation ($ax + by$) looks identical to the algebra for a standard numeric dot product.

---

## 4. The Geometry of the 1D Transformation

Imagine a 2D plane with a single unit vector $\hat{u}$ rooted at the origin. Let's create a transformation that takes any 2D vector and projects it directly onto the line containing $\hat{u}$.

- Is this projection a **linear transformation**? Yes, because grid lines remain straight, parallel, and evenly spaced on the number line.
- To find its $1 \times 2$ matrix, we must find where the standard basis vectors $\hat{i}$ and $\hat{j}$ land when projected onto $\hat{u}$'s line.
- By exploiting symmetry, the number where $\hat{i}$ lands when projected onto $\hat{u}$'s line is exactly equal to the $x$-coordinate of $\hat{u}$ itself!
- Similarly, the number where $\hat{j}$ lands when projected onto $\hat{u}$'s line is exactly equal to the $y$-coordinate of $\hat{u}$.

> [!tip] The Core Revelation of Duality
> The $1 \times 2$ matrix that performs the geometric projection of vectors onto a unit vector $\hat{u}$ consists simply of the coordinates of $\hat{u}$ written horizontally:
> $$ \begin{bmatrix} u_x & u_y \end{bmatrix} $$

---

## 5. Summary of Duality

This deep natural correspondence is called **mathematical duality**.

- Every linear transformation that maps a multi-dimensional space to a 1D number line corresponds to a unique vector in that space.
- **Multiplying by that transformation matrix is physically identical to taking a dot product with that corresponding vector.**
- The dot product is not just an arithmetic trick; it is the physical manifestation of a multi-dimensional-to-1D spatial projection.
