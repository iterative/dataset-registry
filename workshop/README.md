## Dataset description

The dataset contains information about RSOs - artificial objects that are in orbit around earth -
used to predict orbit trajectories. 

Each row represents an orbit observation of a satellite. There are 600 satellites that have 
multiple observations. It is subdivided into three main parts:

- The **jan_train** dataset contains data on both true and simulated kinematic states of 600 satellites 
for the 24-day period of time from 01-Jan-2014 00:00 to 24-Jan-2014 23:59.

- The **jan_test** dataset contains data on only the simulated kinematic states of the same 600 satellites
 for the final 7-day period of time from 25-Jan-2014 00:00 to 30-Jan-2014 23:59.

- The **answer_key** dataset contains data on only the true kinematic states of the same 600 satellites 
for the final 7-day period of time from 25-Jan-2014 00:00 to 30-Jan-2014 23:59. 
NOTE: The answer_key should only be used for the purpose of evaluation, NOT for training.


### Features Description

- *id (integer)*: unique row identifier
- *epoch (datetime)*: datetime (at the instant of measurement) in "%Y-%m-%d %H:%M:%S.%f" format (e.g. 2014-01-27 18:28:18.284)
- *sat_id (integer)*: unique satellite identifier, ranging from 0 to 599
- *x, y, z (float)*: the true position coordinates of a satellite (km)
- *Vx, Vy, Vz (float)*: the true speeds of a satellite, measured along the respective axes (km/s)
- *x_sim, y_sim, z_sim (float)*: the simulated position coordinates of a satellite (km)
- *Vx_sim, Vy_sim, Vz_sim (float)*: the simulated speeds of a satellite, measured along the respective axes (km/s)


### Acknowledgments

Dataset published in [Kaggle](https://www.kaggle.com/datasets/idawoodjee/predict-the-positions-and-speeds-of-600-satellites) and has been collected by the Russian Astronomical Science Centre.