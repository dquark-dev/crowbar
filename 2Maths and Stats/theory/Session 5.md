Linear Independence
Basis and Rank
Linear Mappings
Affine Spaces

### **Linear Independence**  
**Definition**: A set of vectors {v₁, v₂, ..., vₙ} is *linearly independent* if no vector in the set can be written as a linear combination of the others. Mathematically, if:  
$$c₁v₁ + c₂v₂ + \dots + cₙvₙ = 0 \implies c₁ = c₂ = \dots = cₙ = 0$$

**Use Case**: Determines if vectors provide unique information (redundant vectors lead to dependence). Used in solving systems of equations, basis selection, and dimensionality reduction.  

**Example**:  
- Independent: $$ \mathbf{v}_1 = \begin{bmatrix} 1 \\ 0 \end{bmatrix}, \mathbf{v}_2 = \begin{bmatrix} 0 \\ 1 \end{bmatrix} (no scalar multiples)$$
- Dependent: $$\mathbf{v}_1 = \begin{bmatrix} 1 \\ 2 \end{bmatrix}, \mathbf{v}_2 = \begin{bmatrix} 2 \\ 4 \end{bmatrix} (v₂ = 2v₁)$$  

---  

### **Basis and Rank**  
**Definition**:  
- *Basis*: A minimal set of linearly independent vectors that span a vector space.  
- *Rank*: The number of linearly independent columns (or rows) in a matrix, equal to the dimension of its column/row space.  

**Use Case**:  
- Basis: Represents coordinate systems (e.g., ℝ³ needs 3 basis vectors).  
- Rank: Measures non-redundancy in matrices (full rank = invertible; rank deficiency = singular).  

**Example**:  
- Basis for ℝ²: \( \begin{bmatrix} 1 \\ 0 \end{bmatrix}, \begin{bmatrix} 0 \\ 1 \end{bmatrix} \).  
- Rank of \( \begin{bmatrix} 1 & 2 \\ 3 & 6 \end{bmatrix} \) is 1 (rows are linearly dependent).  

---  
### **Linear Mappings**  
**Definition**: A function $$ T: V \to W$$ between vector spaces is *linear* if:  
1. $$T(v₁ + v₂) = T(v₁) + T(v₂) (additivity)$$  
2. $$T(c \cdot v) = c \cdot T(v) (homogeneity)$$  

**Use Case**: Models transformations like rotations, scaling, and projections. Encoded as matrices (e.g., $$T(\mathbf{x}) = A\mathbf{x}$$  

**Example**:  
- Matrix multiplication: $$A = \begin{bmatrix} 2 & 0 \\ 0 & 3 \end{bmatrix} scales x-axis by 2, y-axis by 3$$
---  
### **Affine Spaces**  
**Definition**: A translated vector space (not necessarily passing through the origin). Formally, S = `\mathbf{a} + V`, where `V` is a vector space and $$\mathbf{a}$$is a fixed vector

**Use Case**: Generalizes lines/planes not through the origin. Used in computer graphics (e.g., 3D modeling), optimization (feasible regions).  

**Example**:  
- Line in ℝ²: \( y = 2x + 1 \) is an affine space (translated subspace).  
- Plane \( x + y + z = 1 \) (does not contain (0,0,0)).  

---  
Each concept builds on the previous: independence → basis → mappings → affine spaces. Let me know if you'd like expansions!