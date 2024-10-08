# Setup Documentation

## Start by cloning this repository https://github.com/PixarAnimationStudios/OpenUSD.git
## Install Visual Studio 2022 (its free)
## Preferably clone this into your desktop
# Building USD library for usage
# Update the build script with the following changes:
![image](https://github.com/user-attachments/assets/409a0681-d877-477c-953c-1a2046f48f59)


![image](https://github.com/user-attachments/assets/cf888265-9be3-476e-b80b-b5563a3ccb68)
Make the above change to the build script

![image](https://github.com/user-attachments/assets/9c2f66d9-7dd8-4616-8eed-957a9d89f46a)

## Once you have made all of these changes run the command bellow to build USD
```python .\build_scripts\build_usd.py C:\Path\to\your\OpenUSD\USD-install --no-docs --no-embree --no-python --no-debug-python --no-draco --no-prman --no-materialx --no-alembic --no-hdf5 --no-opencolorio --no-openimageio --no-usdview --no-openvdb --no-ptex --no-imaging```
### Use this command and ensure that you have installed all necessary dependencies (Python & potentially more)


# Clone down this repository (Note you will need to keep track of where you put things)
## Open the VS .sln file
## Visual Studio Setup
### Visual Studio Tracks a lot of files and will probably have some issues locating some dependencies because of file path differences between machines.
## Go to the solutions pane and right click, select properties.
## In properties scroll to C++ and then in the drop down for Language settings ensure that it is selected to C++ 17 or newer
## In **C++ > Code Generation > Runtime library** ensure that this is set to MT for multithreaded
## Go to **LINKER > Inport > Additional Dependencies** and ensure that this location matches the location of your C:\Path\to\your\OpenUSD\USD-install\libs
## Go to the Go to **C++ > General > Include directories**. Ensure that this matches C:\Path\to\your\OpenUSD\USD-install\include
## Go to the Properties > Build actions > Pre-build and update the script from ```xcopy /Y /I "C:\Users\Seth\Desktop\OpenUSD\new-try\bin\*.dll" "$(TargetDir)``` to ```xcopy /Y /I "C:\Path\to\your\OpenUSD\USD-install\bin\*.dll" "$(TargetDir)```
