# Fusion360_transforms
A usefulf script for urdf modeling with fusion360

The script "transform_fusion360.py" can be used to get the relative transforms between the links of a kinematic chain build on Fusion360.

It is a plugin that must be insert in the plugin section of Fusion360. 

# installation
In Fusion360 go in utilities -> add-in, select create and create a new python script. 
Click on modify and paste the transform_fusion360.py contents. 

The script uses scipy, so you must install it in the fusion360 environment.
You can use the accompaining install_scipy_fusion360.py script installing and running it with the same procedure of the aformentioned script. 

# Use
In the realization of a kinematic chain with fusion, you have to define links and joints between links. 

Once the kinematic chain is ready you can run the script transform_fusion360.py. As result, the script will write on the specified txt file all the relative transformations between the links.

Specifically, suppose to have the following kinematic chain:
l1 -> (j1) -> l2 -> (j2) -> l3

with li being the i-th link and ji being the i-th joint, the script will give the transformation l1_T_l2 and l2_T_l3 (the notation is parentframe_T_childframe)
NOTE: when defining the joints component1 is the child link while component2 is the parent link.

The obtained transformations can be used for urdf modelling. 
