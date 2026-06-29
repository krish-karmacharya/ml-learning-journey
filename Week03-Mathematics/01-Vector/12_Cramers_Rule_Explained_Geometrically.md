---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Cramer's Rule Explained Geometrically
series: Essence of Linear Algebra
video_url: https://youtu.be/jBsC34PxzoM
---

# Cramer's Rule Explained Geometrically

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 12)

---

## 1. Why Cramer's Rule is Traditionally Disliked

When solving systems of linear equations like $A\vec{x} = \vec{v}$, students are occasionally taught **Cramer's Rule**. It is often presented as a tedious, algebraic recipe involving ratios of determinants that feels completely ungrounded and magical.

Looking at it through a geometric lens shows it is a highly intuitive consequence of area scaling factors.

---

## 2. Geometric Setup in the Un-Transformed Space

Consider a 2D linear system where we seek an unknown vector $\vec{x} = \begin{bmatrix} x \\ y \end{bmatrix}$ such that:
$$ A\vec{x} = \vec{v} $$

Before applying the transformation $A$, let's look at our standard basis vectors $\hat{i}$ and $\hat{j}$.

- The unknown vector $\vec{x}$ can be written as $x\hat{i} + y\hat{j}$.
- **The Area Trick:** Create a parallelogram using the unknown vector $\vec{x}$ and the basis vector $\hat{j}$.
  - The base of this parallelogram along the y-axis ($\hat{j}$) has a length of $1$.
  - The perpendicular height of this parallelogram is exactly equal to the $x$-coordinate of our unknown vector.
  - Therefore, **the area of this parallelogram is exactly equal to $x$.**

Similarly, the area of the parallelogram spanned by $\hat{i}$ and $\vec{x}$ is exactly equal to the $y$-coordinate.

---

## 3. Applying the Transformation $A$

Now, let's watch what happens when we apply the linear transformation $A$ to this entire setup:

- $\hat{i}$ transforms into the first column of the matrix, $\text{Col}_1(A)$.
- $\hat{j}$ transforms into the second column of the matrix, $\text{Col}_2(A)$.
- Our unknown vector $\vec{x}$ transforms into the known target vector $\vec{v}$.

### Tracking the Shifted Area

The parallelogram that originally had an area of $x$ (spanned by $\vec{x}$ and $\hat{j}$) has now been transformed into a new parallelogram spanned by **$\vec{v}$ and $\text{Col}_2(A)$**.

> [!important] The Determinant Link
> Recall from Chapter 6 that a linear transformation scales the areas of _all_ shapes uniformly by a factor equal to the **determinant** of the matrix ($\det(A)$).

$$ \text{Transformed Area} = \text{Original Area} \times \det(A) $$

Substituting our known geometric properties into this relation yields:
$$ \det(\begin{bmatrix} \vec{v} & \text{Col}\_2(A) \end{bmatrix}) = x \cdot \det(A) $$

---

## 4. Deriving Cramer's Rule

By isolating $x$, we arrive directly at Cramer's Rule:

$$ x = \frac{\det(\begin{bmatrix} \vec{v} & \text{Col}\_2(A) \end{bmatrix})}{\det(A)} $$

To solve for the coordinate $x$, you construct a matrix where the first column (the destination of $\hat{i}$) is replaced by your target vector $\vec{v}$, calculate its determinant, and divide it by the determinant of the original matrix $A$.

This formula is simply tracking how a spatial area scaling factor relates back to an unknown coordinate component.
