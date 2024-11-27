cmake_minimum_required(VERSION 3.5)

project(zed_display_rviz)

## Generate symbols for IDE indexer -- 生成 compile_commands.json 文件，用于开发工具（如 VSCode 或 QtCreator）索引代码符号
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# 查找 ROS 的 catkin 包，catkin 是 ROS 中的标准构建工具，负责管理依赖、配置和编译
find_package(catkin REQUIRED)

# 声明一个 ROS 功能包
catkin_package()

# Add all files in subdirectories of the project in a dummy_target so qtcreator have access to all files -- 递归搜索当前项目目录中的所有文件，并将其列表存储在变量 extra_files 中
file(GLOB_RECURSE extra_files ${CMAKE_SOURCE_DIR}/*)
# 创建一个名为 all_files_zed_display_rviz 的虚拟目标，包含所有文件（extra_files）
add_custom_target(all_files_${PROJECT_NAME} SOURCES ${extra_files})

###############################################################################
# INSTALL

# 将项目中的 launch 文件夹安装到 ROS 的 share 目录中
install(DIRECTORY
    launch
    DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}) # DESTINATION 指定目标路径，CATKIN_PACKAGE_SHARE_DESTINATION 是 catkin 提供的标准路径变量，通常位于 install/share/<package_name>
