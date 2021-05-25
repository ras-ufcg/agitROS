# Installing ROS

Before you can do anything with ROS, naturally you must ensure that it is installed on your computer. (If you are working with a computer on which someone else has already
installed ROS — including the `ros-indigo-turtlesim`package — you can skip directly to next section). The installation process is [well documented](http://wiki.ros.org/ROS/Installation) and mostly straightforward. Here’s a summary of the necessary steps.

## Adding the ROS repository 

As root, create a file called
```
/etc/apt/sources.list.d/ros-latest.list
```
containing a single line:
```
deb http://packages.ros.org/ros/ubuntu trusty main
```

> :warning: This line is specific to Ubuntu 14.04, whose codename is `trusty`. If you are using Ubuntu 13.10 instead, you can substitute `saucy` for `trusty`.
>> :fast_forward: Other versions of Ubuntu — both older and and newer — are not supported by the pre-compiled packages for the `indigo` distribution of ROS. However, for Ubuntu versions newer than 14.04, [installing ROS from its source](http://wiki.ros.org/indigo/Installation/Source) may be a reasonable option.
> If you are unsure of which Ubuntu version you’re using, you can find out using this command:
> ``` 
> lsb_release -a
> ```
> The output should show both a codename and a release number.

## Installing the package authentication key

Before installing the ROS packages, you must acquire their package authentication key. First, download the key:
```
wget https://raw.githubusercontent.com/ros/rosdistro/master/ros.key
```
If this works correctly, you’ll have a small binary file called `ros.key`. Next, you should configure the `apt` package management system to use this key:
```
sudo apt-key add ros.key
```
After completing this step (`apt-key` should say `OK`), you can safely delete `ros.key`.

## Downloading the package lists

Once the repositories are configured, you can get the latest lists of available packages in the usual way:
```
sudo apt-get update
```
Note that this will update *all* of the repositories configured on your system, not just the newly added ROS repositories.

## Installing the ROS packages 

Now we can actually install the ROS software. The simplest approach is to perform a complete install of the core ROS system:
```
sudo apt-get install ros-indigo-desktop-full
```
If you have plenty of free disk space — a few GB should suffice — this package is almost certainly the best choice. If you need them, there are also some more compact alternatives, including `ros-indigo-desktop` and `ros-indigo-ros-base`, that omit some packages and tools in favor of reduced disk space requirements.

## Installing turtlesim 

In this book we’ll refer many times to a simple “simulator” called `turtlesim` to illustrate how things work. If you plan to follow along with any of the examples — Recommended answer: Yes — you’ll need to install `turtlesim`. Use a command like this:
```
sudo apt-get install ros-indigo-turtlesim
```

## Setting up `rosdep` systemwide 
After installing the ROS packages, you’ll need to execute this command:
```
sudo rosdep init
```
This is a one-time initialization step; once ROS is working correctly, many users will not need to revisit `rosdep`.

> :fast_forward: As its name suggests, the purpose of this command is to initialize [`rosdep`](http://wiki.ros.org/rosdep), which is a tool for checking and installing package dependencies in an OS-independent way. On Ubuntu, for example, rosdep acts as a front end to `apt-get`. We won’t use `rosdep` directly, but we will use a few tools that invoke it behind the scenes. Those tools will be very unhappy if `rosdep`is not set up correctly.

> :warning: The online documentation occasionally mentions a tool called `rosinstall`, whose job is to [install ROS software from source](http://wiki.ros.org/rosinstall). The software that we’ll need in this book is all available in Ubuntu `deb` packages, which do not require `rosinstall`.

