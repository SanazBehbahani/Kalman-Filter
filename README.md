# Kalman-Filter
Simple C++ implementation of 1-D and N-D kalman filter.

## One dimensional kalman filter

### Variable Naming Conventions
* X<sub>t</sub>: state
* Z<sub>t</sub>: measurement
* U<sub>t</sub>: control action

### State Prediction

* &mu;' = &mu;<sub>1</sub> + &mu;<sub>2</sub>
* &sigma;<sup>2</sup>' = &sigma;<sup>2</sup><sub>1</sub> + &sigma;<sup>2</sup><sub>2</sub>

### Measurement Update

* &mu;' = (r<sup>2</sup>&mu; + &sigma;<sup>2</sup>&nu;) / (r<sup>2</sup> + &sigma;<sup>2</sup>)
* &sigma;<sup>2</sup>' = 1 / (1/r<sup>2</sup> + 1/&sigma;<sup>2</sup>)

## Multi dimensional kalman filter

### Variable Naming Conventions
* F: Transition function
* H: Measurement function
* Q: Process noise
* R: Measurement noise

### State Prediction
* x' = Fx
* P' = FPF<sup>T</sup> + Q

### Measurement Update
* y = Z - Hx'
* S = HP'H<sup>T</sup> + R

### Calculation of Kalman Gain
* K = P'H<sup>T</sup>S<sup>-1</sup>

### Calculation of Posterior State and Covariane
* x = x' + ky
* P = (I-KH)P'
