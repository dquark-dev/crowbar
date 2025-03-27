Optimization Using Gradient Descent
Constrained Optimization and Lagrange Multipliers
Convex Optimization

### **Optimization Using Gradient Descent**  
**Definition**:  
- Iterative algorithm to minimize a function \( f(\mathbf{x}) \) by moving in the direction of the negative gradient:  
  \[
  \mathbf{x}_{k+1} = \mathbf{x}_k - \alpha \nabla f(\mathbf{x}_k)
  \]  
  where \( \alpha \) is the **learning rate**.  

**Use Case**:  
- Training machine learning models (e.g., linear regression, neural networks).  
- Solving large-scale optimization problems.  

**Example**:  
- Minimize \( f(x) = x^2 \):  
  - Gradient: \( \nabla f(x) = 2x \).  
  - Update: \( x_{k+1} = x_k - \alpha \cdot 2x_k \).  
  - Converges to \( x = 0 \) (global minimum).  

---

### **Constrained Optimization & Lagrange Multipliers**  
**Definition**:  
- Optimize \( f(\mathbf{x}) \) subject to constraints \( g_i(\mathbf{x}) = 0 \) or \( h_j(\mathbf{x}) \leq 0 \).  
- **Lagrange multipliers** convert constrained problems to unconstrained ones:  
  \[
  \mathcal{L}(\mathbf{x}, \lambda) = f(\mathbf{x}) + \sum \lambda_i g_i(\mathbf{x})
  \]  
  where \( \lambda_i \) are Lagrange multipliers.  

**Use Case**:  
- Economics (utility maximization with budget constraints).  
- Support Vector Machines (SVMs) in ML.  

**Example**:  
- Maximize \( f(x,y) = xy \) subject to \( x + y = 10 \):  
  - Lagrangian: \( \mathcal{L} = xy + \lambda (10 - x - y) \).  
  - Solve \( \nabla \mathcal{L} = 0 \): yields \( x = y = 5 \).  

---

### **Convex Optimization**  
**Definition**:  
- Minimize a **convex function** \( f(\mathbf{x}) \) over a **convex set**.  
- **Convex function**: Graph lies below any chord (e.g., \( f(x) = x^2 \)).  
- **Convex set**: Line segment between any two points lies in the set.  

**Use Case**:  
- Portfolio optimization in finance.  
- Engineering design (e.g., minimizing material cost).  

**Example**:  
- **Linear Programming (LP)**:  
  Minimize \( \mathbf{c}^T \mathbf{x} \) subject to \( A\mathbf{x} \leq \mathbf{b} \).  
  - Solvable efficiently (e.g., via simplex method).  

---

### **Key Summary Table**  

| Concept                  | Key Idea                                     | Example                                                                       |     |
| ------------------------ | -------------------------------------------- | ----------------------------------------------------------------------------- | --- |
| **Gradient Descent**     | Follow negative gradient to minimize \( f \) | \( x^2 \rightarrow x_{k+1} = x_k - 2\alpha x_k \)                             |     |
| **Lagrange Multipliers** | Add constraints to objective function        | \( \max xy \) s.t. \( x + y = 10 \) → \( x = y = 5 \)                         |     |
| **Convex Optimization**  | Global minima guaranteed for convex problems | LP: \( \min \mathbf{c}^T \mathbf{x} \) s.t. \( A\mathbf{x} \leq \mathbf{b} \) |     |

**Pro Tips**:  
- **Gradient Descent**: Choose \( \alpha \) carefully (too small → slow; too large → divergence).  
- **Convexity**: Verify \( f \) is convex (e.g., Hessian \( \nabla^2 f \succeq 0 \)).  

Let me know if you'd like examples from ML or finance!