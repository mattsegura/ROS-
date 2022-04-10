### BUILDING THE ROS PACKAGE

```
# Create our custom ROS package
cd ~/catkin_ws/src
catkin_create_pkg robotic_car std_msgs rospy roscpp

# Create our scripts folder
mkdir robotic_car/scripts
cd first_example/scripts

# Create the two node scripts
touch command_node.py
touch drive_node.py

# Make the scripts executable
chmod +x command_node.py
chmod +x drive_node.py
```
& 
``` 
# Compile the ROS package
cd ~/catkin_ws
catkin_make

# Source the workspace
echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
source ~/.bashrc

# Run in the current terminal window:
roscore

# Run in terminal window 2:
rosrun robotic_car command_node.py

# Run in terminal window 3:
rosrun robotic_car drive_node.py
```

1. in the **terminal** run... ```roscore```
  - This will start some basic nodes required for ROS to work
2. in the **terminal** run... ```rosrun first_example command_node.py```
  - This  take keyboard input to communicate with the navigation aka pwm signals by publishing 

###TESTING THE ROBOTIC CAR NODES
```
Bash commands to test the system locally

# Optional: Sometimes running node files copied from 
# elsewhere give errors because they are not executable. 
# Do the following to make sure your node files are:

# Go to your robotic car's package scripts folder
cd ~/catkin_ws/robotic_car/src/scripts

# Make the scripts executable by running:
chmod +x command_node.py
chmod +x drive_node.py
```
