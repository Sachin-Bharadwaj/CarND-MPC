# CarND-Controls-MPC
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
  * Run either `install-mac.sh` or `install-ubuntu.sh`.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x. See [this PR](https://github.com/udacity/CarND-MPC-Project/pull/3) for more details.
* Fortran Compiler
  * Mac: `brew install gcc` (might not be required)
  * Linux: `sudo apt-get install gfortran`. Additionall you have also have to install gcc and g++, `sudo apt-get install gcc g++`. Look in [this Dockerfile](https://github.com/udacity/CarND-MPC-Quizzes/blob/master/Dockerfile) for more info.
* [Ipopt](https://projects.coin-or.org/Ipopt)
  * If challenges to installation are encountered (install script fails).  Please review this thread for tips on installing Ipopt.
  * Mac: `brew install ipopt`
       +  Some Mac users have experienced the following error:
       ```
       Listening to port 4567
       Connected!!!
       mpc(4561,0x7ffff1eed3c0) malloc: *** error for object 0x7f911e007600: incorrect checksum for freed object
       - object was probably modified after being freed.
       *** set a breakpoint in malloc_error_break to debug
       ```
       This error has been resolved by updrading ipopt with
       ```brew upgrade ipopt --with-openblas```
       per this [forum post](https://discussions.udacity.com/t/incorrect-checksum-for-freed-object/313433/19).
  * Linux
    * You will need a version of Ipopt 3.12.1 or higher. The version available through `apt-get` is 3.11.x. If you can get that version to work great but if not there's a script `install_ipopt.sh` that will install Ipopt. You just need to download the source from the Ipopt [releases page](https://www.coin-or.org/download/source/Ipopt/).
    * Then call `install_ipopt.sh` with the source directory as the first argument, ex: `sudo bash install_ipopt.sh Ipopt-3.12.1`. 
  * Windows: TODO. If you can use the Linux subsystem and follow the Linux instructions.
* [CppAD](https://www.coin-or.org/CppAD/)
  * Mac: `brew install cppad`
  * Linux `sudo apt-get install cppad` or equivalent.
  * Windows: TODO. If you can use the Linux subsystem and follow the Linux instructions.
* [Eigen](http://eigen.tuxfamily.org/index.php?title=Main_Page). This is already part of the repo so you shouldn't have to worry about it.
* Simulator. You can download these from the [releases tab](https://github.com/udacity/self-driving-car-sim/releases).
* Not a dependency but read the [DATA.md](./DATA.md) for a description of the data sent back from the simulator.


## Basic Build Instructions


1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./mpc`.

## Tips

1. It's recommended to test the MPC on basic examples to see if your implementation behaves as desired. One possible example
is the vehicle starting offset of a straight line (reference). If the MPC implementation is correct, after some number of timesteps
(not too many) it should find and track the reference line.
2. The `lake_track_waypoints.csv` file has the waypoints of the lake track. You could use this to fit polynomials and points and see of how well your model tracks curve. NOTE: This file might be not completely in sync with the simulator so your solution should NOT depend on it.
3. For visualization this C++ [matplotlib wrapper](https://github.com/lava/matplotlib-cpp) could be helpful.)
4.  Tips for setting up your environment are available [here](https://classroom.udacity.com/nanodegrees/nd013/parts/40f38239-66b6-46ec-ae68-03afd8a601c8/modules/0949fca6-b379-42af-a919-ee50aa304e6a/lessons/f758c44c-5e40-4e01-93b5-1a82aa4e044f/concepts/23d376c7-0195-4276-bdf0-e02f1f3c665d)

## Editor Settings

We've purposefully kept editor configuration files out of this repo in order to
keep it as simple and environment agnostic as possible. However, we recommend
using the following settings:

* indent using spaces
* set tab width to 2 spaces (keeps the matrices in source code aligned)

## Code Style

Please (do your best to) stick to [Google's C++ style guide](https://google.github.io/styleguide/cppguide.html).

## Project Instructions and Rubric

Note: regardless of the changes you make, your project must be buildable using
cmake and make!

More information is only accessible by people who are already enrolled in Term 2
of CarND. If you are enrolled, see [the project page](https://classroom.udacity.com/nanodegrees/nd013/parts/40f38239-66b6-46ec-ae68-03afd8a601c8/modules/f1820894-8322-4bb3-81aa-b26b3c6dcbaf/lessons/b1ff3be0-c904-438e-aad3-2b5379f0e0c3/concepts/1a2255a0-e23c-44cf-8d41-39b8a3c8264a)
for instructions and the project rubric.

## Hints!

* You don't have to follow this directory structure, but if you do, your work
  will span all of the .cpp files here. Keep an eye out for TODOs.

## Call for IDE Profiles Pull Requests

Help your fellow students!

We decided to create Makefiles with cmake to keep this project as platform
agnostic as possible. Similarly, we omitted IDE profiles in order to we ensure
that students don't feel pressured to use one IDE or another.

However! I'd love to help people get up and running with their IDEs of choice.
If you've created a profile for an IDE that you think other students would
appreciate, we'd love to have you add the requisite profile files and
instructions to ide_profiles/. For example if you wanted to add a VS Code
profile, you'd add:

* /ide_profiles/vscode/.vscode
* /ide_profiles/vscode/README.md

The README should explain what the profile does, how to take advantage of it,
and how to install it.

Frankly, I've never been involved in a project with multiple IDE profiles
before. I believe the best way to handle this would be to keep them out of the
repo root to avoid clutter. My expectation is that most profiles will include
instructions to copy files to a new location to get picked up by the IDE, but
that's just a guess.

One last note here: regardless of the IDE used, every submitted project must
still be compilable with cmake and make./

## REFLECTIONS

### Model

The MPC model takes the following information from the simulator
* ptsx  : x-cordinates of the waypoints ahead in global cordinates
* ptsx  : y-cordinates of the waypoints ahead in global cordinates
* px    : current x-position of the vehicle in global cordinates
* py    : current y-position of the vehicle in global cordinates
* psi   : current orientation of vehicle in global frame
* v     : current speed of the vehicle
* delta : steering angle of the car (NOTE: this is different from orientation (psi) of the car, it controls how the front wheels of car are turned)
* a     : current throttle

#### Polynomial Fitting & Preprocessing

In order to simplify processing, the waypoints are transformed from simulator's global cordinates to car cordinates (refer lines 113-118 in main.cpp). First, each of the waypoints are translated to car cordinatres by subtracting out px and py. Then 2D rotation is applied on the translated points.

A third-degree polynomial line is fit to these transformed waypoints using polyfit() function (this polynomial line is the path that vehicle should try). Since we are operating from the vehicle's coordinates, we can use px, py and psi all equal to zero: from the vehicle's standpoint. 
The cross-track error is calculated by evaluating the polynomial function (polyeval()) at px (which in  zero). The psi error, or epsi, which is calculated from the derivative of polynomial fit line, is therefore simpler to calculate, as polynomials above the first order in the original equation are all eliminated through multiplication by zero (since x is zero). It is the negative arc tangent of the second coefficient (the first-order x was in the original polynomial).

#### Handling Latency

There is an additional latency of 100ms added in the simulator between the actuator calculation and when the simulator will actually perform that action. Since there is a latency in path going from estimator (MPC) to simulator, I have introduced similar latency on the forward path on the information going from simulator to estimator(MPC). Instead of passing the current information from simuator to MPC, I predict the state after 100ms using vehicle update equations (refer line 127 to 137 in main.cpp). Note that these equations were simplified again because of the coordinate system transformation. This new predicted state, along with the coefficients, are then fed into the mpc.Solve() function found in MPC.cpp.

### Main.cpp

Within the MPC class's Solve() function, the independent variables (based on state size, actuators, and timesteps) are first set to zero besides the first variable, which is set to the current input (i.e., predicted state accoutning for latency). The variables then have upper and lower boundaries set for their values. Defaults are taken from the Udacity lessons, for ex, delta (steering angle) within limits of -25 to 25 degrees and "a" within -1 to 1. Constraints are then set similarly to how variables were begun, with zero for all values other than the initial (based on input state).

FG_eval class: First, overall cost function is created. The overall cost function consist of weighted cost of cte, epsi, speed and cost related to `delta` and `a`. Higher wieghts are set for cte and epsi cost so that vehicle remain on track. Similarly, non-zero weights are set for speed so that vehicle doesn't stop. The cost related to `delta_change` and `a_change` ensures that the ride is smooth.

The updated cost constraints are calculated by first calculating the states at time t and time + 1. This, along with the variables and constraints calculated earlier, can be fed to the `ipopt` solver. This solver takes in all the information and will calculate the future predicted states, which also includes updated delta and "a" values that I use for my actuator values.

### TimeStep (N) and Timestep duration(dt)

N=10 and dt=0.1 was chosen after some trial and error. This means we essentially predict for only 1 sec. This seems to be a fine choice since car is able to maintain the track without any erratic driving.




