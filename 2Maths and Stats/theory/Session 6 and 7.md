Matrices Definition, Addition, Transpose
Scalar Multiplication, Matrix Multiplication, Matrix Multiplication Properties
Hadamard Product, Functions, Linear Transformation, Determinant, Identity Matrix,
Invertible

### **Matrices: Definition, Addition, Transpose**  
**Definition**:  
- A **matrix** is a rectangular array of numbers arranged in rows and columns (e.g., $$A \in \mathbb{R}^{m \times n}$$  
- **Addition**: Matrices of the same size are added element-wise: $$ (A + B)_{ij} = A_{ij} + B_{ij}$$
- **Transpose**: Flips rows and columns: $$(A^T)_{ij} = A_{ji}$$
**Use Case**:
- Represent systems of equations, transformations, and data tables.  
- Transpose used in dot products, symmetric matrices.  

**Example**:  
- \( A = \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix}, B = \begin{bmatrix} 5 & 6 \\ 7 & 8 \end{bmatrix} \)  
  - \( A + B = \begin{bmatrix} 6 & 8 \\ 10 & 12 \end{bmatrix} \)  
  - \( A^T = \begin{bmatrix} 1 & 3 \\ 2 & 4 \end{bmatrix} \).  

---  

### **Scalar Multiplication**  
**Definition**: Multiply every element of a matrix by a scalar \( c \): \( (cA)_{ij} = c \cdot A_{ij} \).  

**Use Case**: Scaling transformations, adjusting weights in ML.  

**Example**:  
- \( 2 \cdot \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} = \begin{bmatrix} 2 & 4 \\ 6 & 8 \end{bmatrix} \).  

---  

### **Matrix Multiplication**  
**Definition**: For \( A \in \mathbb{R}^{m \times n} \), \( B \in \mathbb{R}^{n \times p} \), the product \( C = AB \) is defined as:  
\[ C_{ij} = \sum_{k=1}^n A_{ik} B_{kj} \]  
(Number of columns in \( A \) = rows in \( B \)).  

**Use Case**: Composing linear transformations (e.g., rotations), neural networks.  

**Example**:  
- \( \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} \begin{bmatrix} 5 & 6 \\ 7 & 8 \end{bmatrix} = \begin{bmatrix} 19 & 22 \\ 43 & 50 \end{bmatrix} \).  

---  
### **Matrix Multiplication Properties**  
**Key Properties**:  
1. **Not commutative**: $$ AB \neq BA$$ (generally).  
2. **Associative**: $$ A(BC) = (AB)C$$
3. **Distributive**: $$A(B + C) = AB + AC$$
**Use Case**: Simplifying matrix expressions, proofs.  

**Example**:  
- \( A(B + C) = AB + AC \) (distributivity holds).  

---  

### **Hadamard Product**  
**Definition**: Element-wise multiplication: $$(A \odot B)_{ij} = A_{ij} \cdot B_{ij}$$

**Use Case**: Image filtering, masking operations.  

**Example**:  
- \( \begin{bmatrix} 1 & 2 \\ 3 & 4 \end{bmatrix} \odot \begin{bmatrix} 5 & 6 \\ 7 & 8 \end{bmatrix} = \begin{bmatrix} 5 & 12 \\ 21 & 32 \end{bmatrix} \).  

---  

### **Functions & Linear Transformations**  
**Definition**: A matrix \( A \) defines a linear transformation $$T(\mathbf{x}) = A\mathbf{x}$$ 
**Use Case**: Rotations, projections, data encoding.  

**Example**:  
- Rotation by \( 90^\circ \): \( A = \begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \).  

---  

### **Determinant**  
**Definition**: A scalar value \( \det(A) \) for square matrices, measuring volume scaling.  

**Use Case**: Invertibility check $$\det \neq 0$$, solving linear systems.  

**Example**:  
- \( \det \begin{bmatrix} a & b \\ c & d \end{bmatrix} = ad - bc \).  

---  

### **Identity Matrix**  
**Definition**: Square matrix \( I_n \) with 1s on the diagonal, 0s elsewhere.  

**Use Case**: Neutral element in multiplication (\( AI = A \)).  

**Example**:  
- $$I_2 = \begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}$$  

---  

### **Invertible Matrices**  
**Definition**: \( A \) is invertible if \( \exists A^{-1} \) such that \( AA^{-1} = I \).  

**Use Case**: Solving $$A\mathbf{x} = \mathbf{b}$$, cryptography.  

**Example**:  
- \( A = \begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix} \), \( A^{-1} = \begin{bmatrix} 0.5 & 0 \\ 0 & 1/3 \end{bmatrix} \).  

---  
**Key Notes**:  
- Matrix multiplication ≠ Hadamard product.  
- Determinant = 0 → matrix is singular (non-invertible).  
- Identity matrix = "1" for matrices. 
