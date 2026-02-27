FROM osrf/ros:jazzy-desktop-full

# Basis Tools
RUN apt-get update && apt-get install -y \
    python3-colcon-common-extensions \
    python3-rosdep \
    ros-jazzy-rmw-cyclonedds-cpp \
    git \
    && rm -rf /var/lib/apt/lists/* 

# rosdep initialisieren
RUN rosdep init || true
RUN rosdep update

# Workspace vorbereiten
ENV ROS_WS=/workspaces/ros2_ws
RUN mkdir -p $ROS_WS/src

WORKDIR $ROS_WS

CMD ["/bin/bash"]