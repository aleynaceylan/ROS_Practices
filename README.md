# ROS_Practices
Improvement Progress Tracking 

Part-1 / Introduction to ROS (29.03.2022)
Covered topics in this section: 
1- Creating a ROS Workspace 
2- Creating a ROS Package 
3- Running a C++ Executable in ROS 
4- Running a Python Executable in ROS 

I wanted to keep track of my progress by adding as much of my work on ROS here as possible.
Since I have just started working with ROS and can be considered a newbie in this field, I should state that I am open to any suggestions and advice.

Progress (29.03.2022)
1- Creating a ROS Workspace:

- Instead of creating a workspace in the home directory, I created a new folder called R_Practices in Desktop. My aim in doing this was to be able to practice many basic ROS works in a single workspace. I also wanted to experience being able to interfere with files with commands via terminal.

- After creating the R_Practices folder on the Desktop, I reached the location of this file via the terminal. Then I created my src folder in this folder with the 'mkdir src' command.

-After these operations, I went to the top-level workspace directory, the location of my workspace, and ran the 'catkin_make' command to build my workspace.

- After this command, the build and devel files in the workspace were created automatically.

- All source codes that I will write or access via Github will be found in the src folder.

- The Devel folder contains all the executables or libraries that will be created after the source codes are built.

- The catkin_make command ensures that all source code files in the src folder are linked, compiled, and the necessary binaries are linked to each other.

- In order not to run the setup.bash file in every new terminal, I added the location of the setup.bash file in my workspace as a line into the file after the source command.


2- Create a ROS Package:

- A ROS package in the Src file in the ROS workspace contains many different files and folders such as CMakeList.txt, package.xml, src, include, scripts, msg, srv, config, launch.

- In my further exercises, I will use src, CMakeList.txt, and scripts files to run C++ and Python files.

- I created the ROS package with the command 'catkin_create_pgk <package_name> <package_dependencies>'. I added rospy and roscpp as package dependencies since I will need these two ROS macros and methods while working on cpp and python in the exercises. After adding rospy with the command, I added the roscpp dependency with the additions I made in the package.xml file.


3- Running a C++ Executable in ROS:

- I have observed that two steps must be performed to be able to run the C++ file in ROS. First, we create an executable file for the cpp file we created with the add_executable command in CMakeList.txt.

- This file is created under the file created with the same name as our package in the lib folder under devel. Of course, in order to achieve this, we need to run the 'catkin_make' command after the changes we have made.

- We can give the Executable file any name we want. I added '_e' to the name of the cpp file, aiming to make this file easier to recognize.

- Catkin Build System is the official build system in the ROS. It is a combination of CMake, Make, and extra other features.

- This build system generates the libraries and executables from the C++ codes using commands written in the CMakeList.txt file.

- After this information and steps, I ran the c++ file I created with the rosrun command. 'rosrun <package_name> <executable_name>'


4- Running a Python Executable in ROS:

- I learned that Python files are kept in the scripts folder in ROS. Like the src file, I created a scripts file in the src folder in the package with the 'mkdir' command.

- Then I created a python file with 'touch hello_py_e.py' at the script's location. I ran the 'which python command' in the exact location, and I added the output of this command with '#!'  to the beginning of my python code.

- Then I checked whether the python file is executable with 'ls -l' in scripts. After seeing that it only has read and write permissions, I made my file executable with the 'chmod +x hello_py_e.py' command.

- Then I ran this file with the 'rosrun' command.

