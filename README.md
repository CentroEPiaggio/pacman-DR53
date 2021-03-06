# pacman-DR53

__(AKA 2nd Year Demo, Object Passing Demo)__

[![Stories in In Progress](https://badge.waffle.io/centroepiaggio/pacman-dr53.svg?label=in%20progress&title=In Progress)](http://waffle.io/centroepiaggio/pacman-dr53)

This sub-project implements the deliverable DR 5.3 of the PaCMan Project, and this document is its __declaration of intent__.

## Overview

This sub-project is powered by open-source software, and UNIPI partner decided to release it as well as open-source. It is part of the list of demos in WP5 within the project. The full list can be found [here]( https://github.com/pacman-project/pacman) (access restricted to PaCMan members).

The sub-project DR53 has a Team-Horizontal structure with 2 levels and reports to Marco Gabiccini (CN [@MarcoGabiccini](https://github.com/MarcoGabiccini)) and [Antonio Bicchi](mailto:bicchi@centropiaggio.unipi.it). Next the premises, orgaznization, development plan, technical details and information on suppliers are described.

## Premises

* Each team at all levels must have at least two members.
* Each member must be able to run the tasks of the team the member belongs to within the demo.
* At least two members per team are advised for redudnacy.
* Everyone must have access to issues, this README document, code related to the sub-project, and pull access to all sub-modules
* Not everyone has push-access to sub-modules related to the work of each team

## Organization

### Level 1: Heads 
  * Carlos Rosales (CN [@carlosjoserg](https://github.com/carlosjoserg))
  * Hamal Marino (CN [@hamalMarino](https://github.com/hamalMarino))

### Level 2: Teams

1. __HMI__
  * Alessandro Settimi (CN [@alessandrosettimi](https://github.com/alessandrosettimi))
  * ?

2. __Grasp DB (Acquisition & Data-Processing)__ 
  * Alessandro Settimi (CN [@alessandrosettimi](https://github.com/alessandrosettimi))
  * Carlos Rosales (CN [@carlosjoserg](https://github.com/carlosjoserg))

3. __Visual perception__
  * Federico Spinelli (CN [@Tabjones](https://github.com/Tabjones))
  * Emanuele Luberto (CN [@emalbt](https://github.com/emalbt))

4. __Pisa/IIT SoftHand perception__
  * Gaspare Santaera (CN [@GaspareSantaera](https://github.com/GaspareSantaera))
  * Emanuele Luberto (CN [@emalbt](https://github.com/emalbt))

5. __High-level Planning__
  * Hamal Marino (CN [@hamalMarino](https://github.com/hamalMarino))
  * Mirko Ferrati (CN [@MirkoFerrati](https://github.com/MirkoFerrati))

6. __Low-level Planning__
  * Hamal Marino (CN [@hamalMarino](https://github.com/hamalMarino))
  * ?

7. __Hardware (real/sim) and controllers__
  * Manuel Bonilla (CN [@manuelbonilla](https://github.com/manuelbonilla))
  * Enrico Corvaglia (CN [@enricocorvaglia](https://github.com/enricocorvaglia))
  * Carlos Rosales (CN [@carlosjoserg](https://github.com/carlosjoserg))

8. __State estimation and reactive controllers (?)__ (The work here heavily relies on the work of teams 3, 4, and 7)
  * Carlos Rosales (CN [@carlosjoserg](https://github.com/carlosjoserg))
  * ?
  
9. __Infrastructure and Technical Support__
  * Federico Spinelli (CN [@Tabjones](https://github.com/Tabjones))
  * Carlos Rosales (CN [@carlosjoserg](https://github.com/carlosjoserg))

## Development

Refer to the [milestones](https://github.com/CentroEPiaggio/pacman-DR53/milestones) section for the development plan, and to the [issues](https://github.com/CentroEPiaggio/pacman-DR53/issues) section for the related actions.

## Techincal

### Software

All modules should use any kind of CI support. We suggest [Travis CI](https://travis-ci.com/), which is actually used within this sub-project, since it is a meta-package that contains all pieces required to run the demo. The CI configuration file contains the instructions to install what you need. See the file here []

Most of the interface between modules is done via launch files, xacros, params, topics, services, and actions. XML-related (launch, xacros) files are advised to follow the interface/implementation paradigm, that is, use `arg`s to define the interface and do what it takes within to implement the functionality, see [here]() and [here](), for an example of a launch and a xacro file definition, respectively. Node-related stuff (params, topics, services, and actions) are advised to follow the namespacing capability in ROS, that is, if `right_hand` and `left_hand` are two devices of the same kind, with the associated topic `/joint_states` published by two IMU-gloves and by a Gazebo simulation, make your node able to publish on topics `/right_hand/imu_glove/joint_states`, `/right_hand/imu_glove/joint_states`, `/left_hand/imu_glove/joint_states` and `/left_hand/imu_glove/joint_states`.

#### Getting the software

Clone this repository recursively with the following command:

`git clone --recursive https://github.com/CentroEPiaggio/pacman-DR53.git` 

Compile it:

`roscd && cd .. && catkin_make`

Check dependencies and installation instructions on each submodule.

To continue developing follow:

1. Checkout `master` branch for submodules:
`cd pacman-DR53 && git submodule foreach git checkout master`

2. For the Vito robot, checkout the development branch for multi-robot configurations:
`cd vito-robot && git submodule foreach git checkout multi-robot-test`

### Hardware

Most of the hardware has an associated software package with instructions on how to setup the device to work with the module. Here we describe how to set the environment.

The following scheme shows the connectivity, IP addresses, and all required information to run the demo (if you don't have access to edit, issue it)
<img src="https://docs.google.com/drawings/d/1kyQeu9JCw8l99c03lb9CYwT3qcxgAatOyYYRmBtoACc/pub?w=960&amp;h=720">

## Suppliers

1. __Pisa/IIT SoftHand__ 
  * [Manuel Catalano](mailto:manuel.catalano@centropiaggio.unipi.it)
  * [QBrobotics](http://www.qbrobotics.com/)

2. __KIT mounting__ (desired, but not required for the demo)
  * [Salvatore Ballestrino](mailto:s.balestrino@centropiaggio.unipi.it)

