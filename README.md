Assignment 1 for design of mechatronics systems
Name: Stuti Gaurav Mathur
ID: 9688

1- in terminal type:
                       cd a1
                      source /opt/ros/lyrical/setup.bash
                      source install/setup.bash
                      ros2 launch package system.launch.py

#this will open turtlesim and run action servers for GoToPose, reset and DrawSquare in a single launch file

2- in a separate terminal (while leaving the previous one running) type:
                        
                      source /opt/ros/lyrical/setup.bash
                      source install/setup.bash
                      ros2 action send_goal /go_to_pose package_interfaces/action/GoToPose "{target: {x: 8.0, y: 8.0, yaw: 1.57}}" 

#this will send the turtle to the point (8,8) and 1.57 radians 
#the coodinates can be changed with the ranges    0<x<11   0<y<11 and -3.14<yaw<3.14 (the x&y are till 11 as this is the size of the turtlesim window)

3- to reset the turtle back to the start type: 

                      ros2 service call /reset_turtle package_interfaces/srv/ResetTurtle "{}"

4-to run the draw square action type:

                      ros2 action send_goal /draw_square package_interfaces/action/DrawSquare "{side_length: 2.0}"

#this draws the square with the length of 2 
#the length can vary from 1 to 5(almost half of the window as the turtle stats from the middle) 

5-to change the speed to the turtle type:

                      ros2 service call /set_speed_limit package_interfaces/srv/SetSpeedLimit "{max_linear: 2, max_angular: 2}"

#the ranges for both linear and angular speeds are from 0.1 to 2 (0 dosen't move the turtle)

6-to play the recorded bag file type:

                      ros2 bag play ~/a1/square_test --topics /turtle1/cmd_vel --rate 1.0

#this plays the recorded DrawSquare action
#to visually see this you need to have turtlesim open on another terminal


