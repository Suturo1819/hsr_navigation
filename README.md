# navigation
The navigation repository. Containing everything navigation related that is not forked from other sources.


# Navigation Doc

### setup
#### Rviz
Launch your favorite rviz configuration for the robot. For navigation (if you want to test it via Rviz) it is important that the *tool properties* are set correctly. Right click on the toolbar in rviz, and select *tool properties*. The following window should pop up and the topics should be set accordingly. These are NOT the default topics that Rviz usually has. So if nothing is happening, check if these are set to the following: 

![](https://hackmd.informatik.uni-bremen.de/uploads/upload_8ecbe08daf21b9271d8d3d12a22e6d89.png)


#### Map Server setup
It should come with kinetic, so you only need to pull this repo for the map and do: 

    rosrun map_server map_server hsr_lab_map7.yaml

#### Snap Map ICP
Pull: https://github.com/Suturo1819/snap_map_icp and: 

    roslaunch snap_map_icp snap_map_icp.launch 
This tool is important. Otherwise the robot's assumed location will drift over time and the location within the map will get worse and worse the more the robot is moving. This tool prevents that from happening.
