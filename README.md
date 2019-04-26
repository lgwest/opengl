# From the course "Computer Graphics with modern OpenGL"

At www.udemy.com, modified for linux (Ubuntu 18:04) using cmake.

## Section 1 Introduction

Install the needed libraries:

 sudo apt-get install libglew2.0 libglew-dev  
 sudo apt-get install libglfw3 libglfw3-dev  
 sudo apt-get install libglm-dev  
 sudo apt-get install pkg-config 
 sudo apt-get install libasimp-dev  

And let cmake find them

#### A note about cmake find_package() 
_from so_:
CMake Find Modules (FindXyz.cmake files) are deprecated in favour of
Package Config files (usually named XyzConfig.cmake). 
Package Config files are shipped and maintained by the package they are intended to find.
See glmConfig.cmake for an example.

CMake's find_package() command has two modes: Module mode (legacy, using Find modules) 
and Config mode (preferred, using Package Config files)

