# Inverse Kinematics

## Inverse Kinematics

* The opposite problem of forward kinematics

## The Workspace of the Robot

* The workspace of the robot is where its end effector can reach. 

## Example of Workspace for 2-Link Planar Robot

* it's workspace is shaped like a doughnut. 
* Case 1: Anything outside the outer boundary is unreachable. 0 solution
* Case 2: Exactly on the outer boundary, there is only one solution.
* Case 3: On its workspace \(between inner and outer boundary\), it has 2 solutions.
* Case 4: Exactly on the inner boundary, there is one solution.
* Case 5: Anything inside the inner boundary is unreachable. 0 solution.

## Inverse Kinematics + Orientation. Is it possible??

* Answer: Forget it. it's not possible. solution for 3 variables \(a, b, gamma\) with only joints \(q1 and q2\) doesn't exist. There isn't enough DOF.
* So, add one more Joint q3 and it becomes possible now.

## Extending our intuition from 2D to 3D

* 3 variables \(x, y, theta\) vs 6 variables \(x, y, z, roll, pitch, yaw\)

## The Human Arm

* 7 degrees of freedom
* 3 DOF at the shoulder, 1 DOF at the elbow and 3 DOF at the wrist.
* 7 DOF is actually redundant for a 3D manipulator.

## Degrees of Freedom in Robots

* A robot with 7 DOF is more expensive than a 6 DOF robot.
* 7 DOF is when you might have obstacles in the environment in the robot workspace.
* Most robot arms stop at 7 DOF.

