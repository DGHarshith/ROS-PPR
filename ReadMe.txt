#My Repo

cd ~/catkin_ws/src

git clone https://github.com/DGHarshith/ROS-PPR.git

cd ..

catkin_make

rosdep install --from-paths src --ignore-src -r -y

#Building Repo

roslaunch navbot_description gazebo.launch

roslaunch gmapping mapping.launch

rosrun teleop_twist_keyboard teleop_twist_keyboard.py

rviz

rosrun map_server map_saver -f newmap

#Verify & Navigation 

roslaunch navbot_description gazebo.launch

roslaunch navbot_navigation move_base.launch

rviz
