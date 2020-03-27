# State_Estimation
Implementation of an Error-State Extended Kalman Filter (ES-EKF) to localize a vehicle using data from the CARLA simulator.

## Table of contents
* [Multisensor Fusion](#multisensor-fusion)
* [Sensor Miscalibration](#sensor-miscalibration)
* [Sensor Dropout](#sensor-dropout)

## Multisensor Fusion
Sensor fusion combines the information from different sensors like cameras, IMUs, LIDAR, RADAR, GPS, etc. to estimate a single and best possible estimate of the vehicle state. To perform this, we can make use of the Extended Kalman Filter (EKF). In this case, we develop an Error State EKF for estimating position, velocity and orientation using an IMU, GNSS sensor and LIDAR.

The Error State EKF is an improved EKF that separates the state into nominal and error state where the error state is the difference between the nominal and the true state at any given time. By this way, we only need to estimate the error state and then use it as a correction to the nominal state.

The filter prediction step relies on IMU data to propagate the state forward in time, and GPS and LIDAR position updates to correct the state estimate. 
