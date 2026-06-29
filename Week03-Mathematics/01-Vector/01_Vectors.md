---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Vectors, What Even Are They?
series: Essence of Linear Algebra
video_url: https://youtu.be/fNk_zzaMoSs
---

# Vectors, What Even Are They?

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 1)

---

## 1. Introduction: Three Perspectives on Vectors

The fundamental building block of linear algebra is the vector. Broadly speaking, there are three distinct-but-related interpretations of vectors depending on your background:

- **The Physics Student Perspective:** Vectors are **arrows pointing in space**. A vector is defined entirely by its **length** (magnitude) and the **direction** it is pointing. As long as these two traits remain identical, you can slide the vector around anywhere in space, and it remains the exact same vector.
- **The Computer Science Perspective:** Vectors are **ordered lists of numbers**. For example, if you are analyzing housing data and care only about square footage and price, you might model a house as a 2D vector: `[2100, 350000]`. In this viewpoint, a vector is simply a fancy word for a list, and its "dimensionality" is just the length of that list.
- **The Mathematician's Perspective:** This view generalizes both of the others. A mathematician views a vector as **anything where there is a sensible notion of adding two vectors and multiplying a vector by a number**. The details are abstract (governed by vector space axioms), allowing vectors to be things like functions or matrices, though it's best to stick to concrete geometric grids when first building intuition.

---

## 2. Vector Coordinates & The Linear Algebra Setting

Linear algebra almost always grounds itself in a coordinate system where the tail of every single vector is rooted at a single central point: **the origin** $(0,0)$.

- **Coordinates as Instructions:** The coordinates of a vector are a pair (or triplet) of numbers that serve as a precise set of instructions for walking from its tail at the origin to its tip.
  - **First number ($x$):** How far to walk along the x-axis (positive = right, negative = left).
  - **Second number ($y$):** How far to walk parallel to the y-axis (positive = up, negative = down).

> [!tip] Notation Convention
> To clearly distinguish vectors from single geometric points, linear algebra uses the convention of writing coordinates vertically as a column wrapped in square brackets:
> $$ \vec{v} = \begin{bmatrix} x \\ y \end{bmatrix} $$

### Expanding to Higher Dimensions

- **3D Space:** Adds a third perpendicular axis ($z$-axis). Vectors are represented as ordered triplets:
  $$ \vec{v} = \begin{bmatrix} x \\ y \\ z \end{bmatrix} $$
- **Higher Dimensions ($n$-D):** While difficult to visualize as arrows, the computer science perspective seamlessly scales to 4D, 5D, or 100D spaces simply by extending the length of the ordered numeric list.

---

## 3. Vector Addition

How do we define operations on vectors, and why do they make sense across both geometric and numeric perspectives?

### Geometric View: The Tip-to-Tail Method

To add two vectors $\vec{v}$ and $\vec{w}$:

1. Draw the first vector $\vec{v}$ starting at the origin.
2. Take the second vector $\vec{w}$ and move it so that its **tail** sits directly on top of the **tip** of $\vec{v}$.
3. Draw a new vector from the origin (the tail of $\vec{v}$) straight to the final destination (the tip of $\vec{w}$). This new arrow is the sum $\vec{v} + \vec{w}$.

> [!important] The Intuition of Movement
> Why do we add vectors this way? Think of every vector as representing a **movement or a step** in space. If you take a step along $\vec{v}$, and then immediately take a step along $\vec{w}$, the net effect of your displacement is exactly equal to traveling along the single vector $\vec{v} + \vec{w}$.

### Numeric View: Component-wise Addition

Numerically, adding vectors is incredibly straightforward. You simply line up the matching components and add them together:
$$ \begin{bmatrix} x_1 \\ y_1 \end{bmatrix} + \begin{bmatrix} x_2 \\ y_2 \end{bmatrix} = \begin{bmatrix} x_1 + x_2 \\ y_1 + y_2 \end{bmatrix} $$

This mirrors the geometric "tip-to-tail" movement: walking $x_1$ steps right then $x_2$ steps right is the same as walking $x_1 + x_2$ steps right overall.

---

## 4. Scalar Multiplication

The second foundational operation is multiplying a vector by a regular number (such as $2$, $0.5$, or $-1$).

### Geometric View: Stretching, Squishing, and Reversing

- **Stretching:** Multiplying a vector by $2$ stretches its length out to be twice as long, keeping its original direction unchanged.
- **Squishing:** Multiplying a vector by $1/3$ compresses its length to a third of its original size.
- **Reversing:** Multiplying by a negative number (like $-1.8$) flips the vector around so that it points in the exact opposite direction along the same line, while also altering its length.

> [!important] Why call them "Scalars"?
> This process of stretching or squishing a vector's length is called **scaling**. Because numbers act as scaling tools in this context, the term **"scalars"** is used almost interchangeably with "numbers" throughout linear algebra.

### Numeric View: Component-wise Scaling

Numerically, to multiply a vector by a scalar, you distribute that scalar by multiplying it into every individual component of the vector:
$$ 2 \cdot \begin{bmatrix} 3 \\ 1 \end{bmatrix} = \begin{bmatrix} 2 \cdot 3 \\ 2 \cdot 1 \end{bmatrix} = \begin{bmatrix} 6 \\ 2 \end{bmatrix} $$

---

## 5. Core Takeaways & The Symmetry

The beauty of linear algebra lies in the ongoing interplay between its geometric and numeric manifestations:

1.  **Symmetry of Perspectives:** It ultimately does not matter whether you prefer to think of vectors as physical arrows in space or as lists of numbers. The math maps back and forth perfectly.
2.  **Visualizing Data:** The geometric view gives data analysts and computer scientists a powerful visual framework to conceptualize long lists of numbers. Viewing a dataset as points or arrows in an abstract space clarifies underlying patterns and makes complex data transformations intuitive.
3.  **Foundation for the Future:** Understanding how vectors combine via addition and scalar multiplication lays the exact groundwork for defining concepts like _linear combinations_, _span_, _basis vectors_, and eventually _linear transformations_.
