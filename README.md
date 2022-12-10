# ros_custom_pkg
**BUILD ARDUINO CUSTOM PACKAGE FOR ESP32:**

1. cd ~/arduino/micro_ros_arduino-galactic/extras/library_generation/extra_packages
2. cd ros_custom_msg/
3. mkdir msg/ && cd msg/
4. create custom msg file with .msg
5. CMakeLists.txt :
    find_package(rosidl_default_generators REQUIRED)
    rosidl_generate_interfaces(${PROJECT_NAME}
      "msg/Num.msg"
     )
6. package.xml :
   <build_depend>rosidl_default_generators</build_depend>
   <exec_depend>rosidl_default_runtime</exec_depend>
   <member_of_group>rosidl_interface_packages</member_of_group>
7. cd ~/arduino/micro_ros_arduino-galactic/
8. docker pull microros/micro_ros_static_library_builder:$ROS_DISTRO
9. docker run -it --rm -v $(pwd):/project --env MICROROS_LIBRARY_FOLDER=extras microros/micro_ros_static_library_builder:galactic -p esp32
