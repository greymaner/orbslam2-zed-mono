对orbslam2重载地图和重定位的再修改     
1.修改了重载地图时候，keyframe会指向空指针的逻辑问题。    
2.新添了zed双目的代码。     
3.后期可能会和加入飞控通讯代码。    

requirements   
1.pangolin  
2.opencv  
3.eigen3  
4.DBoW2 and g2o(included in Thirdparty folder)  
5.ROS  
6.usb_cam or zed_wrapper  
                         
installation   
1.git clone https://github.com/greymaner/orbslam2-zed-mono.git  
cd orbslam2-zed-mono   
chmod +x build.sh   
./build.sh    
             
2.在ros/ORB_SLAM2下   
mkdir build      
cd build        
cmake ..      
make      

3.在ros的workspace 下运行Zed 或者Mono（详细操作请百度）
 Zed : roslaunch zed_wrapper zed.launch   
(在ros/ORB_SLAM2文件夹下） rosrun ORB_SLAM2 Zed ORBvoc.bin zed.yaml 0   
(重载地图）rosrun ORB_SLAM2 Zed ORBvoc.bin zed.yaml true    
ps : 记得修改Slam_latest_Map.bin的名称为Slam_Map.bin    
     
Mono: roslaunch usb_cam usb_cam-test.launch   
      rosrun ROB_SLAM2 Mono ORBvoc.bin (相机文件）0   
      rosrun ROB_SLAM2 Mono ORBvoc.bin (相机文件）true   
ps:同理   
