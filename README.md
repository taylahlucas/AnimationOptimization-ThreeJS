# AnimationOptimization-ThreeJS
#### 15th October 2022

A script to render 27,000 cubes as a larger cube at 60fps.

# Setup

To run the following index.html file, either open it in your browser, or use:

npm i -g serve
serve -l 1234

# Changes

- Main changes involve:
  - Using an InstancedMesh instead of Mesh since it reduces the amount of draw calls to the CPU.
  - Moving rendering functions to the end of their respective functions to ensure all scene updates have been made before performing the render.
  - Removing extra variables that are not needed since they have already been defined.
  - Using DynamicDrawUsage for the InstanceMesh since the geometry is changing frequently and the buffer attribute needs to be updated dynamically.
  - Changing Group to Object3D for faster performance.
  - Moving geometry and material initializes out of the for loop as these don't change and can be CPU intensive.
