# ROS II Composable Node Creator
C++ ROS II composable node များကို အလိုအလျောက်ရေးပေးသော bash script များဖြစ်ပါသည်။


#### ပထမဆုံး ROS2 composable package ဖန်တီးပြီး build လုပ်ပါ။
```
# create pkg
ros2 pkg create --dependencies rclcpp rclcpp_components your_dependency --build-type ament_cmake your_pkg_name
# build
cd /go/to/workspace; colcon build --packages-select your_pkg_name
```

#### နမူနာ composable publisher node ဖန်တီးပုံ
```
# run script
./create_composable_pub_node
# copy some text for CMakeLists.txt and launch file
```

#### How to run
```
ros2 run rclcpp_components component_container_mt 
ros2 component load /ComponentManager your_pkg_name MyComposableNode
```

#### Create launch file
