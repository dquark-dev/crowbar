Functions, Scalar Derivative, Definition, Intuition
Common Rules Of Differentiation, Chain Rule

### **Functions & Scalar Derivatives**  

#### **Definition**:  
- **Function**: A rule that maps an input \( x \) to an output \( f(x) \) (e.g., \( f(x) = x^2 \)).  
- **Derivative**: Measures the rate of change of \( f(x) \) w.r.t. \( x \). Defined as:  
  \[
  f'(x) = \lim_{h \to 0} \frac{f(x+h) - f(x)}{h}
  \]  

#### **Intuition**:  
- Slope of the tangent line to \( f(x) \) at point \( x \).  
- **Interpretation**:  
  - \( f'(x) > 0 \): Function is increasing.  
  - \( f'(x) < 0 \): Function is decreasing.  

#### **Use Case**:  
- Optimization (finding maxima/minima).  
- Physics (velocity = derivative of position).  

#### **Example**:  
- \( f(x) = 3x^2 \), \( f'(x) = 6x \).  
  - At \( x = 2 \), slope \( f'(2) = 12 \).  

---

### **Common Rules of Differentiation**  

#### **1. Power Rule**:  
\[
\frac{d}{dx} x^n = n x^{n-1}
\]  
- **Example**: \( \frac{d}{dx} x^3 = 3x^2 \).  

#### **2. Sum Rule**:  
\[
\frac{d}{dx} [f(x) + g(x)] = f'(x) + g'(x)
\]  
- **Example**: \( \frac{d}{dx} (x^2 + \sin x) = 2x + \cos x \).  

#### **3. Product Rule**:  
\[
\frac{d}{dx} [f(x) \cdot g(x)] = f'(x)g(x) + f(x)g'(x)
\]  
- **Example**: \( \frac{d}{dx} (x^2 e^x) = 2x e^x + x^2 e^x \).  

#### **4. Quotient Rule**:  
\[
\frac{d}{dx} \left( \frac{f(x)}{g(x)} \right) = \frac{f'(x)g(x) - f(x)g'(x)}{g(x)^2}
\]  
- **Example**: \( \frac{d}{dx} \left( \frac{\sin x}{x} \right) = \frac{x \cos x - \sin x}{x^2} \).  

#### **Use Case**:  
- Simplifying complex derivatives (e.g., in gradient descent).  

---

### **Chain Rule**  

#### **Definition**:  
- For composite functions \( h(x) = f(g(x)) \):  
  \[
  h'(x) = f'(g(x)) \cdot g'(x)
  \]  
- **Intuition**: Rate of change cascades through nested functions.  

#### **Use Case**:  
- Backpropagation in neural networks.  
- Differentiating complex models (e.g., \( \sin(x^2) \)).  

#### **Example**:  
- \( h(x) = \sin(3x) \):  
  - Let \( f(u) = \sin u \), \( u = g(x) = 3x \).  
  - Then \( h'(x) = \cos(u) \cdot 3 = 3 \cos(3x) \).  

---

### **Key Summary Table**  

| Concept               | Rule/Formula                          | Example                          |  
|-----------------------|---------------------------------------|----------------------------------|  
| **Power Rule**        | \( \frac{d}{dx} x^n = n x^{n-1} \)   | \( \frac{d}{dx} x^4 = 4x^3 \)   |  
| **Product Rule**      | \( (fg)' = f'g + fg' \)              | \( (x e^x)' = e^x + x e^x \)     |  
| **Chain Rule**        | \( f(g(x))' = f'(g(x)) g'(x) \)      | \( \frac{d}{dx} e^{2x} = 2e^{2x} \) |  

**Pro Tip**:  
- Chain rule is crucial for **auto-differentiation** in ML frameworks (e.g., TensorFlow, PyTorch).  

Let me know if you'd like more examples or applications!