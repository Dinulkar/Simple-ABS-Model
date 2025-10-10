# 🚗 Simple ABS Model Simulation

% Author: Dinesh Kumar Rajakumaran
% Date: October 10, 2025
% Description: Simple ABS model simulation towards different braking forces 
% to see the reaction of the wheel slip in the model.

Simulink Model Description

A Simulink model named ABS_SimulinkModel.slx is used to simulate the vehicle and wheel dynamics under different braking torques.

Model Components

Wheel Dynamics Block

Governing equation:

𝐽𝑅(𝜔_dot)=𝑀𝐵−𝐹𝑥𝑟R

Inputs: braking torque (M_B), tire-road friction force (F_x).

Output: wheel angular velocity (ω).

Vehicle Longitudinal Dynamics Block

Calculates vehicle deceleration from tire forces and aerodynamic drag.

Tire Model Block

Uses the slip ratio 
𝜆=𝑣−𝜔𝑟𝑅(𝑣_dot)

Computes friction coefficient 
𝜇(𝜆)based on the curve from Task 1.

Outputs the longitudinal force 
𝐹𝑥=𝜇(𝜆)𝑚𝑔
Brake Torque Input Block
Applies braking torques (M_B) sequentially to simulate different braking levels.
Scopes and Logging

Monitors:
1 Wheel slip (λ)
2 Vehicle speed (v)
3 Wheel angular speed (ω)
4 Brake torque (M_B)
5 Friction coefficient (μ)
6 Simulation Outputs

The Simulink model produces the following plots:
1 Wheel Slip vs. Time: shows how slip evolves during braking.
2 Vehicle vs. Wheel Speed: highlights when the wheel starts to lock.
3 Brake Torque Input: displays the applied torque profile.

Friction Coefficient Variation: validates tire-road interaction.

📊 Results Summary
- The slip curve verifies the nonlinear friction behavior typical of tires.
- Higher braking torques (5300 N·m and 5500 N·m) cause quicker slip growth and potential wheel lock-up.
- The optimal braking region is observed around λ ≈ 0.2.
- The simulation demonstrates how ABS prevents excessive slip by modulating torque to stay within this region.
