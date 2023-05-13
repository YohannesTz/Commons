# OpenCV C++ Installation with CMake
Just going to put this here so I don't suffer in the future.😜 the link to an answer
that seems to work is [here](https://stackoverflow.com/a/65738297)

# Step 1 - update everything and install libgtk, pkg-condfig
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install libgtk2.0-dev pkg-config
```
# Step 2 - then cmake and g++ (if you haven't already)
```
sudo apt install -y g++
sudo apt-get install cmake make
```
# Step 3 - then clone opencv and opencv_contrib
```
git clone https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git
```
# Sept 4 - return to home and create build directory
```
cd ~
mkdir -p build && cd build
```
# Step 5 - Configure - generate build scripts for the preferred build system
replace the first "../opencv_contrib/modules" with the absolute location for opencv_contrib you cloned earlier 
optionally you can change the second one with ablosute location for open_cv if you cloned it in another place
```
cmake -DOPENCV_EXTRA_MODULES_PATH=../opencv_contrib/modules ../opencv
```
# Step 6 -  Build - run actual compilation process. 4 is number of used processor cores. this part may takes some minutes.
for me just ```make``` worked for me. but the answer says you can sepcify cores with "-j4"
```
make -j4
```
# Step 7 - Installation process copies files to predefined locations and do minor patching:
```
sudo make install
```

# To uninstall
```
sudo make uninstall
```
# Adding to a project 
Create a CMake file. the name of the source code is DisplayImage.cpp for example:
```
cmake_minimum_required(VERSION 2.8)
project( DisplayImage )
find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )
add_executable( DisplayImage DisplayImage.cpp )
target_link_libraries( DisplayImage ${OpenCV_LIBS} )
```
# Generate the executable. This part is easy, just proceed as with any other project using CMake:
```
cd <Project_Dir>
cmake .
make
```
# run executable file:
```
./DisplayImage
```
