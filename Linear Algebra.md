# Linear Algebra

### Vector Space
- **Definition:** A set of vectors where addition and scalar multiplication are defined and satisfy certain axioms (closure, associativity, identity, etc.).
- **Example:** The set of all $\ n $-dimensional vectors, $\\ {R}^n$.

### Subspaces
- **Definition:** A subset of a vector space that is also a vector space under the same operations.
- **Example:** The set of all vectors in $\ {R}^3 $ that lie on a plane through the origin.

### Linear Dependence and Independence of Vectors
- **Linear Dependence:** Vectors $\ \{v_1, v_2, \ldots, v_k\} $ are linearly dependent if there exist scalars $\ a_1, a_2, \ldots, a_k $, not all zero, such that $\ a_1 v_1 + a_2 v_2 + \ldots + a_k v_k = 0 $.
- **Linear Independence:** Vectors are linearly independent if the only solution to $\ a_1 v_1 + a_2 v_2 + \ldots + a_k v_k = 0 $ is $\ a_1 = a_2 = \ldots = a_k = 0 $.

### Matrices
- **Definition:** Rectangular array of numbers, symbols, or expressions, arranged in rows and columns.
- **Operations:** Addition, multiplication, transpose, inverse.

### Projection Matrix
- **Definition:** A matrix $\ P $ such that $\ P^2 = P $.
- **Example:** Orthogonal projection onto a subspace.

### Orthogonal Matrix
- **Definition:** A square matrix $\ Q $ such that $\ Q^T Q = QQ^T = I $, where $\ I $ is the identity matrix.
- **Properties:** Preserves lengths and angles.

### Idempotent Matrix
- **Definition:** A matrix $\ A $ such that $\ A^2 = A $.
- **Example:** Projection matrices are idempotent.

### Partition Matrix and Their Properties
- **Definition:** A matrix divided into smaller matrices called blocks or submatrices.
- **Properties:** Operations on partitioned matrices follow certain rules similar to standard matrix operations.

### Quadratic Forms
- **Definition:** A homogeneous polynomial of degree 2 in a number of variables.
- **Example:** $\ Q(x) = x^T A x $, where $\ A $ is a symmetric matrix.

### Systems of Linear Equations and Solutions
- **Definition:** A collection of linear equations involving the same set of variables.
- **Methods of Solution:** Substitution, elimination, matrix methods (Gaussian elimination).

### Gaussian Elimination
- **Definition:** A method for solving systems of linear equations by transforming the matrix to row-echelon form.
- **Steps:** Forward elimination, back substitution.

### Eigenvalues and Eigenvectors
- **Eigenvalue (λ):** A scalar such that $\ A v = \lambda v $ for some nonzero vector $\ v $.
- **Eigenvector:** The vector $\ v $ associated with eigenvalue $\ \lambda $.

### Determinant
- **Definition:** A scalar value that can be computed from the elements of a square matrix.
- **Properties:** Used to determine matrix invertibility (a matrix is invertible if its determinant is nonzero).

### Rank and Nullity
- **Rank:** The dimension of the column space (or row space) of a matrix.
- **Nullity:** The dimension of the null space of a matrix.
- **Relationship:** Rank-Nullity Theorem: $\ \text{rank}(A) + \text{nullity}(A) = n $ for an $\ n \times n $ matrix.

### Projections
- **Definition:** Mapping a vector onto a subspace.
- **Orthogonal Projection:** Projection onto a subspace such that the error vector is orthogonal to the subspace.

### LU Decomposition
- **Definition:** Factorization of a matrix $\ A $ into the product of a lower triangular matrix $\ L $ and an upper triangular matrix $\ U $.
- **Application:** Simplifies solving systems of linear equations.

### Singular Value Decomposition (SVD)
- **Definition:** Factorization of a matrix $\ A $ into $\ U \Sigma V^T $, where $\ U $ and $\ V $ are orthogonal matrices and $\ \Sigma $ is a diagonal matrix with singular values.
- **Application:** Used in signal processing, statistics, and machine learning.
