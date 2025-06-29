# 3D Robotic Arm Kinematics & Trajectory Planning

This project simulates a 3-Degree-of-Freedom (3-DOF) robotic arm in 3D space using Python. It demonstrates the core principles of robotic motion, including forward and inverse kinematics using numerical optimization, and trajectory planning in a 3D environment.

<div align="center">
  <h3><a href="3d_arm_trajectory.mp4">🎥 Click Here to Watch the 3D Animation Video</a></h3>
  <em>A simulation of the arm moving from a start to an end position along a planned 3D trajectory.</em>
</div>

## Key Concepts Implemented

This simulation is built on several key robotics and mathematical concepts:

1.  **3D Homogeneous Transformation Matrices:** The foundation of the model. 4x4 matrices are used to represent both the rotation and translation of each joint and link in 3D space, allowing the entire kinematic chain to be calculated with simple matrix multiplication.

2.  **Forward Kinematics (FK):** This model calculates the `(x, y, z)` position of the arm's end-effector from a given set of joint angles (`θ1`, `θ2`, `θ3`).

3.  **Inverse Kinematics (IK) via Numerical Optimization:** This is the core of the solver. Instead of a complex analytical solution, this project uses the `scipy.optimize.minimize` function to find the required joint angles for a given target position. It works by iteratively minimizing the distance (error) between the current end-effector position and the target. This is a powerful and flexible method applicable to almost any arm configuration.

4.  **3D Trajectory Planning & Visualization:** A straight-line path is generated in 3D Cartesian space. The IK solver is then called for each point on the path to generate a smooth "choreography" of joint movements. The final result is visualized using `Matplotlib`'s 3D plotting and animation toolkits.

## Technologies Used
* Python
* NumPy (for matrix operations)
* Matplotlib (for 3D plotting and animation)
* SciPy (for the numerical optimization-based IK solver)
* Jupyter Notebook

## How to Run
1.  Clone this repository.
2.  Create a Conda environment and install the dependencies from `requirements.txt`.
3.  Launch Jupyter Notebook and open the `.ipynb` file.
4.  Run the cells sequentially to see the calculations and the final animation.
