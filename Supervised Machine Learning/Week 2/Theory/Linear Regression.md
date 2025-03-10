### 1. What is Linear Regression?

Linear regression is a statistical method to model the relationship between a **dependent variable** (target, \( y \)) and one or more **independent variables** (features, \( x \)). For simplicity, we’ll focus on **simple linear regression** with one feature.

- **Goal**: Find a straight line \( y = wx + b \) that best fits the data.
  - \( w \): Slope (weight) – how much \( y \) changes per unit of \( x \).
  - \( b \): Intercept (bias) – where the line crosses the y-axis when \( x = 0 \).
- **Example**: Predict house prices (\( y \)) based on house size (\( x \)).

#### Intuition

Imagine plotting data points on a graph. Linear regression draws the "best" line through those points to capture the trend.

---

### 2. The Cost Function

The **cost function** (or loss function) measures how well the line fits the data. It quantifies the error between the predicted values (\( \hat{y} \)) and actual values (\( y \)).

#### Common Choice: Mean Squared Error (MSE)

\[ J(w, b) = \frac{1}{n} \sum\_{i=1}^{n} (y_i - \hat{y}\_i)^2 \]

- \( n \): Number of data points.
- \( y_i \): Actual value.
- \( \hat{y}\_i = w x_i + b \): Predicted value.
- \( (y_i - \hat{y}\_i) \): Error for each point.

#### Why Squared?

- Squares make all errors positive (no cancellation).
- Larger errors are penalized more (e.g., \( 2^2 = 4 \), \( 1^2 = 1 \)).
- It’s differentiable, which helps with optimization.

#### Purpose

- A perfect fit has \( J = 0 \) (rare in real data).
- The goal is to **minimize \( J(w, b) \)** by adjusting \( w \) and \( b \).

#### Intuition

Think of the cost function as a "score." Lower scores mean better predictions. Our job is to tweak the line until the score is as low as possible.

---

### 3. Gradient Descent

**Gradient descent** is an algorithm to minimize the cost function by iteratively updating \( w \) and \( b \). It’s like walking downhill to find the lowest point in a valley.

#### How It Works

1. **Start**: Pick initial values for \( w \) and \( b \) (e.g., 0 or random).
2. **Gradient**: Calculate the slope (partial derivatives) of \( J \) with respect to \( w \) and \( b \):
   - \( \frac{\partial J}{\partial w} = \frac{-2}{n} \sum\_{i=1}^{n} (y_i - \hat{y}\_i) x_i \)
   - \( \frac{\partial J}{\partial b} = \frac{-2}{n} \sum\_{i=1}^{n} (y_i - \hat{y}\_i) \)
3. **Update**: Move parameters in the opposite direction of the gradient:
   - \( w = w - \alpha \cdot \frac{\partial J}{\partial w} \)
   - \( b = b - \alpha \cdot \frac{\partial J}{\partial b} \)
   - \( \alpha \): Learning rate (step size, e.g., 0.01).
4. **Repeat**: Keep going until \( J \) stops decreasing (convergence).

#### Intuition

- Gradient: Tells you the direction of the steepest increase in cost.
- Opposite direction: Moves you toward the minimum.
- Learning rate: Controls how big your steps are.

---

### 4. Putting It All Together: A Simple Example

Let’s predict \( y \) from \( x \) with this data:

- \( (x_1, y_1) = (1, 2) \)
- \( (x_2, y_2) = (2, 4) \)
- \( (x_3, y_3) = (3, 6) \)

True relationship: \( y = 2x \) (but we’ll pretend we don’t know this and let gradient descent find it).

#### Step-by-Step

1. **Initialize**: \( w = 0, b = 0 \), \( \alpha = 0.1 \).
2. **Iteration 1**:
   - Predictions: \( \hat{y}\_1 = 0 \cdot 1 + 0 = 0 \), \( \hat{y}\_2 = 0 \), \( \hat{y}\_3 = 0 \).
   - Cost: \( J = \frac{(2-0)^2 + (4-0)^2 + (6-0)^2}{3} = \frac{4 + 16 + 36}{3} = 18.67 \).
   - Gradients:
     - \( \frac{\partial J}{\partial w} = \frac{-2}{3} [(2-0) \cdot 1 + (4-0) \cdot 2 + (6-0) \cdot 3] = \frac{-2}{3} (2 + 8 + 18) = -18.67 \)
     - \( \frac{\partial J}{\partial b} = \frac{-2}{3} (2 + 4 + 6) = -8 \).
   - Update:
     - \( w = 0 - 0.1 \cdot (-18.67) = 1.867 \)
     - \( b = 0 - 0.1 \cdot (-8) = 0.8 \).
3. **Iteration 2**:
   - New model: \( \hat{y} = 1.867x + 0.8 \).
   - Predictions: \( \hat{y}\_1 = 2.667 \), \( \hat{y}\_2 = 4.534 \), \( \hat{y}\_3 = 6.401 \).
   - Cost: \( J = \frac{(2-2.667)^2 + (4-4.534)^2 + (6-6.401)^2}{3} \approx 0.245 \) (much lower!).
   - Repeat until \( w \approx 2, b \approx 0 \).

---

### 5. Python Implementation

Here’s how to code this in Python using NumPy:

```python
import numpy as np
import matplotlib.pyplot as plt

# Data
X = np.array([1, 2, 3])  # Features
y = np.array([2, 4, 6])  # Targets

# Initialize parameters
w, b = 0, 0
alpha = 0.1  # Learning rate
iterations = 100

# Gradient Descent
costs = []  # To track cost over time
for _ in range(iterations):
    # Predictions
    y_hat = w * X + b

    # Cost (MSE)
    cost = (1/len(X)) * np.sum((y - y_hat) ** 2)
    costs.append(cost)

    # Gradients
    dw = (-2/len(X)) * np.sum((y - y_hat) * X)
    db = (-2/len(X)) * np.sum(y - y_hat)

    # Update parameters
    w -= alpha * dw
    b -= alpha * db

# Results
print(f"Final w: {w:.3f}, b: {b:.3f}")
print(f"Final cost: {costs[-1]:.3f}")

# Plot data and line
plt.scatter(X, y, color='blue', label='Data')
plt.plot(X, w * X + b, color='red', label='Fit')
plt.xlabel('X')
plt.ylabel('y')
plt.legend()
plt.show()

# Plot cost over iterations
plt.plot(costs)
plt.xlabel('Iteration')
plt.ylabel('Cost')
plt.title('Cost vs. Iteration')
plt.show()
```

#### Output

- After 100 iterations, \( w \approx 2 \), \( b \approx 0 \), and the cost approaches 0.
- First plot: Data points with the fitted line.
- Second plot: Cost decreasing over iterations.

---

### 6. Key Takeaways

- **Linear Regression**: Models \( y = wx + b \) to fit data.
- **Cost Function**: Measures error (e.g., MSE) to evaluate the fit.
- **Gradient Descent**: Optimizes \( w \) and \( b \) by minimizing the cost iteratively.

#### Tips

- **Learning Rate**: If \( \alpha \) is too big, it may overshoot; too small, it’s slow.
- **Convergence**: Stop when the cost change is tiny or after a fixed number of iterations.
- **Scaling**: For real-world data, normalize \( x \) to help gradient descent converge faster.
