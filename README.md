# PINN for Solving a 1D Eigenvalue Problem

This project implements a **Physics-Informed Neural Network (PINN)** to solve a 1D second-order differential **eigenvalue problem** of the form:

d²ψ/dx² + (2π/L)² * ψ = 0, with ψ(0) = ψ(L) = 0

The exact analytical solution is:  
ψ(x) = sin(2πx / L)

## 🔍 What this project does

- Approximates the eigenfunction using a fully connected neural network.
- Enforces:
  - **Dirichlet boundary conditions**:  ψ(0) = ψ(L) = 0
  - **Physics-based loss** via the differential equation residual
  - **Normalization**:∫ ψ² dx = 1
- Trains using PyTorch and visualizes both the **exact** and **predicted** wavefunctions during training.

> Note: The network may converge to either +ψ(x) or -ψ(x) as both satisfy the same equation and constraints. This is expected and physically valid.


## 📈 Output

The script displays a comparison between the learned solution and the exact analytical solution during training. Here’s an example:

![image](https://github.com/user-attachments/assets/e8d8bdc4-b91a-4eb9-a321-82a269ee1ef6)

