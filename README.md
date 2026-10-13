# 1. Project Overview

This project investigates how **Polynomial Chaos Expansion (PCE)** can be used to model uncertainty in the solution of the one-dimensional inviscid Burgers' equation.

The inviscid Burgers' equation is a nonlinear partial differential equation (PDE) that serves as a simplified model for fluid dynamics:

\[
\frac{\partial u}{\partial t}
+u\frac{\partial u}{\partial x}=0.
\]

Here, \(u(x,t)\) represents the solution/velocity at position \(x\) and time \(t\).

Because the initial condition is unknown, this project introduces uncertainty through a random variable:

\[
u(x,0;\xi)=\xi\sin(x),
\qquad \xi\sim\mathcal{N}(0,1).
\]

The goal is to approximate the solution by using a finite Polynomial Chaos Expansion to derive a coupled system of deterministic PDEs, and numerically solve the resulting equations for different truncation orders (called M).


# 2. Project Structure

```text
project/
├── main.ipynb                  # Main file for running tests and experiments
├── burgers_helper.ipynb        # Burgers equation and related functions
├── helper_function.ipynb       # Numerical helper functions
├── README.md                # Project documentation
└── ...                      # Other source files, plots, and outputs
```

## File descriptions

| File | Purpose |
|---|---|
| `main.ipynb` | Defines parameters and initial conditions required to run tests and experiments, calls the solver functions, and produces results. |
| `burgers_helper.ipynb` | Contains functions related to the Inviscid Burgers' equation. |
| `helper_function.ipynb` | Contains reusable numerical helper functions, such as derivatives calculation, inner products calculation, and function assigning given initial condition for a PDE. |

# 3. Function Reference

This section documents each function's purpose, arguments, and return value.
## 3.1 `burgers_helper.ipynb`
### 3.1.1 `GeneralBurgHierachy(...)`

**Purpose:** Computes the right-hand side of the truncated Burgers' PCE coefficient system.

This function handles different truncation orders and may support a recursive mode in which lower-order coefficients are taken from a previously computed solution while the highest-order coefficient is evolved separately.

**Inputs:**

- `u`: Array containing the PCE coefficient values on the spatial grid.
- `t`: Current time.
- `delta_x`: Spatial grid spacing.
- `M`: PCE truncation order.
- `N`: Number of spatial grid points.
- `u_from_lower`: Optional previously computed lower-order solution, if supported by the selected mode.
- `t_grid`: Optional time grid used for matching the lower-order solution, if supported.

**Output:** The time derivative of the coefficient array, in the format required by the time-integration method.


### 3.1.2 `BurgersKEqualsZeroEqn(...)`

**Purpose:** Solves or evaluates the zeroth coefficient equation, corresponding to \(M=0\), if this is how the function is implemented.

**Inputs and outputs:** Document the actual function signature and return value from the source code.

### 3.1.3 `BurgersKEqualsOneEqn(...)`
**Purpose:**
**Inputs and outputs:**

### 3.1.4 `BurgersKEqualsTwoEqn(...)`
**Purpose:**
**Inputs and outputs:**

## 3.2 `helper_function.ipynb`
### 3.2.1 `double_prod(...)`

### 3.2.2 `triple_prod(...)`

### 3.2.3 `xderiv_central(...)`

### 3.2.4 'getallxderiv(...)`

### 3.2.5 `getinitcond(...)`


# 4. Installation and Requirements

- Python 3
- NumPy
- SciPy
- Matplotlib



# 5. Results 

[TO BE FILLED]

