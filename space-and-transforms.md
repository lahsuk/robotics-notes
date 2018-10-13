# Space and Transforms

## Something that Moves in Physical Space

## Homogenous Coordinates

Combining Rotations and Translations into a single operation by simply adding a 1 to your coordinates.

## Different Perspectives - Getting Philosophical

Question: Is it me that is moving or is it the point P that is moving? kind of like - is it the flag that is moving or is it the wind that is moving?

## Rotation Representations \(All are interchangeable\)

* Rotation Matrix
* Axis - Angle -&gt; \(ax, ay, az\), alpha
* Elementary Rotations -&gt; Roll, Pitch, Yaw

  Combining Elementary Rotations to make an Rotation around an Arbitrary Axis 

  Roll, Pitch and Yaw might be a better representation than \(ax, ay, az, alpha\)

* Unit QUATERNION -&gt; \(gx, gy, gz, gw\)

## Which representation is Good?

* Rotation Matrix is good for humans to look at, whereas, Unit Quaternion is good for computers to look at.
* Unit Quaterniion is better for Numerical, Memory and Chaining Operations

## Any Rotation in Space can be specified by 3 Numbers. So it is 3 DOF

## Any Transform in Space is 6 DOF

because it combines Rotation \(3 DOF\) and translation \(3 DOF\)

