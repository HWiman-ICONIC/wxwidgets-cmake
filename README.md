# wxwidgets-cmake
Some of the wxWidgets samples with CMake build files for vcpkg
## Build
### On Windows
#### With Visual Studio
- Install vcpkg by following the instructions [here](https://github.com/microsoft/vcpkg)
- Install [wxwidgets](https://www.wxwidgets.org) with command ```vcpkg install wxwidgets:x64-windows``` 
- Clone this ```wxwidgets-cmake``` repo
- Open Visual Studio, select Open Folder and browse to the ```wxwidgets-cmake``` directory
- CMake will kick in and generate build file
- Select ```Build all```
- Select a sample application in startup target pull down menu
- Select ```Debug->Start without debugging```
