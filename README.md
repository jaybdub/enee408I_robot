Robot Controller
================

You need a router or phone hotspot with your computer and robot connected 
to run this setup.  The university network may not work.

Run Arduino Code
----------------

1.  Install Arduino IDE.
2.  Follow first tutorial at wiki.ros.org/rosserial_arduino/Tutorials to set up
    ROS with Arduino.
3.  Load arduino/robot_controller.ino to arduino101 board. (You may need to
    modify the motor controller code for your robot)
4.  Connect Arduino code by USB to robot computer.

Run ROS Code (On robot)
-----------------------


You need the usb_cam, web_video_server, rosbridge, and rosserial packages to run
the robot controller code.

1.  Place the robot_controller folder (located in ros folder) in your
    catkin_ws/src folder on the robot.
2.  >> cd ~/catkin_ws
3.  >> catkin_make
4.  >> source ~/catkin_ws/devel/setup.sh  (note: do this for each new terminal)
5.  new terminal-> >> roscore
6.  new terminal-> >> rosrun usb_cam usb_cam_node
7.  new terminal-> >> rosrun web_video_server web_video_server
8.  new terminal-> >> rosrun rosbridge_server rosbridge_websocket
9.  new terminal-> >> rosrun rosserial_python serial_node.py /dev/ttyACM0 (may
    need to use a different port than /dev/ttyACM0 corresponding to your
arduino)


Run HTML Client
---------------

1.  Modify the html to use your IP address in place of <ip_address>  with the ip
    address of your robot.
2.  Open the html page in your browser.  You should see the video stream and be 
able to control the robot.
