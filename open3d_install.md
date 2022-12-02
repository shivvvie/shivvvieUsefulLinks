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
