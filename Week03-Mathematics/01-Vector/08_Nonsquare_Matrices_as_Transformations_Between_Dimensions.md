---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Nonsquare Matrices as Transformations Between Dimensions
series: Essence of Linear Algebra
video_url: https://youtu.be/v8VSDg_WQlA
---

# Nonsquare Matrices as Transformations Between Dimensions

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 8)

---

## 1. Transforming Across Dimensions

Up to this point, we have focused exclusively on transformations that map 2D space to 2D space, or 3D space to 3D space. However, it is entirely possible to have a linear transformation that takes an input vector from one dimension and maps it to an output vector in a completely different dimension.

- **Geometric Meaning:** A transformation from 2D to 3D space takes a flat 2D plane and maps it into a 3D environment.
- **The Structural Baseline:** Linearity still holds strictly true: grid lines must remain straight and evenly spaced, and the origin must remain anchored at $(0,0,0)$.

---

## 2. Reading a $3 \times 2$ Matrix (2D to 3D)

Consider a matrix with 3 rows and 2 columns:

$$ \begin{bmatrix} a & b \\ c & d \\ e & f \end{bmatrix} $$

> [!tip] Understanding the Matrix Shape
>
> - **Number of columns (2):** Represents the size of the input space. Since there are 2 columns, we are tracking exactly **two** input basis vectors ($\hat{i}$ and $\hat{j}$).
> - **Number of rows (3):** Represents the size of the output space. Each basis vector is given a destination described by **three** coordinate values.

### Columns as Spatial Mapping

- **Column 1 ($\begin{bmatrix} a \\ c \\ e \end{bmatrix}$):** The precise 3D destination where the 2D basis vector $\hat{i}$ lands.
- **Column 2 ($\begin{bmatrix} b \\ d \\ f \end{bmatrix}$):** The precise 3D destination where the 2D basis vector $\hat{j}$ lands.

The **column space** of this matrix is a flat 2D plane slicing through the 3D origin. Because the transformation outputs 3D vectors but only has a maximum rank of 2, it maps all 2D inputs onto this 2D slice embedded inside 3D space.

---

## 3. Reading a $2 \times 3$ Matrix (3D to 2D)

Conversely, consider a matrix with 2 rows and 3 columns:

$$ \begin{bmatrix} a & b & c \\ d & e & f \end{bmatrix} $$

- **Input Space (3 columns):** We track three starting basis vectors: $\hat{i}$, $\hat{j}$, and $\hat{k}$.
- **Output Space (2 rows):** Each column lists a 2D coordinate vector.
- **Geometric Impact:** This transformation squishes an entire 3D volume down into a flat 2D plane.

---

## 4. $1 \times 2$ Matrices (2D to 1D)

A matrix with 1 row and 2 columns looks like this:

$$ \begin{bmatrix} a & b \end{bmatrix} $$

- It tracks 2 input basis vectors ($\hat{i}$ and $\hat{j}$).
- It maps them both directly onto a **1D number line**.
- Multiplying a vector by this matrix outputs a single scalar value. This serves as the direct mathematical bridge to understanding the dot product.
