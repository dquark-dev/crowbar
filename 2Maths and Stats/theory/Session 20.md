Gradient Algorithms, Local/Global Maxima and Minima
Saddle Point, Convex Functions
Gradient Descent Algorithms-Batch, Mini-Batch, Stochastic
Performance Comparison

### **Gradient Algorithms, Local/Global Maxima and Minima**  

#### **Definition**:  
- **Gradient Algorithms**: Optimization methods that use gradients to find minima/maxima of functions.  
- **Local Minima/Maxima**: Points where a function has the lowest/highest value in a *neighborhood* (but not necessarily globally).  
- **Global Minima/Maxima**: Points where a function has the absolute lowest/highest value.  

#### **Use Case**:  
- **Machine Learning**: Training models by minimizing loss functions.  
- **Engineering**: Optimizing designs for cost or performance.  

#### **Example**:  
- **Local vs. Global**:  
  - $$ f(x) = x^4 - x^2 $$ has a local max at \( x = 0 \) and global minima at \( x = \pm \sqrt{1/2} \).  

---

### **Saddle Points**  

#### **Definition**:  
- A critical point where the gradient is zero, but it is neither a minimum nor a maximum (e.g., a "flat" region or a hyperbolic point).  
- **Hessian Matrix Test**:  
  - If eigenvalues of the Hessian are *mixed* (positive and negative) → saddle point.  

#### **Use Case**:  
- **Deep Learning**: High-dimensional loss landscapes often have saddle points, not local minima.  

#### **Example**:  
- $$f(x, y) = x^2 - y^2$$ has a saddle point at \( (0,0) \).  

---

### **Convex Functions**  

#### **Definition**:  
- A function \( f \) is **convex** if for any two points \( x, y \): 
  $$f(\lambda x + (1-\lambda)y) \leq \lambda f(x) + (1-\lambda)f(y), \quad \lambda \in [0,1]$$

- **Key Property**: Any local minimum is a global minimum.  
#### **Use Case**:  
- **Optimization**: Guarantees convergence to the global optimum (e.g., linear regression).  
#### **Example**:  
- $$f(x) = x^2 is convex$$
- $$f(x) = \sin(x) is *not* convex$$

---

### **Gradient Descent Algorithms**  

#### **1. Batch Gradient Descent**  
**Definition**:  
- Computes gradient using the *entire dataset* at each step.  
- **Update Rule**:  
  $$\theta_{k+1} = \theta_k - \alpha \nabla_\theta J(\theta; \text{all data})
   $$

**Use Case**:  
- Small datasets or simple models (e.g., linear regression).  

**Example**:  
- Training a linear model on 1,000 data points.  

#### **2. Mini-Batch Gradient Descent**  
**Definition**:  
- Computes gradient using a *subset (batch)* of data at each step (typical batch size: 32–512).  

**Use Case**:  
- **Deep Learning**: Balances speed and stability (e.g., training CNNs).  

**Example**:  
- Training a neural network with batch size = 64.  

#### **3. Stochastic Gradient Descent (SGD)**  
**Definition**:  
- Computes gradient using *one random sample* at a time.  
- **Update Rule**:  
  $$\theta_{k+1} = \theta_k - \alpha \nabla_\theta J(\theta; \text{one example})
$$

**Use Case**:  
- Online learning or very large datasets.  

**Example**:  
- Real-time recommendation systems.  

---

### **Performance Comparison**  

| **Algorithm**     | **Computational Cost** | **Convergence Speed** | **Noise in Updates** | **Use Case**       |     |
| ----------------- | ---------------------- | --------------------- | -------------------- | ------------------ | --- |
| **Batch GD**      | High (per iteration)   | Slow                  | Low                  | Small datasets     |     |
| **Mini-Batch GD** | Moderate               | Moderate              | Medium               | Deep learning      |     |
| **Stochastic GD** | Low                    | Fast (but erratic)    | High                 | Large-scale/online |     |

**Trade-offs**:  
- **Batch GD**: Precise but slow.  
- **SGD**: Fast but noisy (may need learning rate tuning).  
- **Mini-Batch**: Best of both worlds.  

---

### **Key Takeaways**  
1. **Convexity** ensures no saddle points/local minima traps.  
2. **SGD** escapes saddle points faster due to noise.  
3. **Mini-Batch GD** is the default choice for deep learning.  

**Example**:  
- Training a neural network:  
  - Use **Mini-Batch GD** (batch size = 32).  
  - Avoid **Batch GD** (too slow for big data).  

Let me know if you'd like a deeper dive into optimization tricks (e.g., momentum, Adam)!
