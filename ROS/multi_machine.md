## multi machine communication

Machine A and B, ros core on B 

```bash
# /etc/hosts A
192.168.1.29   A_name
127.0.1.1      A_name
192.168.1.156  B_name
```

```bash
# /etc/hosts B
192.168.1.29   A_name
127.0.1.1      B_name
192.168.1.156  B_name
```

```bash
# ~/.bashrc A
export ROS_HOSTNAME=A_name
export ROS_MASTER_URI=https://B_name:11311
```

```bash
# ~/.bashrc B
export ROS_HOSTNAME=B_name
export ROS_MASTER_URI=https://B_name:11311
```

**test**

```bash
# B terminal 1
roscore
# B terminal 2
rosrun turtlesim turtlesim_node
# A terminal 1
rosrun turtlesim turtle_teleop_key 
```



