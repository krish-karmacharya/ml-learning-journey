---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Cross Products
series: Essence of Linear Algebra
video_url: https://youtu.be/eu6iDH-w_Wr
---

# Cross Products

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 10)

---

## 1. The Geometric Definition in 2D Space

Strictly speaking, the true cross product maps two 3D vectors to a third 3D vector. However, a common prelude is the "2D cross product," which takes in two vectors $\vec{v}$ and $\vec{w}$ and returns a single scalar number.

- **Area Tracking:** Geometrically, this value measures the **area of the parallelogram** spanned by $\vec{v}$ and $\vec{w}$.
- **Determinant Parity:** This is exactly equal to the determinant of a $2 \times 2$ matrix built with those vectors as columns:

$$ \text{Area} = \det\left(\begin{bmatrix} v_x & w_x \\ v_y & w_y \end{bmatrix}\right) = v_x w_y - v_y w_x $$

- **Sign Dynamics:**
  - **Positive:** If $\vec{v}$ is counterclockwise from $\vec{w}$.
  - **Negative:** If $\vec{v}$ is clockwise from $\vec{w}$.

---

## 2. The Geometric Definition in 3D Space

In true 3D space, the cross product combines two vectors $\vec{v}$ and $\vec{w}$ to create a brand new **3D vector**, written as $\vec{v} \times \vec{w}$.

Instead of computing a single area number, we construct an arrow with these geometric properties:

1.  **Length:** The length of the output vector equals the area of the parallelogram spanned by $\vec{v}$ and $\vec{w}$ in 3D space.
2.  **Direction:** The output vector points in a direction that is **perpendicular (orthogonal)** to both $\vec{v}$ and $\vec{w}$.
3.  **Orientation:** To determine which of the two perpendicular directions it points, use the **Right-Hand Rule**: index finger along $\vec{v}$, middle finger along $\vec{w}$, and your thumb points toward the cross product.

---

## 3. The Standard Computational Formula

The standard mnemonic taught in physics and engineering classes involves evaluating a symbolic determinant using the basis vectors $\hat{i}, \hat{j}, \hat{k}$ placed along the top row:

$$ \vec{v} \times \vec{w} = \det\left(\begin{bmatrix} \hat{i} & \hat{j} & \hat{k} \\ v_x & v_y & v_z \\ w_x & w_y & w_z \end{bmatrix}\right) $$

Expanding this determinant gives the standard component formula:
$$ \hat{i}(v_y w_z - v_z w_y) - \hat{j}(v_x w_z - v_z w_x) + \hat{k}(v_x w_y - v_y w_x) $$

> [!warning] The Conceptual Question
> Why does putting basis vectors inside a determinant generate a vector that is perfectly perpendicular to the other two, with a length representing spatial area? The answers are traditionally glossed over, requiring duality to be fully unmasked.
