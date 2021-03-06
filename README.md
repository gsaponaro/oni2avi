Oni2Avi
============================

https://github.com/KirillLykov/oni2avi

Overview
--------

Oni2Avi is a command line application converting *.oni files into *.avi.
Oni data file contains images and depth obtained from Kinect. Oni files 
are supported by OpenNI library.

Command line syntax
--------------------------

The following options are available:

* --help
* --input-file
* --output-file
* --codec
* --depth-png

Input-file must be a valid *.oni file, output-file is always avi file with extension,
codec might be MPEG-1, MPEG-4, MPEG-4.2, MPEG-4.3, FLV1. The default
codec is MPEG-4.2. Option depth-png allows to save depth frames as png images instead of avi file.
The result of the program execution is two avi files for image and depth data 
or, in case of --depth-png=yes, avi file for images and a folder with *.png for depth.

Requirements & installation
--------------------------

NOTE: I checked build scripts (make/cmake) only for MacOS with homebrew, so in case if you are using different setup, 
you might need to modify path to the dependencies (in Makefile or CMakeList.txt).

The following libraries must be installed in order to build oni2avi:
* OpenNI 2.x
* OpenCV 3.x
* Boost

Paths to these libraries as well as related headers paths must be specified in the Makefile. 
Alternatively, it's possible to use CMake to build oni2avi. In case all the necessary libraries
are installed, CMake will find them automatically.

Note that I checked the code only with OpenNI 2.0, OpenCV 3, boost > 1.59, clang 3,
under MacOS >= 10.9.

Legacy version for old OpenNI and OpenCV
--------------------------
Legacy version working with  openni 1.5 and opencv3 might be found in branch legacy:
```bash
git clone git://github.com/KirillLykov/oni2avi.git
cd oni2avi
git checkout legacy
mkdir build && cd build
cmake ../
make
```

Building with CMake (Windows, Linux, Mac OS X)
--------------------------

```bash
git clone git://github.com/KirillLykov/oni2avi.git
cd oni2avi
mkdir build && cd build
cmake ../
make
```

Building with make (Linux, Mac OS X)
--------------------------

```bash
git clone git://github.com/KirillLykov/oni2avi.git
cd oni2avi
make
```
Note, that if you are using MacOS with macports, it is a recommended option. Otherwise, `cmake` should be simpler.
