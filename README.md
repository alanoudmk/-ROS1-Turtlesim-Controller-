# Exploring the Turtlesim Package in ROS Noetic
****

## What is Turtlesim Package in ROS?

Small and simple manipulate with turtlesim package in ROS noetic.
The Turtlesim package in ROS Noetic is a simple 2D turtle simulator that serves as a great starting point for newcomers to learn the basic concepts of ROS, such as publishing and subscribing to topics, and controlling a robot.

## Prerequisites

Before we begin, ensure that you have the following:

1.  ROS Noetic installed on your system.
    - [HERE](https://github.com/alanoudmk/Install-ROS-Noetic-on-Ubuntu) is how to download it.
2.  Basic understanding of ROS concepts, such as nodes, topics, and messages.



*****

# Getting Started


### 1. Open a **Terminal**: 
   > Ctrl + Alt + T
  - OR
   > searching for **Terminal** in the application menu.



***


### 2. Start the ROS master: 
- In the **Terminal**, run the following command:

```
$ roscore
```

- This will start the ROS master, which is the central node that manages the ROS network.

<img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/d6cc02b8-0d1b-43b8-ad0a-d110eb4e8a9d" width="390" height="190">



***



### 3.1 Running the Turtlesim Node:
- Open a new **Terminal** window.
  > Ctrl + Alt + T

- To install and start the turtlesim:

    ```
    $ sudo apt-get install ros-$(rosversion -d)-turtlesim
    ```
    
- Run turtlesim:
  
    ```
    $ rosrun turtlesim turtlesim_node
    ```


  <img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/fdad8652-51ab-4a28-8672-dc1a50751de2" width="420" height="100">

- This will start the Turtlesim node, which is the main node that controls the Turtlesim simulation

  <img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/cbe8634e-a4de-4812-9e72-ba9478efb858" width="200" height="200">

***

### 3.2 ROS Qt:
- Open a new **Terminal** window.
  > Ctrl + Alt + T
- Run the following command:
  
```
$ rqt_graph
```

  <img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/74632f3d-e7b1-480e-9af3-e97f268d2d94" width="460" height="45">

- The rqt_graph tool allows you to visualize the ROS computation graph, which shows the active nodes, topics, services, and other ROS entities.

   <img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/f9fa308a-6249-4b4e-af71-34fbd8d404f2" width="200" height="180">




***



### 4. Start the Turtlesim GUI:
- Open a new **Terminal** window.
  > Ctrl + Alt + T
- Run the following command:
  
```
$ rosrun turtlesim turtle_teleop_key
```

- This will start the Turtlesim GUI and allow you to control the turtle using the keyboard.

  <img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/ade9f411-317c-4f56-80d8-b749c8cb52f1" width="350" height="150">


- Use the keyboard arrows (or WASD keys) to control the movement of the turtle within the simulation window.
    - _rosrun_: run a ROS node.
    - _turtlesim_: This is the name of the ROS package containing the Turtlesim simulation.
    - _turtle_teleop_key_: a specific node we're launching, which provides the keyboard control interface for the turtle.



  <img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/1cd56a5d-7a41-4d6f-8ad4-2b5d4b09651c" width="230" height="200">



***


###  **<mark> Improve your knowledge: <mark>**

- Open a new **Terminal** window.
  > Ctrl + Alt + T
- Run the following command:
  
```
$ rqt_graph
```

  <img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/74632f3d-e7b1-480e-9af3-e97f268d2d94" width="460" height="45">

- The resulting graph will visually represent the ROS nodes and their communication via topics, allowing you to understand the flow of data and the overall ROS system structure.


   <img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/67ba1722-d49b-4af3-9945-acf3e7f25d33" width="390" height="220">


- The `turtlesim_node` Node:
   - the main node that controls the Turtlesim simulation.

- The `turtle_teleop_key` Node:
  - the node that publishes the keyboard commands to control the turtle.

- The topic connections between the nodes:
   - The `turtle_teleop_key` node publishes to the `/turtle1/cmd_vel` topic.
   - The `turtlesim_node` subscribes to the `/turtle1/cmd_vel` topic to receive the velocity commands and update the turtle's movement.


-  <mark> This visualization is very useful for understanding the ROS architecture, debugging issues, and gaining insights into the system's behavior, especially when working with more complex ROS setups. <mark>










*****

# ROS Noetic's Turtlesim: Diverse Commands for Simulation Manipulation


### 1. Control the turtle's movement using the keyboard:
```
    $ rosrun turtlesim turtle_teleop_key
 ```
    
- The node publishes velocity commands to the /turtle1/cmd_vel topic, which the turtlesim_node subscribes to, causing the turtle to move.

***

### 2. Draw a Square:
 ```
    $ rosrun turtlesim draw_square 
```

<img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/3a4d8d93-7051-4839-9941-c7b918bbf11c" width="230" height="200">


- rosrun: a ROS command that allows you to run a specific node (a program in ROS) from the command line.
- turtlesim: name of the package that contains the draw_square node.
- draw_square: This is the name of the node that you're running, which is responsible for making the turtle draw a square.



***

### 3. Reset the Turtle:
```
    $ rosservice call /reset
```


***

### 4. Spawn a New Turtle:

 ```
    $ rosservice call /spawn 2 2 0.2 turtle2
 ```

- This command calls the /spawn service, which creates a new turtle at the specified (x, y, theta) location and with the given name.

<img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/1f1994c5-9889-4f1e-9935-dd31c2bfe92e" width="230" height="200">



***

### 5. Kill a Turtle:
 ```
    $ rosservice call /kill turtle2
 ```

- This command calls the /kill service, which removes the turtle with the specified name.

<img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/13a53dea-4ada-4ab8-8f8d-2ff8be2c8a5d" width="230" height="200">



***

### 6. Teleport the Turtle Absolutely:
 ```
    $ rosservice call /turtle1/teleport_absolute x y theta
 ```

- The x, y, and theta parameters represent the desired absolute position and orientation for the turtle.
- Ex:

```
    $ rosservice call /turtle1/teleport_absolute 2.0 3.0 1.57
```

- This command will teleport the turtle to the position (2.0, 3.0) with an orientation of 1.57 radians (approximately 90 degrees).
  
<img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/8009be1e-eead-42d3-b69d-697ee5dc868e" width="230" height="200">




***

### 7. Get the Logger Levels:
 ```
    $ rosservice call /turtlesim/get_loggers
 ```

- This command will return the current logger levels for the turtlesim node.
- Response will be a list of the logger names and their corresponding levels.
- Information can be useful for debugging and understanding the logging output of the turtlesim node.

<img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/df8538fb-2af7-44ae-97b4-fbe54df45fc8" width="230" height="200">



