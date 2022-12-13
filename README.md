# ros_custom_pkg
**BUILD ARDUINO CUSTOM PACKAGE FOR ESP32:**

1. cd ~/arduino/libraries/
2. git clone -b humble https://github.com/ruchi029/micro_ros_arduino.git
3. cd micro_ros_arduino/
4. docker run -it --rm -v $(pwd):/project --env MICROROS_LIBRARY_FOLDER=extras microros/micro_ros_static_library_builder:humble -p esp32
