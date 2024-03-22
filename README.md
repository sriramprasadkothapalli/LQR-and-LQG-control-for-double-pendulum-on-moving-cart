# LQR and LQG controller for dual pendulum on a moving cart
ENPM 667 - Control of Robotic Systems final project

## About the Project
This is a Matlab code collection of control experiments.

- The system is a frictionless cart crane on a 1D track with mass M, actuated by external force F.
- Two loads with masses m1 and m2, and cable lengths l1 and l2, are suspended from the crane.
- Control experiments aim to regulate crane motion and loads using input force F.
- Objective: Achieve stable control of crane position and loads' dynamics.
- Challenges include coordinating crane motion, accounting for load masses and lengths, and avoiding physical constraints.
- MATLAB is used for implementing and testing various control algorithms.

## Linearization of Non-Linear system around an Equilibrium Point

This is a open loop system with M=1000Kg, m1=100, m2=100, L1 = 20m, L2=10m.
- Since the original system is non linear, At first it is linearized around the equilibrium point.

  ###                                              System animation
  ![open_loop](https://github.com/sriramprasadkothapalli/LQR-and-LQG-control-for-double-pendulum-on-moving-cart/assets/143056659/9c944dd7-fd5f-4bbd-bcf3-7b98d1e4e301)
- We find the state space representation of a Non-Linear system then Linearize it.

## Controllability 
- The obtained linearized system has to be checked for its controllability. The time-invariant 
linear state equation is controllable if and only if the n x nm controllability matrix satisfied and controllability matrix is obtained.
- The system is said to be controllable when its controllability matrix has full rank. The rank of 
the matrix can be ascertained through its determinant. A non-zero determinant indicates full 
rank, implying controllability of the system defined by the matrix.

## LQR Controller 
- For linear time invariant systems, LQR computes the state-feedback control u= −Kx that 
minimizes the quadratic cost function
- The inbuilt MATLAB function [K, S, P] = lqr(A, B, Q, R, N) computes the optimal control 
gain matrix K, along with the solution S to the corresponding algebraic Riccati equation and 
the closed-loop poles P. This is performed in the context of continuous-time state-space 
representations using matrices A and B.

 ![image](https://github.com/sriramprasadkothapalli/LQR-and-LQG-control-for-double-pendulum-on-moving-cart/assets/143056659/dea89ac8-2bed-48af-9d67-390f65df7398)

- Below figure represents  the system response after LQR Controller has been applied. Initially R is 
taken to be 0.01 and Q as identity matrix. It is observed that the system output still does not 
converge to zero.
 ![image](https://github.com/sriramprasadkothapalli/LQR-and-LQG-control-for-double-pendulum-on-moving-cart/assets/143056659/7f9bf832-89e9-4580-aa00-1664e350622e)

- We further increase the Q and decrease R = 0.001. In this case the system output reaches zero after about 300s.

  ![image](https://github.com/sriramprasadkothapalli/LQR-and-LQG-control-for-double-pendulum-on-moving-cart/assets/143056659/4dac77b2-e635-45df-83dd-ccaf2713cc26)
##                                                Non-linearized system response     
![image](https://github.com/sriramprasadkothapalli/LQR-and-LQG-control-for-double-pendulum-on-moving-cart/assets/143056659/b17d07e9-32d9-4517-b662-a362c3b80fa1)
                         
## Observability 
- The LTI system is called "observable" if the knowledge of u(t) and y(t) over some finite time interval 0 ≤ t ≤ tf 
is enough to uniquely determine x0

## Luenberger Observer 
- A Luenberger Observer, also known as a state observer or Luenberger observer, is a 
mathematical tool used in control theory to estimate the internal state variables of a 
system from the system's output. The Luenberger Observer is designed to provide an 
estimate of the unmeasured state variables by using the system dynamics and the 
available output measurements.
![image](https://github.com/sriramprasadkothapalli/LQR-and-LQG-control-for-double-pendulum-on-moving-cart/assets/143056659/a7eafc2f-1ee0-4542-ac9b-c9be44059548)


## LQG Controller 
- The Linear Quadratic Gaussian Controller is designed for LTI systems with additive 
white Gaussian noise. LQG is a combination of two main components: LQR for state 
feedback and Kalman filter for state estimation.


- LQG controller for output x(t)

  
![image](https://github.com/sriramprasadkothapalli/LQR-and-LQG-control-for-double-pendulum-on-moving-cart/assets/143056659/30c47cc1-6653-4455-bb9f-8f8caa677374)

- LQG for nonlinear system

  
![image](https://github.com/sriramprasadkothapalli/LQR-and-LQG-control-for-double-pendulum-on-moving-cart/assets/143056659/10db7343-8638-4f7e-ae7b-4c0aefafbf7c)
