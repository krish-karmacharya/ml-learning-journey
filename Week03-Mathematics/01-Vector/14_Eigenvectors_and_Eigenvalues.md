---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Eigenvectors and Eigenvalues
series: Essence of Linear Algebra
video_url: https://youtu.be/PFDu9oVAE-g
---

# Eigenvectors and Eigenvalues

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 14)

---

## 1. Visualizing the Special Vectors

When a linear transformation morphs space, most vectors get knocked off their original span. Their directional orientation changes, meaning they rotate in space.

However, some special vectors remain anchored to their original span during a transformation. The line passing through them does not rotate; they are merely **scaled—stretched, compressed, or flipped in reverse**.

> [!important] Core Definition
>
> - **Eigenvector:** Any non-zero vector that does not change its directional axis (span) during a linear transformation.
> - **Eigenvalue ($\lambda$):** The scaling factor by which an eigenvector is stretched, compressed, or reversed during that transformation.

---

## 2. Visual Examples

- **3D Rotation:** Think about rotating a globe in 3D space. Every single point moves, except for the points sitting directly along the axis of rotation. The vectors pointing along that rotation axis are eigenvectors, and their eigenvalue is exactly **$1$**, because their length remains completely unaltered.
- **A Shear Transformation:** In a horizontal shear, the x-axis remains completely locked in place. Every vector pointing along the x-axis is an eigenvector with an eigenvalue of **$1$**. Vectors off the x-axis get tilted diagonally, so they are not eigenvectors.

---

## 3. The Algebraic Formulation

To find these special vectors mathematically, we set up an equation stating that transforming a vector $\vec{v}$ by matrix $A$ must yield the exact same result as scaling $\vec{v}$ by a number $\lambda$:

$$ A\vec{v} = \lambda\vec{v} $$

To solve this using matrix algebra, we rewrite the right side using the identity matrix $I$ so we can group our terms:
$$ A\vec{v} = (\lambda I)\vec{v} $$
$$ (A - \lambda I)\vec{v} = \mathbf{0} $$

---

## 4. Solving for the Eigenvalues

For a non-zero eigenvector $\vec{v}$ to satisfy the equation $(A - \lambda I)\vec{v} = \mathbf{0}$, the new transformed matrix $(A - \lambda I)$ **must collapse space into a lower dimension**. If it didn't collapse space, the only vector that could land on the origin would be the zero vector itself.

As established in Chapter 6, a transformation collapses space if and only if its determinant is exactly zero:

$$ \det(A - \lambda I) = 0 $$

### The Calculation Workflow

1.  Subtract $\lambda$ from the main diagonal entries of your matrix $A$.
2.  Compute the determinant of this altered matrix, which yields a polynomial expression in terms of $\lambda$ (the **characteristic polynomial**).
3.  Solve for the roots where this polynomial equals $0$. These roots are your valid **eigenvalues**.
4.  Plug those eigenvalues back into $(A - \lambda I)\vec{v} = \mathbf{0}$ to solve for the individual **eigenvector** coordinates.

---

## 5. Diagonal Matrices & Eigendecomposition

If a matrix has its non-zero entries located exclusively along its main diagonal, it is called a **diagonal matrix**:

$$ \begin{bmatrix} 3 & 0 \\ 0 & 2 \end{bmatrix} $$

- **The Geometric Setup:** This matrix simply scales the x-axis by $3$ and the y-axis by $2$.
- **The Basis Advantage:** This means our standard basis vectors ($\hat{i}$ and $\hat{j}$) are _already_ the eigenvectors of the transformation.

### Diagonalization Shortcut

If a transformation has enough eigenvectors to form a full basis for the space, you can use those eigenvectors as a new coordinate system (a **change of basis**). Written in this eigenvector basis, your transformation matrix $A$ simplifies into a perfect diagonal matrix $D$:

$$ D = P^{-1} A P $$

This structural simplification makes computing massive matrix powers ($A^{100}$) simple, because raising a diagonal matrix to a power only requires raising its diagonal entries to that power.
