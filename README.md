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

### Airsim(Colosseum)
Airsim, developed by Microsoft, is an open-source simulator for drones and ground vehicles. It is used to
simulate the physical and sensor dynamics of the drone for the project. Colosseum is forked from Airsim, a
simulator for robotic, autonomous systems, built on Unreal Engine5+.

### Cesium v2.5 with Google Maps API
The accurate representation of the Genova map within the simulation is achieved using Google API and Ce-
sium. Google API provides real-time data and mapping services, while Cesium offers detailed 3D geospatial
visualization.

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

- Clone the UE5.2 if your internet connection is not good please install the zip file of UE5.2
```sh 
mkdir VR
cd VR
git clone https://github.com/EpicGames/UnrealEngine.git
git checkout 5.2
```
- We need to make some changes before intallation
```sh 
cd UnrealEngine-5.2.0-release/Engine/Source/Developer/DesktopPlatform/Private
gedit DesktopPlatformBase
```
- go to line 581 and change it with
```cpp
Arguments += " -Progress";
```
- You may skeep this step. To speed up the next commands you may increase the processor cores to do that first check your number of processor cores, keep few of them and use the rest ( in our case it is 12 )
```sh 
nproc
make j10
```
- Navigate the UnrealEngine-5.2.0-release folder and rund the following commands.
```sh 
./Setup.sh
./GenerateProjectFiles.sh
make
```
If you have an error while running `./Setup.sh` run it with `sudo`

- Now you should be able to run UE5.2
```sh
cd UnrealEngine-5.2.0-release/Engine/Binaries/Linux
./UnrealEditor
```

### Coleseum
- Clone the Colesseum repository
```sh
cd VR
git clone https://github.com/CodexLabsLLC/Colosseum.git
```
- We need to make same changes before installation, first open the setup.sh and change line 63 with:
```sh
sudo apt-get install -y clang-10 clang++-10 libc++-10-dev libc++abi-10-dev
```
- Open the build.sh file and change line 67,68,70,71 respectively with following:
```sh
export CC="gcc-10"
export CXX="g++-10"
export CC="clang-10"
export CXX="clang++-10"
```
- After go to Colosseum/cmake/cmake-modules then open CommonSetup.cmake and change the lines 62 and 64 respectively with the following:

```sh
set(CXX_EXP_LIB "-L${LLVM_LIBRARY_DIRS} -ferror-limit=10")
set(CXX_EXP_LIB "-fmax-errors=10 -Wnoexcept -Wstrict-null-sentinel")
```
- Go to Colosseum/ros2/src/airsim_ros_pkgs then open CMakeLists.txt and change line 37 with:
```sh
-fmax-errors=10
```

- Now we can build it
```sh
./setup.sh
./build.sh
```
If you have an error releated with clang version you can try 8 or 12 instead of 10






