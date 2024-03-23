cmake_minimum_required(VERSION 3.5)
project(designator_integration_msgs)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++17
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 17)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)

## Generate messages in the 'msg' folder
rosidl_generate_interfaces(${PROJECT_NAME}
  msg/Designator.msg
  msg/KeyValuePair.msg
  msg/DesignatorRequest.msg
  msg/DesignatorResponse.msg
  srv/DesignatorCommunication.srv
  DEPENDENCIES
  builtin_interfaces
  geometry_msgs
)

ament_package()
