# Motion Planning

## Motion Planning

Search of a path from start to goal through obstacles.

* Mobile Robot: direct application in task space
* Robot Arms: articulated movement in task space is turned into path through C-space.
* for mobile robots, the problem space is 2D. So, it's simpler. but for robot arms, the prbolem space can be high-dimensional. So, translating obstacle outlines from task space to C-space is hard.
* practical planning for arms: sampling-based algorithms

  2.1. based on "random" exploration of C-space

  2.2. only requires the ability to check points in C-space.

## Configuration Space

From task space to joint space

## Sample Based Motion Planning

#### When you don't know the shape of the obstacles beforehand, use the power of randomness and trees.

* only requires the ability to quickly check if a point in C-space is legal or not.
* many versions are probabilistically complete: "if a path exists, it will be found in finite time."
* ...but makes no guarantees. "in worst case, time to solution can be very long"
* in practice, these algorithms tend to be very effective in high-dimensional spaces.
* examples: RRT & PRM \(probabilistic roadmaps\)

## RRT \(Rapidly exploring Random Trees\) to go from Start S to Goal G

* Basic Idea: build a tree by creating random new points and connect the new point to the closest point in the tree \(but the length is only of some fixed length in the direction of new point\). If there is an obstacle, extend the line only till it almost reaches obstacle. Continue until a connection to the goal G is found.
* Step 2: Eliminate Zig Zags. After the tree connects start S and goal G, connect points that can be connected from S to G to get a straighter path.

## PRM \(probabilistic RoadMaps\)

* Similar to RRT. But, instead of closest point, the new random point is connected fully by lines to all points in the graph \(roadmap\) if there are not obstacles between. Continue for a certain number of points are added to roadmap.
* After the roadmap is made, connect the start S to closest point in roadmap
* Connect the goal G to closest point in roadmap.
* Use the roadmap to get from S to G.

## DEMO \(Baxter from ReThink Robotics\)

* Get MoveIt to simulate motion planning robot arms in ROS.

### Final Project: Implement Rapidly-exploring Random Trees \(RRT\)

