# syntax = docker/dockerfile:1.3

ARG ROS_DISTRO=rolling

######################### Tutorial Image  #################################################

FROM moveit/moveit2:${ROS_DISTRO}-source as tutorial_image

LABEL org.opencontainers.image.description "This container has working versions of the tutorials discussed here: https://moveit.picknik.ai/main/doc/tutorials/tutorials.html"

# Copy MoveIt sources from docker context
COPY . src/moveit2_tutorials

# Commands are combined in single RUN statement with "apt/lists" folder removal to reduce image size
# https://docs.docker.com/develop/develop-images/dockerfile_best-practices/#minimize-the-number-of-layers
RUN --mount=type=cache,target=/root/.ccache/ \
    # Fetch required upstream sources for building
    vcs import src < /root/ws_moveit/src/moveit2_tutorials/.github/upstream.repos

RUN cat /root/ws_moveit/src/moveit2_tutorials/.github/upstream.repos
