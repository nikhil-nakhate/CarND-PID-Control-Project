# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1(mac, linux), 3.81(Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets)
  * Run either `./install-mac.sh` or `./install-ubuntu.sh`.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x. See [this PR](https://github.com/udacity/CarND-MPC-Project/pull/3) for more details.
* Simulator. You can download these from the [project intro page](https://github.com/udacity/self-driving-car-sim/releases) in the classroom.

## Reflection
### Describe the effect each of the P, I, D components had in your implementation.
The proportional portion of the controller tries to steer the car toward the center line (against the cross-track error). If used alone, the car overshoots the central line very easily and go out of the road very quickly. This can be thought of as the inertia of the car to move along the current direction of velocity.

The integral portion tries to eliminate a possible bias in the steering system. In the case of the simulator, no bias is present and hence this component can be set to zero. (This is also in accordance with the lectures)

The differential portion helps smoothing the approach to it to the center line (with minimum CTE). This helps in providing a gradual change in the direction of the velocity so that the car doesn't overshoot.

### Describe how the final hyperparameters were chosen.
The parameters were chosen manually by trial and error. The car drove in a straight line when all the params were set to 0. Hence we could say that there is no steering bias and the integral param could stay 0. The proportional and differential values were initially set to 0.2 and  3.0 (from the lectures) and modified a little.

