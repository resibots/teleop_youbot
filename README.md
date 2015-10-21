# Youbot teleoperation with a Logitech Joypad
This ROS package contains the launch file and configuration file for a logitech F710 joypad to control the YouBot base.

## Installation
You will need the official driver and ROS interface to control this robot. You can find them on the official repositories from youbot: [youbot_driver] and [youbot_driver_ros_interface]. Be carefull to use the hydro-devel branch, even if you use Jade. The other ones are not up to date, as of October 2015.

These two repositories have to be cloned in the source directory of a catkin workspace.

[youbot_driver]: https://github.com/youbot/youbot_driver
[youbot_driver_ros_interface]: https://github.com/youbot/youbot_driver_ros_interface

## Usage
Thanks to the ROS interface for YouBot, it is easy to send velocity commands to the robot on the cmd_vel topic. Also, if one uses one of our Logitech joypads, ROS has packages to make their use easy to control the robot. One can plug the USB reciever of the joypad directly on the robot. Here is how to controlling the YouBot with the Logitech joypad:

- start roscore
- activate the robot's motors (with the onboard screen-button interface) and wait a little for the control board to start
- start the ROS interface for YouBot with `roslaunch youbot_driver_ros_interface youbot_driver.launch`
- if not already done, plug the USB reciever for the joypad in one of the free USB plugs
- start the nodes taking the joypad instructions and converting them into velocity messages with `roslaunch teleop_youbot teleop_omnigrasper.launch`

Now, if you continuously press the RB button on the remote (assuming the D - X switch is on the D position), you can use the left joystick for translation and the right one for rotation of the mobile base. There is a boost mode that is not recommended for normal use but is available by continuously pressing the LT button instead of the RT.

It might be wise to switch the motor boards down once you are done with the remote control of Omnigasper.

## Authors
These two lone files were authored by Dorian Goepp.

## Licence
[CeCILL](http://www.cecill.info/index.en.html)