Gradients of Vector Valued Functions
Gradient of Matrices
Useful Identities for Computing Gradients
Back propagation and Automatic Differentiation
Linearization and Multivariate Taylor Series

### **Gradients of Vector-Valued Functions**  
**Definition**:  
- For a function \( \mathbf{f}: \mathbb{R}^n \rightarrow \mathbb{R}^m \), the gradient is a **matrix** (Jacobian) of partial derivatives:  
  \[
  \nabla \mathbf{f} = \begin{bmatrix}
  \frac{\partial f_1}{\partial x_1} & \cdots & \frac{\partial f_1}{\partial x_n} \\
  \vdots & \ddots & \vdots \\
  \frac{\partial f_m}{\partial x_1} & \cdots & \frac{\partial f_m}{\partial x_n}
  \end{bmatrix}
  \]  
- Each row is the gradient of a component \( f_i \).  

**Use Case**:  
- Robotics (Jacobian in kinematics).  
- Neural networks (backpropagation).  

**Example**:  
- \( \mathbf{f}(x,y) = \begin{bmatrix} x^2 + y \\ \sin(x) \end{bmatrix} \):  
  \[
  \nabla \mathbf{f} = \begin{bmatrix}
  2x & 1 \\
  \cos(x) & 0
  \end{bmatrix}
  \]  

---

### **Gradient of Matrices**  
**Definition**:  
- For a scalar function \( f: \mathbb{R}^{m \times n} \rightarrow \mathbb{R} \), the gradient is a matrix of partial derivatives:  
  \[
  \nabla_X f = \begin{bmatrix}
  \frac{\partial f}{\partial X_{11}} & \cdots & \frac{\partial f}{\partial X_{1n}} \\
  \vdots & \ddots & \vdots \\
  \frac{\partial f}{\partial X_{m1}} & \cdots & \frac{\partial f}{\partial X_{mn}}
  \end{bmatrix}
  \]  

**Use Case**:  
- Matrix optimization (e.g., deep learning weight updates).  

**Example**:  
- \( f(X) = \text{tr}(X^T X) \), \( \nabla_X f = 2X \).  

---

### **Useful Identities for Computing Gradients**  
**Key Identities**:  
1. **Linear**: \( \nabla (\mathbf{a}^T \mathbf{x}) = \mathbf{a} \).  
2. **Quadratic**: \( \nabla (\mathbf{x}^T A \mathbf{x}) = (A + A^T)\mathbf{x} \).  
3. **Chain Rule**: \( \nabla (f \circ g)(\mathbf{x}) = \nabla f(g(\mathbf{x})) \cdot \nabla g(\mathbf{x}) \).  

**Use Case**:  
- Simplifying gradient calculations in optimization.  

**Example**:  
- \( f(\mathbf{x}) = \mathbf{x}^T A \mathbf{x} \), \( \nabla f = (A + A^T)\mathbf{x} \).  

---

### **Backpropagation and Automatic Differentiation**  
**Definition**:  
- **Backpropagation**: Efficiently computes gradients in neural networks using the chain rule.  
- **Autodiff**: Algorithmic differentiation using computational graphs.  

**Use Case**:  
- Training deep learning models.  

**Example**:  
- For a neural network with loss \( L \), backprop computes \( \frac{\partial L}{\partial W} \) for each weight \( W \).  

---

### **Linearization and Multivariate Taylor Series**  
**Definition**:  
- **Linearization**: Approximate \( f(\mathbf{x}) \) near \( \mathbf{a} \) as:  
  \[
  f(\mathbf{x}) \approx f(\mathbf{a}) + \nabla f(\mathbf{a})^T (\mathbf{x} - \mathbf{a})
  \]  
- **Multivariate Taylor**: Higher-order approximation:  
  \[
  f(\mathbf{x}) \approx f(\mathbf{a}) + \nabla f(\mathbf{a})^T (\mathbf{x} - \mathbf{a}) + \frac{1}{2} (\mathbf{x} - \mathbf{a})^T H(\mathbf{a}) (\mathbf{x} - \mathbf{a})
  \]  
  where \( H \) is the Hessian matrix.  

**Use Case**:  
- Optimization (Newton’s method).  
- Physics (small perturbations).  

**Example**:  
- \( f(x,y) = e^{xy} \) at \( (0,0) \):  
  \[
  f(x,y) \approx 1 + 0 + \frac{1}{2} (x^2 \cdot 0 + 2xy \cdot 1 + y^2 \cdot 0) = 1 + xy
  \]  

---

### **Key Summary Table**  

| Concept               | Formula/Definition                  | Example                          |  
|-----------------------|-------------------------------------|----------------------------------|  
| **Vector Gradient**   | \( \nabla \mathbf{f} = \text{Jacobian} \) | \( \nabla \begin{bmatrix} x^2 \\ \sin(y) \end{bmatrix} = \begin{bmatrix} 2x & 0 \\ 0 & \cos(y) \end{bmatrix} \) |  
| **Matrix Gradient**   | \( \nabla_X f = \left[ \frac{\partial f}{\partial X_{ij}} \right] \) | \( \nabla_X \text{tr}(X^T X) = 2X \) |  
| **Backpropagation**   | Chain rule applied to NN layers     | \( \frac{\partial L}{\partial W} \) for weight updates |  
| **Multivariate Taylor** | \( f(\mathbf{x}) \approx f(\mathbf{a}) + \nabla f(\mathbf{a})^T (\mathbf{x} - \mathbf{a}) \) | \( e^{xy} \approx 1 + xy \) near \( (0,0) \) |  

**Pro Tip**:  
- Autodiff frameworks (e.g., PyTorch, TensorFlow) automate gradient computations using backpropagation.  

Let me know if you'd like deeper dives into neural networks or optimization!