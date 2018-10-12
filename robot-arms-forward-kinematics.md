## Kinematic Chains ##
- Simply collection of links and joints
- Different values of the joints mean that the robot is moving in space
- Transforms associated with links never change, whereas, Transforms associated with joints change with the joint values.

## Definition of Forward Kinematics: The Task of computing the pose of all links (including end effector) given the joint angles. ###

## URDF vs DH Notation ##
- URDF is used in ROS and research, whereas, DH is used in industries.

## DH Notation ##
- meant to be compact way to describe robot
- Joint Axis is always Local Z. (that is, Axis for J(i) is Z(i-1) )
- L(i) can be translation along X(i) or rotation around X(i)
- Uses 4 numbers: theta, d, a, alpha
- Rotation around Z, Translation along Z, Translation along X, Rotation X

### Goal of DH: ###
- A nice analytical formulation for the forward kinematics for a particular robot.

## DH Notation Example 1 - 2 Link Planar Robot ##
https://www.youtube.com/watch?v=Ss2v-dr_yWU

## DH Notation Example 2 - SCARA Robot ##
https://www.youtube.com/watch?v=vKD20BTkXhk
### Rules ###
-  If the transform has TRANSLATION first and then ROTATION, then you can concatenate the transform.

## DH Notation Example 3 - 6 DOF and 7 DOF Robots ##
- All revolute joints and no prismatic joints
- Very common in Industrial Robots
- Simulation of 6 DOF Visualizer - GraspIT

### Question: Why is 6 DOF a very common configuration? ###

## Coding Challenge Forward Kinematics (by Daniel Shiffman) ##
https://www.youtube.com/watch?v=xXjRlEr7AGk&t=202s
