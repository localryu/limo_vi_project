## limo_vi_project
we used limo(https://github.com/johannes-graeter/limo.git)
This repository made for visual intelligent term project


# interest sources
    src/limo/keyframe_bundle_adjustment_ros_tool/src/mono_lidar/mono_lidar.cpp
    src/limo/keyframe_bundle_adjustment_ros_tool/src/mono_lidar/mono_lidar.hpp
    src/limo/keyframe_bundle_adjustment_ros_tool/src/common/general_helpers.hpp
 
# Usage
  sould be changed : 
  
    src/limo/keyframe_bundle_adjustment_ros_tool/src/mono_lidar/mono_lidar.cpp
         
  1. build :
  
    cd src/limo && bash install_repos.sh
  
  2. source update (optional):
  
    cd ~ && source ${your catkin limo dir}/devel_limo_release/setup.bash
  
  3. run rosbag : 
  
    rosbag play 04.bag -r 0.1 --pause --clock (run roscore)
  
  4. run node :
  
    roslaunch demo_keyframe_bundle_adjustment_meta kitti_standalone.launch
   -> test.txt file will be created (test.txt : estimated pose data file.)
    
# evaluation
  download (evaluate_odometry.cpp, matrix.cpp, matrix.h, mail.h, 04.txt) in limo directory
  
  required : 
  
    pdfcrop : sudo apt-get -y install texlive-extra-utils
    
    gnuplot : sudo apt-get -y install gnuplot
             
  setup : 
  
   make resulto4 directory in limo direcotry (cd src/limo && mkdir resulto4)
    
   move test.txt file in the result04 directory
   
    1. g++ -O3 -DNDEBUG -o evaluate_odometry evaluate_odometry.cpp matrix.cpp
  
    2. ./evaluate_odometry 04
   -> evaluation files will be created in the result04 directory.
