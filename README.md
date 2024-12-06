# Setting Up A Raspberry Pi 4 Model B For C++ Development With OpenCV Using Visual Studio Code And CMake

This guide outlines the steps involved in setting up a Raspberry Pi 4 Model B for C++ development with OpenCV using Visual Studio Code and CMake. It covers the necessary hardware, software installation, and project setup, enabling you to leverage the Raspberry Pi's capabilities for computer vision tasks.

## Hardware Used In This Guide

- (1x) [Raspberry Pi 4 Model B](https://www.adafruit.com/product/4564 "adafruit.com")
- (1x) [Official Raspberry Pi USB-C Power Supply](https://www.adafruit.com/product/4298 "adafruit.com")
- (1x) [32 GB MicroSD Card](https://www.bestbuy.com/site/sandisk-ultra-plus-32gb-microsdhc-uhs-i-memory-card/6346822.p?skuId=6346822 "bestbuy.com")
- (1x) [Micro HDMI to HDMI Cable](https://www.bestbuy.com/site/insignia-8-micro-hdmi-cable-to-hdmi-black/6392464.p?skuId=6392464 "bestbuy.com")
- (1x) [Logitech Wireless Touch Keyboard K400r with Built-In Multi-Touch Touchpad, Black](https://www.walmart.com/ip/Logitech-Wireless-Touch-Keyboard-K400-with-Built-In-Multi-Touch-Touchpad-Black/17253322 "walmart.com")
- (1x) USB Webcam

## Getting The Micro SD Card Ready

- Download and install [Raspberry Pi Imager](https://www.raspberrypi.com/software/ "raspberrypi.com").
  - Available for Windows, macOS, and Linux.
- Launch Raspberry Pi Imager.
  - Choose Raspberry Pi Device:
    - Raspberry Pi 4 Model B
  - Choose Operating System:
    - Raspberry Pi OS (64-bit)
      - A port of Debian Bookworm with the Raspberry Pi Desktop.
  - Choose Storage:
    - Carefully select the SD card drive in the Imager.
    - **Warning:** Incorrect selection can erase data on other drives.
  - Click NEXT.
  - Click EDIT SETTINGS.
  - Under GENERAL:
    - Set hostname.
    - Set username and password.
    - Configure wireless LAN.
    - Set locale settings.
  - Click SAVE then click YES.
  - Click YES again.
  - Wait for writing to finish.
  - Click FINISH.
- Close Raspberry Pi Imager.
- Remove the microSD card from your computer and insert it into the Raspberry Pi 4 Model B.

## Powering Up The Raspberry Pi

## Remove Pre-Installed Software (Optional)

- On your Pi, go to the Applications Menu -> Preferences -> Recommended Software
- Uncheck the following programs:
  - Firefox
  - Thonny
  - Sqeekboard
- Click Apply.
- Click Close.
- On your Pi, go to the Applications Menu -> Preferences -> Add / Remove Software
- Search: Geany
- Uncheck the following programs:
  - fast and lightweight IDE
  - fast and lightweight IDE - common files
- Click Apply.
- Click Ok.

## Expand the Filesystem

- Open the Terminal on your Pi.
- Type ```sudo raspi-config``` in the Terminal and press Enter.
- Go to Advanced Options and press Enter.
- Go to Expand Filesystem and press Enter.
- Go to Ok and press Enter.
- Press Tab twice to go to Finish and press Enter.
- Go to Reboot Now and press Enter.
- After Reboot, open the Terminal.
- Type ```df -h``` in the Terminal and press Enter.
- You should see that the filesystem has been expanded.
- Type ```exit``` in the Terminal and press Enter.

## Update && Upgrade

- Open the Terminal on your Pi.
- Type ```sudo apt-get update && sudo apt-get upgrade``` in the Terminal and press Enter.
- Type ```Y``` in the Terminal to continue and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install Visual Studio Code

- Open the Terminal on your Pi.
- Type ```sudo apt install code``` in the Terminal and press Enter.
- After installation finishes, type ```code``` in the Terminal and press Enter.
- Visual Studio Code should now open if installation was successful.
- Close Visual Studio Code.
- Go back to the Terminal and type ```exit``` then press Enter.

## Install G++

- Open the Terminal on your Pi.
- Type ```sudo apt install -y g++``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install GDB

- Open the Terminal on your Pi.
- Type ```sudo apt install gdb``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install CMake

- Open the Terminal on your Pi.
- Type ```sudo apt install -y build-essential cmake pkg-config``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install Make

- Open the Terminal on your Pi.
- Type ```sudo apt install -y make``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install Git

- Open the Terminal on your Pi.
- Type ```sudo apt install -y git``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install OpenCV Image Dependencies

- Open the Terminal on your Pi.
- Type ```sudo apt install -y libjpeg-dev libtiff5-dev libpng-dev``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install OpenCV Video Dependencies

- Open the Terminal on your Pi.
- Type ```sudo apt install -y libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install OpenCV GUI Dependencies

- Open the Terminal on your Pi.
- Type ```sudo apt install -y libfontconfig1-dev libcairo2-dev libgdk-pixbuf2.0-dev libpango1.0-dev libgtk2.0-dev libgtk-3-dev``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install OpenCV Matrix Operations Dependencies

- Open the Terminal on your Pi.
- Type ```sudo apt install -y libatlas-base-dev gfortran``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install OpenCV HD5 Dataset Dependencies

- Open the Terminal on your Pi.
- Type ```sudo apt install -y libhdf5-dev libhdf5-serial-dev libhdf5-103``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install OpenCV QT GUI Dependencies

- Open the Terminal on your Pi.
- Type ```sudo apt install -y libqt5gui5 libqt5webkit5 libqt5test5 python3-pyqt5``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install OpenCV Python Dependencies

- Open the Terminal on your Pi.
- Type ```sudo apt install -y python3-dev``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Install OpenCV From Source

- Go to [opencv.org/releases/](https://opencv.org/releases/ "opencv.org").
- Under the latest release click on the GitHub link.
- Click on the green Code button and copy the HTTPS URL.
- Open the Terminal on your Pi.
- Type ```git clone the_copied_url``` in the Terminal and press Enter.
- Type ```mkdir -p build && cd build``` in the Terminal and press Enter.
- Type ```cmake ../opencv``` in the Terminal and press Enter.
- Type ```make -j4``` in the Terminal and press Enter.
  - **Important:** This step can take two to three hours to complete
- Type ```sudo make install``` in the Terminal and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Update && Upgrade

- Open the Terminal on your Pi.
- Type ```sudo apt-get update && sudo apt-get upgrade``` in the Terminal and press Enter.
- Type ```Y``` in the Terminal to continue and press Enter.
- Type ```exit``` in the Terminal and press Enter.

## Check OpenCV Version Using Python

- Open the Terminal on your Pi.
- Type ```python``` in the Terminal and press Enter.
- Type ```import cv2``` in the Terminal and press Enter.
- Type ```cv2.__version__``` in the Terminal and press Enter.
- It should display the version of OpenCV installed on your Pi if the installation was successful.

## Install Visual Studio Code Extensions For C++

- Open Visual Studio Code on your Pi.
- Press Ctrl + Shift + X to open the Extensions menu.
- In the search box type ```c++``` and press Enter.
- Click the Install Button on the following extensions:
  - C/C++
  - C/C++ Extensions Pack
- The previous step should also install:
  - C/C++ Themes
  - CMake
  - CMake Tools
- Close Visual Studio Code.

## Building Your First C++ OpenCV Project In Visual Studio Code With CMake

- Open the Terminal on your Pi.
- Type ```mkdir Projects && cd Projects``` and press Enter.
- Type ```mkdir OpenCV_Webcam_Test && cd OpenCV_Webcam_Test``` and press Enter.
- Type ```code .``` and press Enter.
- Visual Studio Code should now open with the OpenCV_Webcam_Test folder as the workspace.
- Press Ctrl + Shift + P to open the command palette.
- Type ```CMake``` and in the submenu select ```CMake: Quick Start```.
- Type ```OpenCV_Webcam_Test``` for the project name and press Enter.
- Click on Create a C++ project.
- Click on Create an executable.
- Click to select both CPack and CTest and then click on Ok.
- This will finish generating the initial program files.
- Open the CMakeLists.txt file for editing.
- On the lines after ```project(OpenCV_Webcam_Test VERSION 0.1.0 LANGUAGES C CXX)``` add:

  ```cmake
  find_package(OpenCV REQUIRED)
  include_directories(${OpenCV_INCLUDE_DIRS})
  ```

- On the line after ```add_executable(OpenCV_Webcam_Test main.cpp)``` add:

  ```cmake
  target_link_libraries(OpenCV_Webcam_Test ${OpenCV_LIBS})
  ```

- The CMakeLists.txt file should look similar to this when finished:

  ```cmake
  cmake_minimum_required(VERSION 3.5.0)
  project(OpenCV_Webcam_Test VERSION 0.1.0 LANGUAGES C CXX)

  find_package(OpenCV REQUIRED)
  include_directories(${OpenCV_INCLUDE_DIRS})
  add_executable(OpenCV_Webcam_Test main.cpp)
  target_link_libraries(OpenCV_Webcam_Test ${OpenCV_LIBS})

  include(CTest)
  enable_testing()

  set(CPACK_PROJECT_NAME ${PROJECT_NAME})
  set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
  include(CPack)
  ```

- Press Ctrl + S to save the file.
- Open the main.cpp file for editing.
- Modify the file so that it looks like the following code:

  ```c++
  #include <iostream>
  #include <opencv2/opencv.hpp>

  int main(int, char**){

      std::cout << "Hello, from OpenCV_Webcam_Test!\n";

      cv::VideoCapture webcam(0);
      if (!webcam.isOpened()) {
          std::cout << "Error opening the webcam.\n";
          return -1;
      }
      cv::Mat frame;
      int key = 0;
      while (key != 27) {
          webcam >> frame;
          cv::imshow("Webcam Feed", frame);
          key = cv::waitKey(1000/30);
      }

      return 0;
  }
  ```

- Press Ctrl + S to save the file.
- Press Ctrl + ` to open the terminal inside of Visual Studio Code.
- Type ```cd build``` and press Enter.
- Type ```cmake .``` and press Enter.
- Type ```make``` and press Enter.
- Type ```./OpenCV_Webcam_Test``` and press Enter to run the program.

## Helpful Links For Putting This Guide Together

- [Installation in Linux](https://docs.opencv.org/3.4/d7/d9f/tutorial_linux_install.html "opencv.org")
- [How to Install OpenCV on a Raspberry Pi](https://www.youtube.com/watch?v=QzVYnG-WaM4 "youtube.com")
- [How to Install OpenCV on Raspberry Pi 4](https://singleboardbytes.com/647/install-opencv-raspberry-pi-4.htm "singleboardbytes.com")
- [How to Install OpenCV in C++ on Linux?](https://geeksforgeeks.org/how-to-install-opencv-in-c-on-linux/ "GeeksforGeeks.org")
