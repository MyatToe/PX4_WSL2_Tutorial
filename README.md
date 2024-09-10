# PX4_WSL2_Tutorial
### Tutorial for PX4 by using WSL2 tools

1. Open PowerShell from Windows and select "Run as administrator."
2. Run the following command:
   ```sh
   wsl --install 
   ```
3. check wsl version: Run the command prompt in windows
    ```sh
   wsl --list --online 
   ```
![alt text](/img/versions.png "Title")
4. Need to install ubuntu version by
   ```sh
   wsl --install -d Ubuntu-20.04
   wsl -l -v 
   ```

5. Otherwise go to the Microsoft Store and search foe"Ubuntu 20.04"
   ![alt text](/img/MSstore.png "Title")

6. Search windows with ubuntu and open
   ![alt text](/img/WindowsBarUbuntu.png "Title")
7. It will comes this screen
   ![alt text](/img/Ubuntu20.04.png "Title")

### Ubuntu Part
#### Installing Required Packages and PX4 Version 1.13.2 on Ubuntu

Follow these steps to install the required packages and PX4 version 1.13.2 on Ubuntu:

1. **Update the package list:**
    ```sh
    sudo apt-get update
    sudo apt-get upgrade -y
    ```

2. **Install required dependencies:**
    ```sh
    sudo apt-get install -y git python3 python3-pip python3-venv python3-empy \
        python3-toml python3-numpy python3-yaml python3-dev python3-pyros-genmsg \
        build-essential genromfs ninja-build exiftool zip clang clang-tidy \
        libc++-dev libc++abi-dev cmake cmake-curses-gui protobuf-compiler \
        libeigen3-dev libopencv-dev
    ```

3. **Clone the PX4 repository:**
    ```sh
    sudo -s git clone -b v1.13.2 https://github.com/PX4/PX4-Autopilot.git
    cd PX4-Autopilot
    sudo bash Tools/setup/ubuntu.sh
    sudo -s reboot
    ```
 
    reboot
4. **Initialize and update submodules:**
    ```sh
    git submodule update --init --recursive
    ```
5. **Install QGC**
   https://docs.qgroundcontrol.com/master/en/qgc-user-guide/getting_started/download_and_install.html

6. **Navigate to the PX4 directory:**
    ```sh
    cd PX4-Autopilot
    sudo make px4_sitl gazebo
    ```
![alt text](/img/Gazebo.png "Title")

7. **Run PX4 with Commander:**
    ```sh
    commander takeoff
    commander land
    commander rtl
    ```
![alt text](/img/Commandar.png "Title")

8. Mission Flight
After install QGC you can create or upload the mission for SITL.
    ![alt text](/img/QGC1.png "Title")


