# ROS2_Docker_Template
```
Docker template for ROS2 development with colcon workspace.

Even GUI applications can be run by help of xLaunch to connect host display to the container

For easier development '~/ros2_ws/src/' folder volume is mapped to the 'src' folder in the template.

Open the 'src' folder in the template with your favourite IDE and start developing right away once you start the docker container. 
```
## Table of Contents

- For Linux
- For Windows


## For Linux
### Introduction

'Linux' folder contains the docker template configured for linux.

### Prerequisites

Following need to be installed before start developments:

- Docker

## Instructions

1. Clone this repository
2. Navigate to docker folder, 
    - on Windows, Use a terminal and navigate to 'Windows/docker/' folder
    - on Linux, Use a terminal and navigate to 'Linux/docker/' folder
3. Use the following command run the script that build the image and start a container. This will build the image and start a container. 
    Also will enable x11 forwarding so that container can access the display for GUI apps

    ` ./ros2_linux.sh up `

4. Use docker commands or GUI to open a terminal for the container.

    ` docker exec -it <container_id or name> bash `

5. You can now develop using using an IDE to edit files in the 'src' folder and use terminals to run applications. 

6. To stop the container use the following command. This will stop x11 forward that used to access display

    ` ./ros2_linux.sh down`



## For Windows
### Introduction

'Windows' folder contains the docker template configured for windows.

### Prerequisites

Following need to be installed before start developments:

- Docker
- VcXsrv (https://sourceforge.net/projects/vcxsrv/) : To let docker container access the display for GUI applications


## Instructions

1. Clone this repository
2. Configure the VcXsrv as below:
    - Multiple Windows
    - Display Number : 0
    - Start no client
    - Keep other settings as default
3. Navigate to docker folder, 
    - on Windows, Use a terminal and navigate to 'Windows/docker/' folder
    - on Linux, Use a terminal and navigate to 'Linux/docker/' folder
4. Use the following command to build the image and start a container

    ` docker-compose up --build -d `

5. Use docker commands or GUI to open a terminal for the container.

    ` docker exec -it <container_id or name> bash `

6. You can now develop using using an IDE to edit files in the 'src' folder and use terminals to run applications. 

7. To stop the container use the following command.

    ` docker-compose down`

Note that all docker commands should be run after navigating to docker folder which contains the yml file.



# Special Note
```
If using an editor inside windows to change files in src folder of the container,
 make sure to use END OF LINE SEQUENCE as 'LF' so that it uses unix system ending.
or configure endofline to '\n' instead of '\r'.
or else you can use dos2unix convertor inside the container to convert the file too.
```
` Doing this once is enough since, editor will recognize the End of Line Sequence and use it in the future for that specific file`



