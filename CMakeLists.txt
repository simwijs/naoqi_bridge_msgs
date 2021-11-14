cmake_minimum_required(VERSION 3.5)
project(naoqi_bridge_msgs)

# Default to C99
if(NOT CMAKE_C_STANDARD)
  set(CMAKE_C_STANDARD 99)
endif()

# Default to C++14
if(NOT CMAKE_CXX_STANDARD)
  set(CMAKE_CXX_STANDARD 14)
endif()

if(CMAKE_COMPILER_IS_GNUCXX OR CMAKE_CXX_COMPILER_ID MATCHES "Clang")
  add_compile_options(-Wall -Wextra -Wpedantic)
endif()

# find dependencies
find_package(ament_cmake REQUIRED)
# uncomment the following section in order to fill in
# further dependencies manually.
# find_package(<dependency> REQUIRED)
find_package(std_msgs REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(sensor_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(nav_msgs REQUIRED)
find_package(trajectory_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)
#find_package(rcutils REQUIRED)
#find_package(rosidl_typesupport_cpp REQUIRED)
#find_package(rosidl_typesupport_c REQUIRED)
#find_package(rosidl_runtime_c REQUIRED)
#find_package(rosidl_runtime_cpp REQUIRED)
#find_package(rosidl_typesupport_interface REQUIRED)

rosidl_generate_interfaces(${PROJECT_NAME}
"msg/AudioBuffer.msg"
"msg/BodyROI.msg"
"msg/BoolStamped.msg"
"msg/Bumper.msg"
"msg/EventStamped.msg"
"msg/FaceROI.msg"
"msg/FadeRGB.msg"
"msg/FloatArrayStamped.msg"
"msg/FloatStamped.msg"
"msg/HandTouch.msg"
"msg/HeadTouch.msg"
"msg/IntArrayStamped.msg"
"msg/IntStamped.msg"
"msg/JointAnglesWithSpeed.msg"
"msg/JointAngleTrajectory.msg"
"msg/MemoryList.msg"
"msg/MemoryPairFloat.msg"
"msg/MemoryPairInt.msg"
"msg/MemoryPairString.msg"
"msg/PoseWithConfidenceStamped.msg"
"msg/RobotInfo.msg"
"msg/SoundLocated.msg"
"msg/StatusChangeStamped.msg"
"msg/StringArrayStamped.msg"
"msg/StringStamped.msg"
"msg/WordRecognized.msg"
"srv/CmdPoseService.srv"
"srv/CmdVelService.srv"
"srv/GetBodyROI.srv"
"srv/GetFacesROI.srv"
"srv/GetFloat.srv"
"srv/GetInstalledBehaviors.srv"
"srv/GetRobotInfo.srv"
"srv/GetString.srv"
"srv/GetTruepose.srv"
"srv/OrthogonalSecurityDistance.srv"
"srv/SetArmsEnabled.srv"
"srv/SetFloat.srv"
"srv/SetString.srv"
"srv/SetTransform.srv"
"srv/TangentialSecurityDistance.srv"
"action/Blink.action"
"action/BodyPose.action"
"action/BodyPoseWithSpeed.action"
"action/FollowPath.action"
"action/JointAnglesWithSpeed.action"
"action/JointTrajectory.action"
"action/RunBehavior.action"
"action/SetSpeechVocabulary.action"
"action/SpeechWithFeedback.action"
  DEPENDENCIES builtin_interfaces geometry_msgs std_msgs sensor_msgs nav_msgs trajectory_msgs
)


ament_export_dependencies(rosidl_default_runtime)

if(BUILD_TESTING)
  find_package(ament_lint_auto REQUIRED)
  # the following line skips the linter which checks for copyrights
  # uncomment the line when a copyright and license is not present in all source files
  #set(ament_cmake_copyright_FOUND TRUE)
  # the following line skips cpplint (only works in a git repo)
  # uncomment the line when this package is not in a git repo
  #set(ament_cmake_cpplint_FOUND TRUE)
  ament_lint_auto_find_test_dependencies()
endif()

ament_package()
