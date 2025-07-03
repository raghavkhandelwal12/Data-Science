# Vector Spaces

- A vector space(called the linear space ) is a set of all objects called `vectors`, which can be add together and multiplied(scaled) by numbers, called `scalars`(typically real or complex numbers), `satisfying a set of properties.

**A vector space must satisfy the following axioms/Properties**

- Let `V` be a vector space over the field F(usually real number R). For ` u, v, w ∈ V and a, b ∈ R` here **u, v, w is a vector** and **a, b is a scalar**.

# Vector Spaces Property

1. `Closure Under Addition` : 
```
If u, v ∈ V, then u + v ∈ V #here u and v are vector

**Example:**  
Let u = [1, 2], v = [3, 4]  
Then u + v = [1 + 3, 2 + 4] = [4, 6] ∈ V
```

**Data Science Usuage** : In NLP, we can add word embedding to find combind meanings.

**E.g., `embedding("king") + embedding("woman") ≈ embedding("queen")`**

2. `Closure Under Scalar Multiplication`:
```
**Property:**  
If a ∈ ℝ and v ∈ V, then a · v ∈ V # here a is scalar and v is vector

**Example:**  
Let v = [2, 3], a = 4  
Then a · v = 4 · [2, 3] = [8, 12] ∈ V
```
**Data Science Usuage**
- Used in `Feature Scaling(normalization) and gradient descent`.

**Feature Scaling in Linear Regression** : In `Linear regression , the prediction is make this equation`.
```
​y cap = w1x1 + w2x2 + ... + wnxn
```
- `x1, x2,...,xn : input features (age, income)`.
- `w1, w2,...,wn : the weight learned by the model`.
- `ycap: is the predicted output`.

**What Happening** : Each `input feature xi is multiplied by a scalar(the weight wi)`. This is `scalar multiplication in vector space`. 

**Why it Matters** : It lets the model `adjust the influence of each feature`. During training, weights change using `gradient descent` to reduce error. This helps the model fit the data better.

3. `Associativity of Addition` : 

```
**Property:**  
(u + v) + w = u + (v + w) # here v, u, and w are vectors

**Example:**  
Let u = [1, 0], v = [0, 2], w = [3, 3]  
Then:  
(u + v) + w = [1, 2] + [3, 3] = [4, 5]  
u + (v + w) = [1, 0] + [3, 5] = [4, 5]
```
**Usuage in data science**
- When combining multiple inputs(image + text + metadata), the order of combination does not affect the result. Used in `multi-model embeddings(e.g. vision + language models)`.

4. `Commutativity of Addition` : 

```

**Property:**  
u + v = v + u #here v and u are vector

**Example:**  
Let u = [1, 2], v = [3, 4]  
Then u + v = [4, 6] = v + u
```
**Usuage in data science** : 
- Used in `cosin similarity`, where the order of vectors does not change the similarity.

5. `Additive Identity` : 
```
**Property:**  
There exists a zero vector 0 ∈ V such that v + 0 = v # here v is vector

**Example:**  
Let v = [5, -3]  
Then v + [0, 0] = [5, -3]
```
**Usuage in data science** : 
- In `machine learning`, when initializing weights or input vectos, we often start with `zero vectors`.
- Adding zero vector means no change helps during initialization or when no information is available.

**Sparse data** : A vector with `many zero values` and only a few non-zero values. In NLP, a `one hot vector like [0, 0, 0, 1, 0, 0] is spars`.

6. `Additive Inverse` : 
```
**Property:**  
For every v ∈ V, there exists -v ∈ V such that v + (-v) = 0 # here v is vector

**Example:**  
Let v = [2, -5]  
Then -v = [-2, 5], and v + (-v) = [0, 0]
```
**Usuage in data Science** : 
- **Gradient Descent(Optimization)** : In `machine learning`, we want to minimize the `loss function` like `Mean squared error(MSE)` or cross-entropy so that model makes better prediction.
- To do this, we `adjust the weight` of the model in `the opposite direction of the gradient`. That's where `additive inverse come in`.

7. `Distributivity of Scalar over Vector Addition` :
```
**Property:**  
a · (u + v) = a · u + a · v # here u and v are vector and a is scalar

**Example:**  
Let u = [1, 2], v = [3, 4], a = 2  
Then:  
u + v = [4, 6]  
a · (u + v) = 2 · [4, 6] = [8, 12]  
a · u + a · v = [2, 4] + [6, 8] = [8, 12]
```

**Usuage in data science** :
- **Use case : Neural Network Linear Layer** : In a neural network, a `linear(desnse) layer` compute
```
Output = W . X + b
```
- `X` : Input vector(features)
- `W` : Weight Matrix(scalars)
- `b` : Bias(vector)
- `W . X ` : Matrix-vecotr multiplication = `scaling + summing

**Let**

- `Input vector X = [x1, x2]`
- `Weight Matrix W = [w1, w2]`
- Then  `W. X = w1x1 + w2x2`

**Here**
```
- u = x1, v = x2
- a = [w1, w2]
```
- We are applying `scalar multiplication to each input, then adding up extractly the distributive property.`

8. `Distibutivity of Vector over Scalar Addition` : 
```
**Property:**  
(a + b) · v = a · v + b · v # Here a and b are scalar and v is a vector

**Example:**  
Let v = [2, 1], a = 1, b = 3  
Then:  
(a + b) · v = 4 · [2, 1] = [8, 4]  
a · v + b · v = [2, 1] + [6, 3] = [8, 4]
```
**Use in data scinece** : 
- Used in `regularization` techniques like `L2` regularization.

9. `Assoicativity of Scalar Multiplication` :
```
**Property:**  
a · (b · v) = (a · b) · v # here a and b are scalar and v is vector

**Example:**  
Let v = [1, 2], a = 2, b = 3  
Then:  
b · v = [3, 6], a · (b · v) = [6, 12]  
(a · b) · v = 6 · [1, 2] = [6, 12] 
```
**Usuage in data Science** : 
- Used in `learning rate scheduling and momentum updates in optimization`.

10. `Scalar Multiplicative Identity` : 
```
**Property:**  
1 · v = v

**Example:**  
Let v = [7, 9]  
Then 1 · v = [7, 9] # Here v for vector
```
**Usuage in Data Science** : 
- Used in `Identity layers(e.g, residual networks in deep learning).


# Real-World Use of Vector Space in Data Science

- In data science, we use the vector - which are just `list of numbers`.

**Example**
- A person(user) in a `movie recommendation system` can be represented like this
```
User vector = [4, 5, 2, 0, 1]
```
- Each number shows how much the user likes a certain movie. So each person or items becomes a `point in space` made of number this is called the vector space.

**Why vector spaces are useful**

1. `Measure Similarity` :  Check two text and similar.
2. `Project Data` : Focus on impartant part of the data.
3. `Scale features` : Make all the data values balanced.
4. `Combine Feature` : Using weight in ml models.

# Practical Example In Data Science

1. `Customer Features` : In a retail dataset, customer behavior(number of purchase, recency, amount spent) is naturally represented as a vector.

2. `Document Embeddings` : Text transformed into word or sentence vectors, which can be classified or clustered.

3. `Sensor Data` : IOT devices capture temprature, pressure, humidity, all packaged as vector.


