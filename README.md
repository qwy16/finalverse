# Finalverse Viewer
In Metaverse, the Viewer is acting like the browsers to internet.
this is firestorm mirror for development for Finalverse Metaverse.

### Firestorm version:
6.6.3

## Building Finalverse, Compiling Finalverse Viewer

### 1. Linux Build
 Linux build instruction from firestorm site [[firestorm linux build]](https://wiki.firestormviewer.org/fs_compiling_firestorm_linux)
 It's still working for linux, follow the instruction should build successfully.
 
 OS Success build on:
 - Ubuntu 18.04
 
### 2. MacOS Build
 MacOS build instruction from firestorm site [[firestorm MacOS build]](https://wiki.firestormviewer.org/fs_compiling_firestorm_macos)
 It's a bit old, requires Xcode 11.7 to build MacOS in current source code.

#### 2.1 Getting development tools

#### 2.2 Set up your source code tree

 ```
 mkdir ~/fv_src
 cd ~/fv_src
 git clone https://vcs.firestormviewer.org/fs-build-variables
 git clone https://github.com/qwy16/finalverse.git
 
 export AUTOBUILD_VARIABLES_FILE=~/fv_src/fs-build-variables/variables
 
 cd ~/fv_src/finalverse
 cp autobuild.xml my_autobuild.xml
 export AUTOBUILD_CONFIG_FILE=my_autobuild.xml

 ```

#### 2.3 Configuring the Viewer
This will configure the viewer for compiling with all defaults and without third party libraries.

```
cd ~/fv_src/finalverse
autobuild configure -A 64 -c ReleaseFS_open
```
You must specify the -A 64 switch to autobuild whenever you configure or build.
This tells autobuild to build a 64-bit viewer; this is the only architecture supported on macOS.

#### 2.4 Compiling the Viewer
```
cd ~/fv_src/finalverse
autobuild build -A 64 -c ReleaseFS_open
```
Compiling may take quite a bit of time, depending on how fast your machine is and how much else you're doing.

#### 2.5 Launching the viewer
Now that the viewer has been compiled, it can be found in build-darwin-x86_64/newview/Release. Enter the following into the terminal to open Finder:
```
open build-darwin-x86_64/newview/Release
```
From here you can run it directly or copy it to the Applications folder for ease of finding and running later.