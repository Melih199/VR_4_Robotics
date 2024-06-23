# Drone-Assisted Smart Ambulance Systems for Emergency Response Final Project
This project is developed by:
1. *Ahmet Samet Kosum - s5635830*
2. *Mustafa Melih Toslak - s5431021*
3. *Natnael Berhanu Takele - s5446838*

## Note: 
This project developed and tested computer with RTX 2060 graphic card  and on ubuntu 20.04. With few more changes it is possible to run it on ubuntu 22.04 this will be disscussed at the and of this report. 

## Aim of The Project
This project aims to simulate an emergency medical response scenario in the challenging terrain of Righi,
located in Genoa, Italy. The scenario involves a smart ambulance equipped with a drone, designed to deliver
life-saving medicines to a patient in an inaccessible area. The simulation will be developed using Unreal
Engine, Cesium, Airsim, QGroundControl, PX4, and Python APIs, ROS , D-Flight to create a realistic and
interactive environment for testing and validating the system’s capabilities.

## Used Tools for Project
### Unreal Engine 5.2.0
Unreal Engine 5 is utilized for creating a detailed and realistic simulation environment. This game engine
provides high-fidelity graphics, advanced physics simulation, and extensive support for virtual reality (VR) and
mixed reality (MR) applications.

### Cesium v2.5 with Google Maps API
The accurate representation of the Genova map within the simulation is achieved using Google API and Ce-
sium. Google API provides real-time data and mapping services, while Cesium offers detailed 3D geospatial
visualization.

### Airsim(Colosseum)
Airsim, developed by Microsoft, is an open-source simulator for drones and ground vehicles. It is used to
simulate the physical and sensor dynamics of the drone for the project. Colosseum is forked from Airsim, a
simulator for robotic, autonomous systems, built on Unreal Engine5+.

### MAVLink
MAVLink, short for Micro Air Vehicle Link, is a lightweight communication protocol designed for exchanging
information between unmanned aerial vehicles (UAVs) and ground control stations (GCS), as well as other
components like onboard computers.

### PX4 and QGroundControl
The PX4 open-source flight control software is employed for managing the drone’s flight operations. It provides
advanced flight modes and robust control algorithms. QGroundControl acts as the ground control station
software, offering a user-friendly interface for mission planning, real-time monitoring, and manual control of the
drone. This setup ensures precise and reliable drone operations in the simulated environment.

### D-Flight
D-Flight is a platform that provides essential data and services for drone operations within regulated airspaces.
It ensures compliance with aviation regulations by offering flight plan validation, real-time airspace information,
and no-fly zone enforcement.

### Spline
The ambulance navigation within the simulation is managed using Spline technology, which allows for smooth
and accurate path following along predefined routes. This ensures that the ambulance can effectively navigate
through the drivable parts of the terrain before deploying the drone for the final leg of the journey.


## Instalations on Ubuntu 20.04

### Unreal Engine 5.2.0

- Follow the 6 steps provided **Accessing Unreal Engine Source Code on GitHub** [Unreal Engine 5.2.0](https://dev.epicgames.com/documentation/en-us/unreal-engine/downloading-unreal-engine-source-code)

- ```sh 
mkdir VR
cd VR
git clone https://github.com/EpicGames/UnrealEngine.git
git checkout 5.2
```

