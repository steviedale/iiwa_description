cmake_minimum_required(VERSION 3.5.0)
project(iiwa_description)

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
