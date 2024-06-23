# LU Decomposition

This repository contains a Jupyter notebook for performing LU decomposition on a randomly generated matrix. LU decomposition is a method of decomposing a matrix into the product of a lower triangular matrix and an upper triangular matrix. This notebook includes functions for LU decomposition and solving linear systems using the decomposed matrices.

## Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Functions](#functions)
- [Examples](#examples)
- [License](#license)

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/LU_Decomposition.git
    cd LU_Decomposition
    ```

2. Install the required dependencies:
    ```sh
    pip install numpy sympy
    ```

3. Open the Jupyter notebook:
    ```sh
    jupyter notebook LU_Decomp.ipynb
    ```

## Usage

The notebook `LU_Decomp.ipynb` demonstrates the process of LU decomposition on a randomly generated matrix. You can execute the cells in the notebook to see the decomposition process and the solution to linear systems using the decomposed matrices.

## Functions

- `LU_decomposition(A)`: Decomposes matrix `A` into lower triangular matrix `L` and upper triangular matrix `U`.
- `solve_system_LU(L, U, b)`: Solves the linear system `Ax = b` using matrices `L` and `U`.

## Examples

1. **LU Decomposition of a Random Matrix**:
    ```python
    import numpy as np
    from sympy import Matrix

    n = int(input("Enter dimension for the Random matrix: "))
    Random = np.random.random((n, n))
    display(Matrix(Random))

    L, U = LU_decomposition(Random)
    display(Matrix(L))
    display(Matrix(U))
    ```

2. **Solving a Linear System**:
    ```python
    n = len(L)
    B = np.eye(len(L))
    Result = np.zeros((n, n))
    for i in range(0, n):
        b = np.array(B[:, i])
        Result[:, i] = solve_system_LU(L, U, b)

    display(Matrix(Result))
    ```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.