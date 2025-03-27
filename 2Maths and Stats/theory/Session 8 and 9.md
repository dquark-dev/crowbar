Matrix and Inverse, Rank, Trace
Popular Type of Matrices-Symmetric, Diagonal, Orthogonal, Orthonormal
Positive Definite Matrix
Matrix Phylogeny
Matrix Approximation

### **Matrix and Inverse**  
**Definition**:  
- A square matrix \( A \) has an **inverse** \( A^{-1} \) if \( AA^{-1} = A^{-1}A = I \).  
- Inverse exists iff \( \det(A) \neq 0 \) (non-singular).  

**Use Case**:  
- Solving linear systems \( A\mathbf{x} = \mathbf{b} \) via \( \mathbf{x} = A^{-1}\mathbf{b} \).  
- Change of basis in transformations.  

**Example**:  
- \( A = \begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix} \), \( A^{-1} = \begin{bmatrix} 0.5 & 0 \\ 0 & 1/3 \end{bmatrix} \).  

---  

### **Rank of a Matrix**  
**Definition**:  
- The **rank** is the dimension of the column/row space (max # of linearly independent rows/columns).  
- Full rank = rank = min(# rows, # columns).  

**Use Case**:  
- Determines solvability of \( A\mathbf{x} = \mathbf{b} \) (full rank ⇒ unique solution).  
- Used in dimensionality reduction (e.g., PCA).  

**Example**:  
- \( \text{rank}\begin{bmatrix} 1 & 2 \\ 3 & 6 \end{bmatrix} = 1 \) (rows are linearly dependent).  

---  

### **Trace of a Matrix**  
**Definition**: Sum of diagonal elements: \( \text{tr}(A) = \sum A_{ii} \).  

**Use Case**:  
- Invariant under similarity transformations.  
- Used in eigenvalues (sum of eigenvalues = trace).  

**Example**:  
- \( \text{tr}\begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} = 1 + 4 = 5 \).  

---  

### **Popular Types of Matrices**  
1. **Symmetric Matrix**: \( A = A^T \) (e.g., covariance matrices).  
   - *Example*: \( \begin{bmatrix} 1 & 2 \\ 2 & 3 \end{bmatrix} \).  
2. **Diagonal Matrix**: Non-zero entries only on diagonal (e.g., scaling matrices).  
   - *Example*: \( \begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix} \).  
3. **Orthogonal Matrix**: \( A^T A = I \) (columns are orthonormal).  
   - *Example*: Rotation matrices like \( \begin{bmatrix} \cos \theta & -\sin \theta \\ \sin \theta & \cos \theta \end{bmatrix} \).  
4. **Orthonormal Matrix**: Orthogonal with unit-norm columns.  

**Use Case**:  
- Symmetric: Eigenvalue decomposition (e.g., PCA).  
- Orthogonal: Preserves vector norms (e.g., rotations).  

---  

### **Positive Definite Matrix**  
**Definition**:  
- A symmetric matrix \( A \) where \( \mathbf{x}^T A \mathbf{x} > 0 \) for all \( \mathbf{x} \neq 0 \).  
- All eigenvalues > 0.  

**Use Case**:  
- Optimization (convex functions).  
- Covariance matrices in statistics.  

**Example**:  
- \( \begin{bmatrix} 2 & -1 \\ -1 & 2 \end{bmatrix} \) (check \( \mathbf{x}^T A \mathbf{x} = 2x_1^2 - 2x_1x_2 + 2x_2^2 > 0 \)).  

---  

### **Matrix Phylogeny**  
**Definition**: Classification of matrices based on properties:  
- **Singular vs. Non-singular**: \( \det(A) = 0 \) vs. \( \det(A) \neq 0 \).  
- **Square vs. Rectangular**: \( m = n \) vs. \( m \neq n \).  
- **Sparse vs. Dense**: Most entries zero vs. non-zero.  

**Use Case**:  
- Guides algorithm selection (e.g., sparse matrices use specialized solvers).  

**Example**:  
- Diagonal matrices are sparse; covariance matrices are dense.  

---  

### **Matrix Approximation**  
**Definition**: Representing a matrix \( A \) with a lower-rank approximation \( \hat{A} \) (e.g., via SVD).  

**Use Case**:  
- Dimensionality reduction (e.g., PCA, image compression).  
- Noise reduction in data.  

**Example**:  
- SVD approximation: \( A \approx U_k \Sigma_k V_k^T \), where \( k \) is the reduced rank.  

---  
**Key Notes**:  
- **Inverse**: Only for square, non-singular matrices.  
- **Rank**: Reveals redundancy in data.  
- **Positive Definite**: Ensures stability in optimization.  
- **Approximation**: Balances accuracy vs. efficiency.  

Let me know if you'd like elaborations on specific applications!