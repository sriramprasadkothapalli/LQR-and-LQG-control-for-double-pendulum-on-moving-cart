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


