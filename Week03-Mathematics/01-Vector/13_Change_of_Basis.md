---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Change of Basis
series: Essence of Linear Algebra
video_url: https://youtu.be/P2LTAUO1TdA
---

# Change of Basis

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 13)

---

## 1. Two Grid Languages

When you describe a vector numerically using coordinates like $\begin{bmatrix} 3 \\ 2 \end{bmatrix}$, you are speaking a language tied directly to your chosen **basis vectors** ($\hat{i}$ and $\hat{j}$).

Imagine an alternative observer, Jennifer. She lives in the same space, but she uses a completely different pair of basis vectors, $\vec{b}_1$ and $\vec{b}_2$.

- To Jennifer, her basis vectors are anchored as her local unit vectors $\begin{bmatrix} 1 \\ 0 \end{bmatrix}$ and $\begin{bmatrix} 0 \\ 1 \end{bmatrix}$.
- To us, her basis vectors look skewed or rotated, having coordinates like $\begin{bmatrix} 2 \\ 1 \end{bmatrix}$ and $\begin{bmatrix} -1 \\ 1 \end{bmatrix}$.

Because your starting anchors differ, **the exact same physical vector in space will be assigned completely different numbers by each observer.**

---

## 2. Translating Jennifer's Language to Our Language

If Jennifer describes a vector as $\vec{x}_{\text{Jennifer}} = \begin{bmatrix} -1 \\ 2 \end{bmatrix}$, she means:
$$ \vec{x} = -1\vec{b}\_1 + 2\vec{b}\_2 $$

To translate this vector into our coordinate language, we can use a **Change of Basis Matrix**. We build a matrix where the columns are Jennifer's basis vectors written in _our_ language:

$$ P = \begin{bmatrix} \vec{b}\_1 & \vec{b}\_2 \end{bmatrix} = \begin{bmatrix} 2 & -1 \\ 1 & 1 \end{bmatrix} $$

Multiplying her coordinate vector by this translation matrix computes the linear combination in our coordinates:
$$ \vec{x}_{\text{Our}} = P \vec{x}_{\text{Jennifer}} $$

---

## 3. Translating Our Language to Jennifer's Language

What if we want to go the opposite way? If we have a vector written in our standard coordinates ($\vec{x}_{\text{Our}}$) and want to translate it into Jennifer's world, we simply play the conversion matrix in reverse.

We calculate the matrix inverse, $P^{-1}$:
$$ \vec{x}_{\text{Jennifer}} = P^{-1} \vec{x}_{\text{Our}} $$

---

## 4. Translating a Transformation Matrix ($P^{-1}AP$)

This translation process becomes essential when modeling operations. Suppose we have a transformation, like a 90-degree rotation, represented by matrix $A$ in our standard basis. Jennifer wants to apply this same physical transformation to a vector written in her coordinate language.

She cannot simply multiply her vector by $A$, because $A$ expects coordinates written in our language. She must execute a three-step translation pipeline:

```text
  [ Jennifer's Coordinates ]
              │
              │  1. Multiply by P (Translate to Our language)
              ▼
    [ Our Coordinates ]
              │
              │  2. Multiply by A (Apply the Transformation)
              ▼
[ Transformed Our Coordinates ]
              │
              │  3. Multiply by P⁻¹ (Translate back to Jennifer's)
              ▼
 [ Jennifer's Final Result ]
```
