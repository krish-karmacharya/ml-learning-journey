---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Three-Dimensional Linear Transformations
series: Essence of Linear Algebra
video_url: https://youtu.be/rHLEWRxRGiM
---

# Three-Dimensional Linear Transformations

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 5)

---

## 1. Scaling the Intuition to 3D Space

Everything we established about 2D transformations carries over perfectly into three-dimensional space, with just one extra layer of depth.

- **Linearity in 3D:** A 3D transformation is linear if the 3D grid lines remain parallel and evenly spaced, and the origin $(0,0,0)$ remains completely fixed in place.
- **Visualizing 3D Movement:** Instead of warping a flat sheet of grid paper, a 3D linear transformation morphs an entire 3D volume of space—stretching, compressing, rotating, or shearing it.

---

## 2. The Three 3D Basis Vectors

In 3D space, we require **three** fundamental basis vectors to anchor our coordinate system:

- $\hat{i}$: The unit vector along the $x$-axis $\begin{bmatrix} 1 \\ 0 \\ 0 \end{bmatrix}$
- $\hat{j}$: The unit vector along the $y$-axis $\begin{bmatrix} 0 \\ 1 \\ 0 \end{bmatrix}$
- $\hat{k}$: The unit vector along the $z$-axis $\begin{bmatrix} 0 \\ 0 \\ 1 \end{bmatrix}$

To understand or compute any 3D linear transformation, you only need to keep track of where these three individual basis vectors land.

---

## 3. Reading a $3 \times 3$ Matrix

Because we are tracking three vectors, each landing at a destination described by three coordinates, a 3D linear transformation is packaged into a **$3 \times 3$ Matrix**:

$$ \begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix} \begin{bmatrix} x \\ y \\ z \end{bmatrix} $$

> [!tip] Direct Spatial Reading
> Slice the matrix vertically into three columns. Each column tells you exactly where one of the standard unit basis vectors landed:
>
> - **Column 1:** Transformed destination of $\hat{i}$
> - **Column 2:** Transformed destination of $\hat{j}$
> - **Column 3:** Transformed destination of $\hat{k}$

---

## 4. 3D Matrix-Vector Multiplication

To calculate where any general vector $\begin{bmatrix} x \\ y \\ z \end{bmatrix}$ lands after the transformation, you scale the transformed columns by $x$, $y$, and $z$, then add them together:

$$ \begin{bmatrix} a & b & c \\ d & e & f \\ g & h & i \end{bmatrix} \begin{bmatrix} x \\ y \\ z \end{bmatrix} = x \begin{bmatrix} a \\ d \\ g \end{bmatrix} + y \begin{bmatrix} b \\ e \\ h \end{bmatrix} + z \begin{bmatrix} c \\ f \\ i \end{bmatrix} $$

This is identical to the 2D rule: the output vector is simply a **linear combination of the transformed basis vectors**.
