cmake_minimum_required(VERSION 3.5)
project(rione_msgs)

if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic -fpermissive)
endif()

find_package(ament_cmake REQUIRED)
find_package(rosidl_default_generators REQUIRED) # メッセージ生成に必要
find_package(std_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(sensor_msgs REQUIRED)

# メッセージ型定義ファイルからヘッダーファイル等を生成する
rosidl_generate_interfaces(${PROJECT_NAME}
    "msg/Command.msg"
    "msg/Location.msg"
    "msg/PredictResult.msg"
    "srv/RequestLocation.srv"
    DEPENDENCIES std_msgs geometry_msgs sensor_msgs
  )

ament_package()
