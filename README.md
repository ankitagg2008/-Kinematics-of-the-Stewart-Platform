# Kinematics-of-the-Stewart-Platform

## Stewart Platform 
A Stewart platform consists of six variable length struts, or prismatic joints, supporting a payload. 
Prismatic joints operate by changing the length of the strut, usually pneumatically or hydraulically. As a 
six-degree-of-freedom robot, the Stewart platform can be placed at any point and inclination in threedimensional space that is within its reach.
Stewart platforms are known by various other names. In many applications, including in flight simulators, 
it is commonly referred to as a motion base. It is sometimes called a six-axis platform or 6-DoF 
platform because of its possible motions and, because the motions are produced by a combination of 
movements of multiple actuators, it may be referred to as a synergistic motion platform, due to the 
synergy (mutual interaction) between the way that the actuators are programmed. Because the device 
has six actuators, it is often called a hexapod (six legs) in common usage.
Project Report: Kinematics of Stewart platform
4
Project Problem Statement 
To simplify matters, the project concerns a two-dimensional version of the Stewart platform. It will model 
a manipulator composed of a triangular platform in a fixed plane controlled by three struts, as shown in 
Figure 1.14. The inner triangle represents
the planar Stewart platform whose dimensions are defined by the three lengths L1, L2, and L3. Let γ 
denote the angle across from side L1. The position of the platform is controlled by the three numbers p1, 
p2, and p3, the variable lengths of the three struts. 
Finding the position of the platform, given the three strut lengths, is called the forward, or direct, 
kinematics problem for this manipulator. Namely, the problem is to compute (x, y) and θ for each given 
p1, p2, p3. Since there are three degrees of freedom, it is natural to expect three numbers to specify the 
position. For motion planning, it is important to solve this problem as fast as possible, often in real time. 
Unfortunately, no closed-form solution of the planar Stewart platform forward kinematics problem is 
known. 
The best current methods involve reducing the geometry of Figure 1.14 to a single equation and solving 
it by using one of the solvers explained in this chapter. Your job is to complete the derivation of this 
equation and write code to carry out its solution. Simple trigonometry applied to Figure 1.14 implies the 
following three equations:
In these equations,
Project Report: Kinematics of Stewart platform
5
Note that (1.38) solves the inverse kinematics problem of the planar Stewart platform, which is to find p1, 
p2, p3, given x, y, θ. Your goal is to solve the forward problem, namely, to find x, y, θ, given p1, p2, p3. 
Multiplying out the last two equations of (1.38) and using the first yields
which can be solved for x and y as
Substituting these expressions for x and y into the first equation of (1.38), and multiplying through by D2, 
yields one equation, namely,
in the single unknown θ. (Recall that p1, p2, p3, L1, L2, L3,γ, x1, x2, y2 are known.) If the roots of f (θ) can 
be found, the corresponding x- and y- values follow immediately from (1.39). 
Note that f (θ) is a polynomial in sinθ and cos θ, so, given any root θ, there are other roots θ + 2πk that 
are equivalent for the platform. For that reason, we can restrict attention to θ in [−π,π]. It can be shown 
that f (θ) has at most six roots in that interval.
