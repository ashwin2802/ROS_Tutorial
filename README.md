# ROS_Tutorial
A simple ROS package to find the centre of a box, aimed as a tutorial for beginners.

Covers most of the basic stuff:
- [Writing a ROS Node](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28c%2B%2B%29)
- [Using ROS Parameters](http://wiki.ros.org/ROS/Tutorials/UnderstandingServicesParams)
- [Creating launch files](http://wiki.ros.org/ROS/Tutorials/UsingRqtconsoleRoslaunch)
- [Using Custom Messages](http://wiki.ros.org/ROS/Tutorials/CreatingMsgAndSrv)
- [Linking with OpenCV](http://wiki.ros.org/cv_bridge/Tutorials/UsingCvBridgeToConvertBetweenROSImagesAndOpenCVImages)

# Installation and Usage

Firstly, install and setup ROS Melodic for Ubuntu 18.04 using the [official installation guide](http://wiki.ros.org/Installation/Ubuntu).

Install the catkin build system using Python:
```bash
sudo apt-get install python-catkin-tools
```

Create and initialize a catkin workspace if you don't have an existing one:
```bash
mkdir -p ~/tutorial_ws/src
cd ~/tutorial_ws
catkin init
```

Clone this repository into the `src` folder of your workspace:
```bash
cd ~/tutorial_ws/src
git clone https://github.com/ashwin2802/ROS_Tutorial.git
git clone https://github.com/catkin/catkin_simple.git
```
[catkin_simple](https://github.com/catkin/catkin_simple.git) is an external dependency that allows for writing a much simpler `CMakeLists.txt`.

Build the package by executing ```catkin build centre_detector``` *inside* your workspace.

Once you have built your package, you'll have to *source* the workspace. This has to be done in every new terminal

```bash
source ~/tutorial_ws/devel/setup.bash
```
Alternatively, you could add the above line into your `~/.bashrc` file.

Launch the detector node using:
```bash
roslaunch centre_detector default.launch
```

After which you can view the images using `rqt_image_view` in a separate terminal.
