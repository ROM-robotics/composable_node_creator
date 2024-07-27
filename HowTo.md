# composable_node_creator



## Create ROS II composable package
```
ros2 pkg create --dependencies rclcpp rclcpp_components --build-type ament_cmake your_package_name
colcon build
echo "find_package(rmw REQUIRED)" >> CMakeLists.txt
echo "find_package(rmw_implementation_cmake REQUIRED)" >> CMakeLists.txt
```


