# Unscented Kalman Filter Project

In this project, utilize an Unscented Kalman Filter to estimate the state of a moving object of interest with noisy lidar and radar measurements. Passing the project requires obtaining RMSE values that are lower that the tolerance outlined in the project rubric. 

This project uses Term 2 simulator and uWebSocketIO, to run this project, follow the steps below.

1. cd build
3. cmake .. && make
3. ./UnscentedKF
4. open simulator and choose dataset 1.

## Accuracy

* For dataset 1, the RMSE meet the requirement.
<img src="https://github.com/jane212/CarND-Term2-UKF/tree/master/output_images/Dataset1_RMSE.png" width="500">

* The lidar NIS in dataset 1 is shown below.
<img src="https://github.com/jane212/CarND-Term2-UKF/tree/master/output_images/Lidar_NIS.png" width="500">

* The radar NIS in dataset 1 is shown below.
<img src="https://github.com/jane212/CarND-Term2-UKF/tree/master/output_images/Radar_NIS.png" width="500">


## Algorithm

This program is built on the starter code provided by Udacity CarND team.

Some key modifications are listed below:

* Initialize state and covariance matrix, use 0.15 as std_px and std_py from lidar setting;
* Tune the parameter of std_a_ and std_yawdd_ as 3 and 0.4 for tracking a bike;
* Predict state with augmentation;
* Update measurement for lidar and radar; 
  * Different sigma points generation;
  * normalize any angle results to make sure it is within -pi to pi;
* Calculate RMSE;
* Calculate NIS and write to NIS_output.txt;
* Plot NIS to check the consistency.

