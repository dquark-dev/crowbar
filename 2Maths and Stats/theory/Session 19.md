Vector And Matrix Calculus
How To Find Derivative Of Scalar-Valued
Vector-Valued Function With Respect To Scalar, Vector, Four Combinations- Jacobian

### **Vector and Matrix Calculus**  

#### **Definition**:  
- Extends calculus to **vectors** and **matrices**, enabling differentiation of functions with multi-dimensional inputs/outputs.  
- Key tools: **Gradient**, **Jacobian**, **Hessian**.  

#### **Use Case**:  
- Machine learning (gradient descent, backpropagation).  
- Physics (force fields, fluid dynamics).  
- Economics (optimization under constraints).  

---

### **Derivative of Scalar-Valued Functions**  

#### **1. With Respect to a Scalar**  
**Definition**:  
- Standard derivative: \( \frac{df(x)}{dx} \).  

**Example**:  
- \( f(x) = 3x^2 \) → \( \frac{df}{dx} = 6x \).  

#### **2. With Respect to a Vector**  
**Definition**:  
- **Gradient**: Vector of partial derivatives:  
  \[
  \nabla f(\mathbf{x}) = \left[ \frac{\partial f}{\partial x_1}, \frac{\partial f}{\partial x_2}, \dots, \frac{\partial f}{\partial x_n} \right]^T.
  \]  

**Example**:  
- \( f(\mathbf{x}) = x_1^2 + x_2^3 \) → \( \nabla f = [2x_1, 3x_2^2]^T \).  

#### **3. With Respect to a Matrix**  
**Definition**:  
- Matrix of partial derivatives:  
  \[
  \nabla_X f(X) = \begin{bmatrix}
  \frac{\partial f}{\partial X_{11}} & \cdots & \frac{\partial f}{\partial X_{1n}} \\
  \vdots & \ddots & \vdots \\
  \frac{\partial f}{\partial X_{m1}} & \cdots & \frac{\partial f}{\partial X_{mn}}
  \end{bmatrix}.
  \]  

**Example**:  
- \( f(X) = \text{tr}(X^T X) \) → \( \nabla_X f = 2X \).  

---

### **Derivative of Vector-Valued Functions**  

#### **1. With Respect to a Scalar**  
**Definition**:  
- Derivative of each component:  
  \[
  \frac{d\mathbf{f}(x)}{dx} = \left[ \frac{df_1}{dx}, \frac{df_2}{dx}, \dots, \frac{df_m}{dx} \right]^T.
  \]  

**Example**:  
- \( \mathbf{f}(x) = \begin{bmatrix} x^2 \\ \sin(x) \end{bmatrix} \) → \( \frac{d\mathbf{f}}{dx} = \begin{bmatrix} 2x \\ \cos(x) \end{bmatrix} \).  

#### **2. With Respect to a Vector**  
**Definition**:  
- **Jacobian Matrix**:  
  \[
  J = \begin{bmatrix}
  \frac{\partial f_1}{\partial x_1} & \cdots & \frac{\partial f_1}{\partial x_n} \\
  \vdots & \ddots & \vdots \\
  \frac{\partial f_m}{\partial x_1} & \cdots & \frac{\partial f_m}{\partial x_n}
  \end{bmatrix}.
  \]  

**Example**:  
- \( \mathbf{f}(\mathbf{x}) = \begin{bmatrix} x_1 + x_2^2 \\ e^{x_1} \end{bmatrix} \) →  
  \[
  J = \begin{bmatrix}
  1 & 2x_2 \\
  e^{x_1} & 0
  \end{bmatrix}.
  \]  

#### **3. With Respect to a Matrix**  
**Definition**:  
- **3D Tensor** (generalization of Jacobian):  
  \[
  \frac{\partial \mathbf{f}}{\partial X} = \left[ \frac{\partial \mathbf{f}}{\partial X_{ij}} \right]_{i,j}.
  \]  

**Example**:  
- Rare in practice; used in deep learning for higher-order tensors.  

---

### **Four Key Combinations**  

| **Function Type**       | **W.R.T.**  | **Result**          | **Example**                          |  
|--------------------------|-------------|---------------------|--------------------------------------|  
| Scalar-valued           | Scalar      | Scalar derivative   | \( \frac{d}{dx}(x^2) = 2x \)         |  
| Scalar-valued           | Vector      | Gradient vector     | \( \nabla (x_1^2 + x_2^2) = [2x_1, 2x_2] \) |  
| Vector-valued           | Scalar      | Vector derivative   | \( \frac{d}{dx} [x^2, \sin(x)] = [2x, \cos(x)] \) |  
| Vector-valued           | Vector      | Jacobian matrix     | \( J = \begin{bmatrix} 1 & 2x_2 \\ e^{x_1} & 0 \end{bmatrix} \) |  

---

### **Usecases**  
1. **Gradient Descent**: \( \nabla f(\mathbf{x}) \) guides weight updates in ML.  
2. **Newton’s Method**: Uses Jacobian \( J \) and Hessian \( H \) for optimization.  
3. **Backpropagation**: Jacobians chain together in neural networks.  

**Example**:  
- **Linear Regression**: Minimize \( \|A\mathbf{x} - \mathbf{b}\|^2 \) → Gradient \( \nabla f = 2A^T(A\mathbf{x} - \mathbf{b}) \).  

---

### **Key Takeaways**  
- **Scalar-by-vector**: Gradient (vector).  
- **Vector-by-vector**: Jacobian (matrix).  
- **Matrix derivatives**: Use reshaping (e.g., vectorization) for simplification.  

Let me know if you’d like to explore tensor calculus or autodiff!