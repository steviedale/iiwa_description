cmake_minimum_required(VERSION 3.5.0)
project(iiwa_description)

# ROS 1
if ($ENV{ROS_VERSION} VERSION_EQUAL "1")

  find_package(catkin REQUIRED)

  catkin_package(
  #  INCLUDE_DIRS include
  #  LIBRARIES iiwa_description
  #  CATKIN_DEPENDS other_catkin_pkg
  #  DEPENDS system_lib
  )

  install(DIRECTORY launch/
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
    PATTERN ".svn" EXCLUDE)

  install(DIRECTORY meshes/
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/meshes
    PATTERN ".svn" EXCLUDE)

  install(DIRECTORY urdf/
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/urdf
    PATTERN ".svn" EXCLUDE)

# ROS 2
else()

  find_package(ament_cmake REQUIRED)

  install(DIRECTORY launch/
    DESTINATION launch
    PATTERN ".svn" EXCLUDE)
 
  install(DIRECTORY meshes/
    DESTINATION meshes
    PATTERN ".svn" EXCLUDE)
 
  install(DIRECTORY urdf/
    DESTINATION urdf
    PATTERN ".svn" EXCLUDE)

  ament_package()

endif()

