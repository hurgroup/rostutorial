cmake_minimum_required(VERSION 2.8.3)
project(my_first_ros_pkg)
find_package(catkin REQUIRED COMPONENTS
  roscpp
  std_msgs
)
catkin_package(
 INCLUDE_DIRS include
#  LIBRARIES my_first_ros_pkg
 CATKIN_DEPENDS roscpp std_msgs
 DEPENDS system_lib
)
include_directories(
  ${catkin_INCLUDE_DIRS}
)
add_executable(my_first_ros_pkg_node src/my_first_ros_pkg_node.cpp)
add_dependencies(my_first_ros_pkg_node my_first_ros_pkg_generate_messages_cpp)
target_link_libraries(my_first_ros_pkg_node
  ${catkin_LIBRARIES}
)