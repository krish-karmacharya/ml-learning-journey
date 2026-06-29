---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Linear Combinations, Span, and Basis Vectors
series: Essence of Linear Algebra
video_url: https://youtu.be/k7RM-ot2NWY
---

# Linear Combinations, Span, and Basis Vectors

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 2)

---

## 1. The Setup: Basis Vectors [00:00:00]

Whenever we write numeric coordinates like $\begin{bmatrix} 3 \\ -2 \\ \end{bmatrix}$, those numbers have a hidden geometric dependency. They rely on a standard set of implicit anchors known as **basis vectors**.

- **The Unit Anchors:** In the standard $xy$-coordinate plane, we have two fundamental vectors:
  - $\hat{i}$ (pronounced "i-hat"): A vector of length $1$ pointing straight to the right along the $x$-axis.
  - $\hat{j}$ (pronounced "j-hat"): A vector of length $1$ pointing straight up along the $y$-axis.
- **Coordinates as Scaling Factors:** When you look at a vector like $\begin{bmatrix} 3 \\ -2 \\ \end{bmatrix}$, you should interpret it as an explicit instruction to scale these unit anchors:
  $$ \vec{v} = 3\hat{i} - 2\hat{j} $$
- **Choosing Different Bases:** Choosing $\hat{i}$ and $\hat{j}$ is a completely arbitrary human convention. If you choose a different pair of starting vectors, you can create a completely valid, alternative coordinate system to describe the exact same points in space.

---

## 2. Linear Combinations [00:02:10]

What happens when we perform vector addition and scalar multiplication simultaneously using a set of vectors?

If we have two vectors $\vec{v}$ and $\vec{w}$, and we scale each of them by some scalars $a$ and $b$ before adding them together, the resulting vector is called a **linear combination** of those two vectors:
$$ a\vec{v} + b\vec{w} $$

### The Visual Shift

- **Fixing one scalar, altering the other:** If you let $a$ be a fixed constant (e.g., $a = 1$) and let $b$ freely vary across all real numbers, the tip of the resulting vector draws a perfect, infinite straight line in space.
- **Altering both scalars:** If you allow both $a$ and $b$ to loop through every possible real number value, you will map out all the possible spatial destinations accessible by those two vectors.

> [!important] Why "Linear"?
> The word **"linear"** comes from this exact visual behavior: if you hold all but one scalar constant and let that remaining scalar vary, the resulting tips of the vectors trace a straight line.

---

## 3. The Concept of "Span" [00:03:52]

The **span** of a set of vectors is simply the collection of all possible vectors you can reach using their linear combinations.

$$\text{Span}(\vec{v}, \vec{w}) = \{ a\vec{v} + b\vec{w} \mid a, b \in \mathbb{R} \}$$

Geometrically, the span of two vectors in 2D space usually falls into one of three distinct categories:

1.  **The Plane:** For the vast majority of pairs of 2D vectors, their span forms the **entire infinite 2D plane**. You can reach absolutely any point in space.
2.  **A Single Line:** If the two original vectors happen to line up perfectly in the exact same direction (or opposite directions), they are trapped. Their span collapses into a **single straight line** passing through the origin.
3.  **The Origin (A Point):** If both vectors are the zero vector $\begin{bmatrix} 0 \\ 0 \\ \end{bmatrix}$, you can scale them all you want, but you will always remain stuck at the **origin** $(0,0)$.

### Scaling Up to 3D Space

- **Two 3D Vectors:** If you take two vectors pointing in different directions in 3D space, their span is a flat, infinite **2D sheet (a plane)** slicing through the 3D origin.
- **Adding a Third Vector:** If you introduce a third vector $\vec{u}$ into your set, the net span depends entirely on where that third vector points.

---

## 4. Linear Dependence vs. Linear Independence [00:06:12]

When scaling up or evaluating vector sets, we must ask: _Does every vector actually add a brand new path or dimension to our span?_

### Case A: Linear Dependence (Redundancy)

If you are in 3D space with two vectors already spanning a flat plane, and you choose a third vector that happens to sit **directly on that flat plane**, that third vector is completely redundant. It does not unlock access to any new coordinates in 3D space.

> [!important] Definition: Linearly Dependent
> When a vector can be written as a linear combination of the other vectors in the set, it is **linearly dependent**. In other words, it is already sitting comfortably inside the span of the other vectors:
> $$ \vec{u} = a\vec{v} + b\vec{w} $$

### Case B: Linear Independence (New Dimensions)

If your third vector points completely away from the plane spanned by the first two, it unlocks a completely new directional capability. It allows you to move off the plane, giving you full access to **every single possible vector in 3D space**.

> [!important] Definition: Linearly Independent
> If each vector in a set genuinely adds a brand new dimension to the resulting span rather than overlapping with previous ones, the vectors are **linearly independent**. No vector in the set can be built from a linear combination of the remaining vectors.

---

## 5. The Technical Definition of a "Basis" [00:08:42]

With the concepts of span and independence firmly established, we can arrive at one of the most foundational definitions in all of linear algebra:

> [!tip] Technical Definition of a Basis
> The **basis** of a vector space is a set of **linearly independent** vectors that **span** the entire space.

- **The Standard Basis:** Our usual grid anchors, $\hat{i}$ and $\hat{j}$, form the standard basis for $\mathbb{R}^2$ because they are completely independent (perpendicular) and can build any 2D vector.
- **Minimalist Framework:** A basis is the perfect goldilocks set: it contains enough vectors to reach everywhere in the space (spans the space), but contains absolutely zero redundant vectors (linearly independent).
