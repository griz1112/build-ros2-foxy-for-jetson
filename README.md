Build ROS2 Foxy on nvidia jetson boards.

Portions of this were reformatted from Dusty-nv's Dockerfile. 

There is a script for the jetson nano and one for the jetson AGX Xavier.

This is for building ros2 foxy desktop.

Addional packages are needed on the AGX so there is a separate script for it.

How-To

Use git to download the repo

cd into the scripts directory.
sudo ./foxy-build-board where board is nano or agx

There are a couple of times you need to interact with the script.

The resulting build will be ros_ws in your home directory.

On the nano DO NOT have any other programs running. You will run out of memory towards the end of the build and have to start over. If you do run out edit the script and in the colcon build line change the number of parallel-workers to 1. Will not build on a 2G nano.

Its a long build. Once you get past the script asking for a yes no on the PyQt5 license no further input is required.

These scripts were tested on a nano and AGX with a fresh install of the 4.5.1 SDK.
If your disk image is customized there could be issues but they are not likely.

To initialize foxy for use the command is source $HOME/ros_ws/install/setup.bash 

If you need to install additional packages just use git to put them into your ros workspace and build your package as usual. This is foxy-desktop so its fairly complete.

Enjoy
