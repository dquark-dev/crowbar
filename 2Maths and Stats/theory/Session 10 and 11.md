Eigen Values & Eigenvectors, Concept, Intuition, Significance
How To Find Principle Component Analysis
Concept, Properties, Applications
Singular Value Decomposition

### **Eigenvalues & Eigenvectors**  
#### **Definition**:
- For a **square matrix** `A`, an **eigenvector** `v` (non-zero) and **eigenvalue** $$\lambda$$ satisfy:
   $$A\mathbf{v} = \lambda \mathbf{v}$$
- Intuitively: Eigenvectors are directions unchanged by $$ A $$; eigenvalues scale them.

#### **Significance**:
- **Key Insight**: Reveals fundamental transformation properties (e.g., stretching/rotation).  
- **Applications**:  
  - Stability analysis (e.g., differential equations).  
  - Principal Component Analysis (PCA) for dimensionality reduction.  
  - Quantum mechanics (observables).  

#### **Example**:
- For $$A = \begin{bmatrix} 2 & 1 \\ 1 & 2 \end{bmatrix}$$
Eigenvalues: $$\lambda_1 = 3, \lambda_2 = 1$$ 
Eigenvectors: $$\mathbf{v}_1 = \begin{bmatrix} 1 \\ 1 \end{bmatrix}$$ $$\mathbf{v}_2 = \begin{bmatrix} -1 \\ 1 \end{bmatrix}$$

---

### **Principal Component Analysis (PCA)**  
#### **Concept**:  
- **Goal**: Reduce data dimensionality while preserving variance.  
- **Method**: Projects data onto eigenvectors (principal components) of the covariance matrix.  

#### **Steps to Find PCA**:  
1. **Center Data**: Subtract mean from each feature.  
2. **Compute Covariance Matrix**: $$\Sigma = \frac{1}{n} X^T X$$  
3. **Find Eigenvectors/Values**: Of $$\Sigma$$  
4. **Select Top-\( k \) Eigenvectors**: Highest eigenvalues = most variance.  
5. **Project Data**: $$X_{\text{PCA}} = X V_k $$where $$V_k = top eigenvectors$$
#### **Applications**:  
- **Image Compression** (e.g., eigenfaces).  
- **Noise Reduction** (discard low-variance components).  

#### **Example**:  
- **Dataset**: 2D points with correlation.  
- **PCA**: Rotates data to align with axes of maximum variance.  

---

### **Singular Value Decomposition (SVD)**  
#### **Definition**:  
- Factorizes any m * n matrix A as:
- A = U \Sigma V^T
  - \( U \): Left singular vectors (eigenvectors of \( AA^T \)).  
  - \( \Sigma \): Diagonal matrix of singular values (\( \sigma_i = \sqrt{\lambda_i} \)).  
  - \( V \): Right singular vectors (eigenvectors of \( A^T A \)).  

#### **Properties**:  
- **Generalization**: Works for non-square matrices (unlike eigen decomposition).  
- **Low-Rank Approximation**: Truncate \( \Sigma \) to approximate \( A \).  

#### **Applications**:  
- **Recommendation Systems** (collaborative filtering).  
- **Image Compression** (e.g., JPEG).  

#### **Example**:  
- For \( A = \begin{bmatrix} 1 & 1 \\ 0 & 1 \end{bmatrix} \):  
  - SVD gives \( U \), \( \Sigma \), \( V \) such that \( A = U \Sigma V^T \).  

---
### **Key Takeaways**:  
| Concept         | Key Idea                        | Use Case Example         |
| --------------- | ------------------------------- | ------------------------ |
| **Eigenvalues** | Axes of transformation scaling  | Stability analysis       |
| **PCA**         | Variance-maximizing projections | Dimensionality reduction |
| **SVD**         | Universal matrix factorization  | Data compression         |

**Eigen vs. SVD**:
- Eigen: Square matrices only.
- SVD: Any matrix, more robust.

Let me know if you’d like a deeper dive into any application!