# Windows
Open3D should just be cloned from git and built according to the instructions given. This doesn't appear to work.

Firstly, you want cmake on the PowerShell command line. Don't bother with Cmake.exe + VS2019, it just doesn't work with Release for some reason.

Follow this:
```
git clone https://github.com/isl-org/Open3D
mkdir build
cd build
cmake .. -DCMAKE_INSTALL_PREFIX=C:\open3d_install // Configure step
cmake --build . --config Release --parallel 12 // Build step
cmake --install .
```
Test using: https://github.com/isl-org/open3d-cmake-find-package

This should be green if the package is found.

# Ubuntu 18.04
Install CMAKE from app centre

Install Open3d:
 - http://www.open3d.org/docs/release/compilation.html

Install Boost:
	```
  sudo apt-get install libboost-all-dev
  ```

Install Eigen3:
	```
  sudo apt install libeigen3-dev
  ```

Install OpenCV:
	```
  sudo apt install python3-opencv libopencv-dev
  ```
	OR 
	```install opencv 3.3.1 zip
	install using cmake + sudo make
  ```
	
	
Install dependencies using Linux dependencies in the SDK
Follow instructions in the readme

If it can't find 3.3 libraries, do the following:
```
	export LD_LIBRARY_PATH=/usr/local/lib
	vi ~/.bash_profile, and add export LD_LIBRARY_PATH=/usr/local/lib
	sudo sh -c 'echo "/usr/local/lib" > /etc/ld.so.conf.d/opencv.conf'
	sudo ldconfig
  ```

	
If cmake can't find python3:
```
sudo apt-get install python3.8 python3.8-dev python3.8-distutils python3.8-venv
```
