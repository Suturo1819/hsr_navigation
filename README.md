# navigation
The navigation repository. Containing everything navigation related that is not forked from other sources.


# Navigation Doc

### setup
The following will explain what needs to be set up in order to localize the robot. This order of the steps should be maintained, since it workd out best this way. 

#### Map Server setup
It should come with kinetic, so you only need to pull this repo for the map and do: 

    rosrun map_server map_server hsr_lab_map7.yaml

#### Snap Map ICP
Pull: https://github.com/Suturo1819/snap_map_icp and: 

    roslaunch snap_map_icp snap_map_icp.launch 
    
This tool is important. Otherwise the robot's assumed location will drift over time and the location within the map will get worse and worse the more the robot is moving. This tool prevents that from happening.

#### Rviz
Launch your favorite rviz configuration for the robot. For navigation (if you want to test it via Rviz) it is important that the *tool properties* are set correctly. Right click on the toolbar in rviz, and select *tool properties*. The following window should pop up and the topics should be set accordingly. These are NOT the default topics that Rviz usually has. So if nothing is happening, check if these are set to the following: 

![](https://hackmd.informatik.uni-bremen.de/uploads/upload_8ecbe08daf21b9271d8d3d12a22e6d89.png)

Click the *2D Pose Estimate* button in the upper toolbar in Rviz and click and drag on the map in rviz to set the robots location. If you do that after launching snap_map_icp, the localization will work  better, since it will help to rotate the robot into the right configuration in rviz and snap the laser scan to the walls of the map the robot currently sees. 
