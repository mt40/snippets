# Install library

In general, the steps are on the **documentation page** of that library. The common methods to install C++ libraries on **Ubuntu / linux** is building from source. Here are the steps:

```bash
cd <path_to_source>

mkdir build

cd build

# Make sure you have `g++`, `cmake` installed
cmake ..
make

# You should use `checkinstall` because the lib can be easily removed
# later from the .deb package
sudo checkinstall --pkgname=<package_name> --pakdir=<path_to_put_package>
```

