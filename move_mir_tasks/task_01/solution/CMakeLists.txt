#This CMakeLists.txt is for the C++ Solution

cmake_minimum_required(VERSION 3.0.2)

project(solution_node1)

find_package(catkin REQUIRED COMPONENTS
  roscpp std_msgs nav_msgs geometry_msgs
)

generate_messages(
   DEPENDENCIES
   nav_msgs
   geometry_msgs
 )
 
catkin_package()

include_directories(
  ${catkin_INCLUDE_DIRS}
)

add_executable(${PROJECT_NAME}_node solution_01.cpp)

add_dependencies(${PROJECT_NAME}_node ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})

target_link_libraries(${PROJECT_NAME}_node
  ${catkin_LIBRARIES}
)
