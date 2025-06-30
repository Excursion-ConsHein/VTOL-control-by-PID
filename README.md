# Control VTOL fixed-wing UAV via PID
This work can be seen as my own initial practice of scientific research, 

so there is little real value in it, just a reference for other relative but more complicated work.

&nbsp;
&nbsp;
&nbsp;
&nbsp;

The target in this task is to **adjust cruising speed** and **maintain the stability of height** in the transition flight stage.

Then start to analyse motion of this UAV, 

in order to **get the variables** which can directly impact on the target above,

and **adjust the relative parameters** which can make control effect more ideal.
  
&nbsp;
&nbsp;
&nbsp;
&nbsp;

Let us focus on the fixed-wing part (because rotor part is widely known).

**The lifting force** by the fixed-wing is following:

$F_{fwt} = 0.5{C_p} \rho S{v_t}^2$

**The resistant force** by the fixed-wing is following:

$f = 0.5{C_d}{\rho}S{v_t}^2$

**The translational motion** can be shown as:

$m{\dot{v_t}} = T_t - f - mgsin{\theta}$

Then according above, make a kind of VTOL fixed-wing UAV **model** ↓ (This UAV is 2kg).

![UAV_model](./images/controller_1.png "UAV_model")

And use **one PID controller** to adjust the max cruising speed and **a cascaded PID controller** to maintain the stability of altitude.
![PID_model](./images/controller_2.png "PID_model")

The result is below.

**This is cruising speed curve**

![cruising_speed](./images/speed_curve.jpg "cruising speed")

**This is height stability curve**

![height_stability](./images/height_curve.jpg "height_stability")

However, this experiment is under quite ideal conditions.

Due to objective constraints, such as motor speed thresholds, positional distribution of paddles and fixed wings, etc., 

it is necessary to find more appropriate control policies, such as Model Predictive Control (MPC), Reinforcement Learning (RL), etc.
