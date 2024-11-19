# Docker, Android and Python on MacBook

Demonstration of using ADB in Docker

## Prerequisites

You must have the following installed:

- Docker Desktop
- Android Studio for emulation
- Android debug bridge (adb)

Ideally, connect an Android device and enable USB debugging. However, all
examples in this project will work without any Android devices present.

## Installing ADB on your Macbook

```
brew install android-platform-tools
```

## Install Android Studio

![Image1](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0j3tt3bwyjkro15e3yfy.png)

## List the Android devices

```
adb devices
List of devices attached
emulator-5554	device
```

## Clone the repo

```
git clone https://github.com/ajeetraina/android-adb-docker-python
```

## To Build

Execute the `build_docker_image.sh` script to build the Docker image.

```
# ./build_docker_image.sh
```

## To Run

Execute the `run_docker_container.sh` to start the docker-compose project. With the
container running, use `docker exec` to run the Python script or run the Robot
tests.

```
# ./build_docker_image.sh
```

```
# ./run_docker_container.sh
Creating network "adb-docker-demo_default" with the default driver
Creating adb-docker-demo ... done
```

```
docker exec adb-docker-demo ./python_adb_example.py
Device:
    device = <AndroidDevice mainline - emulator-5554>
    serial = EMULATOR35X2X10X0
    model = mainline
    architecture = arm64-v8a
    sdk_version = 34
    release_version = 14
```

```
# docker exec adb-docker-demo robot robot_adb_example.robot

..
Output:  /code/output.xml
Log:     /code/log.html
Report:  /code/report.html
```

