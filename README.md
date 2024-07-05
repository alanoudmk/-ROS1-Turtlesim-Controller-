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
- Run the following command:
  
```
$ rosrun turtlesim turtlesim_node
```


  <img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/fdad8652-51ab-4a28-8672-dc1a50751de2" width="420" height="120">

- This will start the Turtlesim node, which is the main node that controls the Turtlesim simulation

  <img src="https://github.com/alanoudmk/-ROS1-Turtlesim-Controller-/assets/127528672/cbe8634e-a4de-4812-9e72-ba9478efb858" width="200" height="200">

***

### 3.2
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



*****


##  **<mark> Improve your knowledge: <mark>**

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
