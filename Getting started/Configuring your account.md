# Configuring your account

Whether you install ROS yourself or use a computer on which ROS is already installed, there are two important configuration steps that must be done within the account of every user that wants to use ROS.

## Setting up `rosdep` in a user account 

First, you must initialize the `rosdep` system in your account, using this command:
```
rosdep update
```
This command stores some files in your home directory, in a subdirectory called `.ros`. It generally only needs to be done once. 

> :warning: Note that, unlike `rosdep` init above, the `rosdep update` command should be run using your normal user account, not using `sudo`.

## Setting environment variables

ROS relies on a few environment variables to locate the files it needs. To set these environment variables, you'll need to execute the [`setup.bash` script](http://wiki.ros.org/rosbash) that ROS provides, using this command:
```
source /opt/ros/indigo/setup.bash
```
You can then confirm that the environment variables are set correctly using a command like this:
```
export | grep ROS
```

If everything has worked correctly, you should see a handful of values (showing values for environment variables like `ROS_DISTRO` and `ROS_PACKAGE_PATH`) as the output from this command. If `setup.bash` has not been run, then the output of this command will usually be empty.

> :warning: If you get “command not found” errors from the ROS commands introduced later in this chapter, the most likely reason is that `setup.bash` has not been run in your current shell.

Note, however, that the steps listed above apply only to the current shell. It would work perfectly well to simply execute that `source` command each time you start a new shell in which you'd like to execute ROS commands. However, this is both annoying and remarkably easy to forget, especially when you consider that the modular design of many ROS systems often calls for several different commands to execute concurrently, each in a separate terminal.

Thus, you'll want to configure your account to run the `setup.bash` script automatically, each time you start a new shell. To do this, edit the file named `.bashrc` in your home directory, and put the above `source` command at the bottom.

> :fast_forward: In addition to setting environment variables, this `setup.bash` script also defines `bash` functions to implement a few commands, including `roscd` and `rosls`, which are introduced below. These functions are defined in the [`rosbash` package](http://wiki.ros.org/rosbash).
