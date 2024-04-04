# Setting up Tesseract in a Windows environment

1. Install [vcpkg](https://github.com/microsoft/vcpkg) 
   - See the README for detailed installation instructions
   - Make sure you do “vcpkg integrate install” to make the installed libraries from anywhere
2. Add the path to the vcpkg install directory to PATH for access from anywhere (setting up the vcpkg .json’s for the process)
3. Install [Leptonica](https://github.com/DanBloomberg/leptonica) (Tesseract dependency) w/ vcpkg
   - not required as vcpkg seems to install its dependencies by itself
4. Install Tesseract using vcpkg
   - Command: vcpkg install tesseract
5. See Tesseract guide for more info


## Resources

*1 [Barebones project to ensure vcpkg is installed and recongnized by CMakeTools](https://learn.microsoft.com/en-us/vcpkg/get_started/get-started?pivots=shell-cmd)

*1: Using an environment variable in the path for CMAKE_TOOLCHAIN_FILE **does not work** on my setup. If you are experiencing the same issue, use the full path instead.

