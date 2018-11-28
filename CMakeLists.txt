cmake_minimum_required(VERSION 2.8.3)
project(ardent_controllers_msgs)


find_package(catkin REQUIRED COMPONENTS
  actionlib_msgs
  geometry_msgs
  message_generation
  trajectory_msgs
)

add_message_files(
   DIRECTORY msg
   FILES
   JointControllerState.msg
   JointTrajectoryControllerState.msg
)
add_service_files(
   DIRECTORY srv
   FILES QueryTrajectoryState.srv
)
add_action_files(
   DIRECTORY action
   FILES
   JointTrajectory.action
   SingleJointPosition.action
)
## Generate added messages and services with any dependencies listed here
generate_messages( DEPENDENCIES trajectory_msgs std_msgs geometry_msgs
   actionlib_msgs)

catkin_package(
    CATKIN_DEPENDS actionlib_msgs trajectory_msgs geometry_msgs message_runtime
)