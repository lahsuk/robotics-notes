# Installation on Windows

### Installation on windows:

Installation instructions were copied from here: [https://janbernloehr.de/2017/06/10/ros-windows](https://janbernloehr.de/2017/06/10/ros-windows)

1. Prerequisite: You need to enable WSL \(Windows Subsystem for Linux\) for this to work.
2. ```text
   sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
   sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116
   sudo apt-get update
   sudo apt-get install ros-melodic-desktop-full
   sudo rosdep init
   rosdep update
   ```

   If it gives error `gpg dirmngr IPC connect call failed` then run the following instead:

   ```text
   sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
   curl -sL "http://keyserver.ubuntu.com/pks/lookup?op=get&search=0x5523BAEEB01FA116" | sudo apt-key add
   sudo apt-get update
   sudo apt-get install ros-melodic-desktop-full
   sudo rosdep init
   rosdep update
   ```

3. If you want to source ros lunar automatically for ever bash session, then:

   ```text
   echo "source /opt/ros/lunar/setup.bash" >> ~/.bashrc
   source ~/.bashrc
   ```

4. Install the Ximg X Server after downloading from here: [https://sourceforge.net/projects/xming/](https://sourceforge.net/projects/xming/)
5. After you have installed Xming, you also need to configure WSL to use it. To do so modify you .bashrc as follows

   ```text
   echo "export DISPLAY=:0" >> ~/.bashrc
   source ~/.bashrc
   ```

### Testing the Installation

1.  Start a new bash prompt and run `roscore`
2. Start a second bash prompt
3. Create a new file `publish.py` with the contents

   ```
   #!/usr/bin/env python
   import rospy
   from std_msgs.msg import String
   
   pub = rospy.Publisher('chatter', String, queue_size=None)
   rospy.init_node('demo_pub_node')
   r = rospy.Rate(1) # 10hz
   while not rospy.is_shutdown():
      pub.publish("hello world")
      print('sending data...')
      r.sleep()
   ```

4.  Run the publisher `python publish.py`
5. Start a third bash prompt
6. Create a new file `subscribe.py` with the contents

   ```
   #!/usr/bin/env python
   import rospy
   from std_msgs.msg import String
   
   def callback(data):
       rospy.loginfo("I heard %s",data.data)
   
   def listener():
       rospy.init_node('demo_sub_node')
       rospy.Subscriber("chatter", String, callback)
       # spin() simply keeps python from exiting until this node is stopped
       rospy.spin()
   
   listener()
   ```

7. Run the subscriber `python subscribe.py`

Running all the above steps should give the following output:

![](.gitbook/assets/image%20%281%29.png)

### Testing the Installation usign Xming

1. Start a new bash prompt and run `roscore`.
2. Start a second bash prompt and run `rosrun turtlesim turtle_teleop_key`.
3. Start a third bash prompt and run `rosrun turtlesim turtlesim_node`. You can control the turtle by using the arrow keys by going back to the second prompt.

![](.gitbook/assets/image%20%282%29.png)

### Running Multiple instances of shell on the single instance

For this, you need to have `tmux` installed in your system. A good starting resouce is [https://hackernoon.com/a-gentle-introduction-to-tmux-8d784c404340](https://hackernoon.com/a-gentle-introduction-to-tmux-8d784c404340) 

If you want to delve deeper, here is another:  [https://leanpub.com/the-tao-of-tmux/read](https://leanpub.com/the-tao-of-tmux/read)

