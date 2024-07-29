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
```
from launch import LaunchDescription
from launch_ros.actions import ComposableNodeContainer
from launch_ros.descriptions import ComposableNode
def generate_launch_description():
    container = ComposableNodeContainer(
            name='my_container',
            namespace='',
            package='rclcpp_components',
            composable_node_descriptions=[
                ComposableNode(
                    package='your_pkg_name',
                    plugin='$class_name',
                    name='as_you_like'),
            ],"
            output='screen',
    )
    return LaunchDescription([container])
```

## ROS 1 အတွက် 
ဒီ [link](https://gitlab.com/robot-ros1/ros_nodelet_creator) ကို သွားပါ။