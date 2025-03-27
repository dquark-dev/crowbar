Partial Derivatives, Gradient
Concept, Intuition, Properties
Directional Derivative

### **Partial Derivatives**  

#### **Definition**:  
- Measures how a **multivariable function** \( f(x_1, x_2, \dots, x_n) \) changes as **one variable** changes, **holding others constant**.  
- Notation: \( \frac{\partial f}{\partial x_i} \).  

#### **Intuition**:  
- **Slope** of \( f \) along the \( x_i \)-axis in \( n \)-dimensional space.  

#### **Use Case**:  
- Optimization in ML (e.g., gradient descent).  
- Physics (e.g., heat flow, pressure gradients).  

#### **Example**:  
- \( f(x, y) = x^2 + 3xy + y^3 \)  
  - \( \frac{\partial f}{\partial x} = 2x + 3y \) (treat \( y \) as constant).  
  - \( \frac{\partial f}{\partial y} = 3x + 3y^2 \) (treat \( x \) as constant).  

---

### **Gradient (∇f)**  

#### **Definition**:  
- Vector of all partial derivatives of \( f \):  
  \[
  \nabla f = \left( \frac{\partial f}{\partial x_1}, \frac{\partial f}{\partial x_2}, \dots, \frac{\partial f}{\partial x_n} \right)
  \]  
- Points in the direction of the **steepest ascent** of \( f \).  

#### **Properties**:  
- **Perpendicular** to level curves/surfaces of \( f \).  
- **Zero gradient** ⇒ critical point (max/min/saddle).  

#### **Use Case**:  
- **Gradient descent**: Minimize loss functions in ML.  
- **Vector calculus**: Fluid dynamics, electromagnetism.  

#### **Example**:  
- \( f(x, y) = x^2 + y^2 \)  
  - \( \nabla f = (2x, 2y) \).  
  - At \( (1, 1) \): \( \nabla f = (2, 2) \) (points away from origin).  

---

### **Directional Derivative**  

#### **Definition**:  
- Rate of change of \( f \) in direction of a unit vector \( \mathbf{u} = (u_1, u_2, \dots, u_n) \):  
  \[
  D_{\mathbf{u}} f = \nabla f \cdot \mathbf{u} = \frac{\partial f}{\partial x_1} u_1 + \dots + \frac{\partial f}{\partial x_n} u_n
  \]  

#### **Intuition**:  
- **Slope** of \( f \) along an arbitrary direction \( \mathbf{u} \) (not just axes).  

#### **Use Case**:  
- Sensitivity analysis (e.g., response to perturbations).  
- Robotics (path planning along gradients).  

#### **Example**:  
- \( f(x, y) = x^2 + y^2 \), \( \mathbf{u} = \left( \frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}} \right) \) (45° direction).  
  - \( D_{\mathbf{u}} f = (2x, 2y) \cdot \left( \frac{1}{\sqrt{2}}, \frac{1}{\sqrt{2}} \right) = \sqrt{2}(x + y) \).  
  - At \( (1, 0) \): \( D_{\mathbf{u}} f = \sqrt{2} \).  

---

### **Key Summary Table**  

| Concept               | Formula/Definition                  | Example                          |  
|-----------------------|-------------------------------------|----------------------------------|  
| **Partial Derivative** | \( \frac{\partial f}{\partial x} \) | \( \frac{\partial}{\partial x}(xy) = y \) |  
| **Gradient**          | \( \nabla f = \left( \frac{\partial f}{\partial x}, \frac{\partial f}{\partial y} \right) \) | \( \nabla (x^2 + y^2) = (2x, 2y) \) |  
| **Directional Derivative** | \( D_{\mathbf{u}} f = \nabla f \cdot \mathbf{u} \) | \( D_{\mathbf{u}}(x^2 + y^2) = \sqrt{2}(x + y) \) |  

**Pro Tip**:  
- **Gradient descent** uses \( \nabla f \) to find minima:  
  \[
  \mathbf{x}_{k+1} = \mathbf{x}_k - \alpha \nabla f(\mathbf{x}_k)
  \]  
  where \( \alpha \) is the learning rate.  

Let me know if you'd like to explore applications in ML or physics further!