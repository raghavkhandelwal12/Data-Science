# Vector Subspace
- A `Vector Subspace` is a `subset of vector space` that itself a vector space using the same `scalar and multiplication operations`.
```
**Formal Definition** : 
- Let `V` be a vector space over the field `F`. A `subset` of  `W ⊆ V is a subspace if`:
    - `W` is a non-empty.
    - `for all u,v ∈ W, u + v ∈ W`,
    - `for all v ∈ W and a ∈ F, av ∈ W`.
```
- If these are satisfied, them `W` inherits all other vector space properties from `V`: **associativity, commutativity, identity, and inverse elements**.

# Geometric Intution
- A subspace can be thought of as a `flat` passes through  the `origin` withing the larger vector space.
- In `R^2`, a line through the origin in a subspace.
- In `R^3`, a plane through the origin is a subspace.

**It must contain the `origin, be closed under linear combinations, and be internally consistent**.

**In 2D(R^2)**:
- A `line through the origin like this`:
```
W = {[x,2x]|x∈ R}
```
- In above This is the line where the second coordinates is always `twice the first`.
- This line passes through the origin(0,0) when we put the `x=0`.
    - It contain the `zero vector`.
    - Any two point on this line can be added, and the result still lies on the line.
    - Any point multiplied by a scalar still lies on the line.
    - So, its `a subspaces of R^2`.

**But a line like** :
```
L = {[x,2x+1]|x∈R}
```
- The above equation is not pass the `origin` so it is not a `subspace`.

**In 3D(R^3)**
- A `plane through the origin` such as 
```
W = {[x,y,0]|x,y∈R}
```
- The above is a flat surface if we put `x and y equal to zero` where the `z-coordinate` is always zero.

    - Contains  the zero vector  [0,0,0]
    - Adding any two vector in this place keeps you in the plane.
    - Scaling a vector in the plane still lies in the plane.

# Conditions and Criteria for a Valid Subspace
- Subspace concepts are fundamental in may data science tasks `involving dimensionality reduction, data transformation, feature selection, embeddings etc`.

**Let's connect the `three subspace conditions to real data science use cases`.**

1. `Contains the Zero Vector`:

```
We check if the zero vector[0,0] is in W:
Let x=0
        [x,2x] = [0,2.0] = [0,0]
so the zero vectors is in W
```
**Usuage in Data Science** :

- In `Principle Component Analysis`, we first substract the mean from our dataset(centering), so that it lies around the origin.This is essential because PCA finds directions(principle components) that passes through the `origin`.

- Imagine a datast of `2D point like height and weights`. After centering the average person becomes the `origin[0,0]. PCA can finds the best direction through the origin to capture variation. `

# Principal Component Analysis (PCA) – Complete Mathematical Example

## What is PCA?

**Principal Component Analysis (PCA)** is a dimensionality reduction technique used in data science and machine learning. It transforms a dataset with possibly correlated features into a new coordinate system with linearly uncorrelated variables called **principal components**.

* The first principal component captures the direction of **maximum variance**.
* Each subsequent component captures the next highest variance **orthogonal** to previous ones.

**Goals of PCA:**

* Reduce dimensions while retaining as much information (variance) as possible.
* Simplify data visualization and modeling.
* Remove redundancy from correlated features.

---

## Where Are Subspace Properties Used in PCA?

In PCA, we use the concept of **subspaces** extensively:

* The **original feature space** is a vector space.
* Each **principal component** defines a **new subspace**.
* The **top-k principal components** span a **k-dimensional subspace** of the original n-dimensional space.
* Projecting data onto this subspace preserves variance and reduces dimensionality.

### Subspace Properties in PCA:

PCA subspaces must satisfy the following:

* **Contain the zero vector**: Centering the data ensures the mean (origin) is at zero.
* **Closed under addition and scalar multiplication**: Any linear combination of principal components remains in the subspace, preserving the vector space structure.

This aligns with the definition of a vector subspace, making PCA a direct application of linear algebra in practice.

---

## Step-by-Step PCA: Full Mathematical Example

### Given Dataset (2D):

Let:

```
X = [ [2, 0],
      [0, 2],
      [3, 1],
      [1, 3] ]
```

(4 samples, 2 features)

---

### Step 1: Center the Data (Subtract Mean)

Mean of each column:

```
mean = [ (2+0+3+1)/4, (0+2+1+3)/4 ] = [1.5, 1.5]
```

Centered data:

```
X_centered = X - mean =
[
 [ 0.5, -1.5],
 [-1.5,  0.5],
 [ 1.5, -0.5],
 [-0.5,  1.5]
]
```

---

### Step 2: Compute Covariance Matrix

Formula:

```
Sigma = (1 / (n - 1)) * X_centered^T * X_centered
```

Compute:

```
X_centered^T =
[ [ 0.5, -1.5,  1.5, -0.5],
  [-1.5,  0.5, -0.5,  1.5] ]

Covariance Matrix:
Sigma = (1/3) * [ [5, -3], [-3, 5] ] = [ [5/3, -1], [-1, 5/3] ]
```

---

### Step 3: Find Eigenvalues and Eigenvectors

Solve the characteristic equation:

```
det(Sigma - lambda*I) = 0
```

Matrix:

```
[ (5/3 - lambda), -1 ]
[ -1, (5/3 - lambda) ]
```

Equation:

```
(5/3 - lambda)^2 - 1 = 0
=> (5/3 - lambda) = ±1
```

Solutions:

```
lambda1 = 5/3 + 1 = 8/3
lambda2 = 5/3 - 1 = 2/3
```

Eigenvectors:

* For lambda1 = 8/3:
  Solve (Sigma - lambda1\*I) \* v = 0
  Results in: v1 = \[1, -1]

* For lambda2 = 2/3:
  Results in: v2 = \[1, 1]

---

### Step 4: Project Data onto Principal Components

Project each row of X\_centered onto v1:

```
z = x . v1
```

Projection results:

```
[0.5, -1.5] . [1, -1] =  2.0
[-1.5, 0.5] . [1, -1] = -2.0
[1.5, -0.5] . [1, -1] =  2.0
[-0.5, 1.5] . [1, -1] = -2.0
```

Final projected 1D data:

```
Z = [2.0, -2.0, 2.0, -2.0]
```

---

## Summary Table

| Step                  | Output                                                      |
| --------------------- | ----------------------------------------------------------- |
| Centered Data         | \[ \[0.5, -1.5], \[-1.5, 0.5], \[1.5, -0.5], \[-0.5, 1.5] ] |
| Covariance Matrix     | \[ \[5/3, -1], \[-1, 5/3] ]                                 |
| Eigenvalues           | 8/3, 2/3                                                    |
| Eigenvectors          | v1 = \[1, -1], v2 = \[1, 1]                                 |
| Projected Data on PC1 | \[2, -2, 2, -2]                                             |

---

## PCA Intuition

* PCA finds new axes (principal components) that best explain the data variance.
* These new axes are orthogonal (90° apart).
* You reduce dimensions by keeping only the components with the highest eigenvalues.
* The top-k components define a **k-dimensional subspace** of the original space, retaining key structure.

---

2. `Closure Under Addition` : 
- We want to show that if
```
u = [x1,2x1]∈W and v = [x2,2x2]∈W
then their sum

u+v = [x1+x2,2x1+2x2]∈W
now observe [x1+x2,2x1+2x2] = [x1+x2,2(x1+x2)] 
- x' = x1+x2
so now [x',2x`]
where x' = x1+x2
- The sum is also in the smae forms as elements of W, which proves
u+v∈W
```
**Used in Data Science**
- In natural language processing, word vectors lie in `high dimensional vector space`. Adding vectors combining meanings and the result remains in the same subspace.

3. `Closure Under Scalar Multiplication` : 
- We take nay v = [x,2x]∈W and any scalar a∈R and check
```
a.v = a[x,2x] = [ax,a.2x] = [x',2x'] where x'=ax
so the sclar multiple is still in the form of [x,2x] hence
a.v∈W
```

# Use Subspace in Data Science
1. `PCA(Principle Component Analysis)` : 
    - Projects data into a `lower-dimensional subspace` while preserving variance. Meaning that in `higher dimensional data(many features or variables)` and this compresses it into fewer dimensions, but keeps `as much important information(variance)` as possible.
    - `Eigenvalue form the basis of a new subspace`. 
```
Let says your data has 100 features
- compute the covariance matrix and find eigenvectors as we calculate above of it.
- Pick the top 2 or 3 eigenvectors with highest eighenvalue.
- These vectors form the principle componenet.
- The subspace spanned by these vector is where the most variance(information) in your data lies.
- You then project you data into this subspace for visualization or modeling.
```

2. `Null Space in Linear Regression` : 
    - Detect `multicolinearity or redundancy in features`.
    - Vectors in null space don't affect output and span a hidden subspace.

3. `Clustering(e.g K-means)` : Each cluster is approximately centered in its own `convex subspace.`

# Relation between Subspaces and Dimensionality Reduction

- `Dimensionality Reduction` means reducing the number of features of variables in our data, while still keeping the important information. 
- Techniques like `PCA(Principle Component Analysis), LDA(Linear Disciminant Analysis) and factor analysis` do this by finding a `smaller subspace` inside the bigger space where our data lives.

**What does that means**
- Think of our data as points in a `high-dimensional space(many feature = many dimensions)`.
- These method `find a new smaller space(called a subspace)` where our data still makes `sense and tells` the smae story.
- This smaller subspace is like a `new coordinate system` that keeps important patterns and throws away the noise  or less useful information.

**Why do we do this?**
- Faster computations
- Easier visualizations
- Better generaizations
- Simple models.
