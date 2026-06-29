---
tags:
  - linear-algebra
  - mathematics
  - 3blue1brown
  - notes
topic: Quick Trick for Computing Eigenvalues
series: Essence of Linear Algebra
video_url: https://youtu.be/e50Bj7X6v6M
---

# Quick Trick for Computing Eigenvalues

**Source:** 3Blue1Brown (Essence of Linear Algebra, Chapter 15)

---

## 1. The Standard 2D Bottleneck

For a $2 \times 2$ matrix, finding eigenvalues using the standard characteristic equation $\det(A - \lambda I) = 0$ requires expanding a quadratic equation:

$$ \lambda^2 - \text{Trace}(A)\lambda + \det(A) = 0 $$

While straightforward, there is an alternative geometric trick that simplifies the arithmetic by focusing on two matrix properties: the **Trace** and the **Determinant**.

---

## 2. Two Fundamental Constraints

For any $2 \times 2$ matrix, its eigenvalues $\lambda_1$ and $\lambda_2$ are strictly bound by two invariants:

1.  **The Sum Rule (Trace):** The sum of the eigenvalues is always equal to the **Trace** of the matrix (the sum of the numbers along the main diagonal):
    $$ \lambda_1 + \lambda_2 = \text{Trace}(A) = a + d $$
2.  **The Product Rule (Determinant):** The product of the eigenvalues is always equal to the **Determinant** of the matrix:
    $$ \lambda_1 \cdot \lambda_2 = \det(A) = ad - bc $$

---

## 3. The Midpoint Trick

Because we know the sum and product of the two eigenvalues, we can view them as two values sitting symmetrically around a central **midpoint ($m$)** on the number line.

- **Step 1: Find the Midpoint ($m$):** The midpoint is simply the average of the two values, which is half of the trace:
  $$ m = \frac{\text{Trace}(A)}{2} $$
- **Step 2: Express the Eigenvalues:** The eigenvalues can be written as this midpoint plus or minus some unknown distance distance ($d$):
  $$ \lambda_1 = m + d \quad \text{and} \quad \lambda_2 = m - d $$
- **Step 3: Exploit the Product Rule:** Multiply these two expressions together and set them equal to the determinant:
  $$ \lambda_1 \cdot \lambda_2 = (m + d)(m - d) = m^2 - d^2 = \det(A) $$
- **Step 4: Solve for the Distance Vector ($d$):**
  $$ d = \sqrt{m^2 - \det(A)} $$

---

## 4. The Final Calculation Shortcut

Using this mental framework, you can calculate the eigenvalues for any $2 \times 2$ matrix using this formula:

$$ \lambda = m \pm \sqrt{m^2 - \det(A)} $$

Where $m = \frac{\text{Trace}(A)}{2}$. This bypasses expanding the full polynomial and completing the square manually, framing the problem around finding a center point and a symmetric offset.
