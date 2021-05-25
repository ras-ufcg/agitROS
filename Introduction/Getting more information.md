# Getting more information

As alluded to above, this book makes no attempt to be a comprehensive reference for ROS. It’s all but certain that you will need additional details to do anything interesting. Fortunately, online information about ROS is abundant.

- Most importantly, the developers of ROS maintain extensive [documentation](http://wiki.ros.org/), including a set of tutorials. This book includes links to many of the corresponding pages in this documentation. If you are reading an electronic version of the book in a reasonably modern PDF viewer, you should be able to click these links directly to open them in your browser.
- When unexpected things happen—and chances are quite good that they will — there is a question and answer site (in the style of Stack Exchange) devoted to [ROS](http://answers.ros.org/).
- It may also be valuable to subscribe to the [ros-users mailing list](http://lists.ros.org/mailman/listinfo/ros-users) on which announcements sometimes appear.

Here are two important details that will help you make sense of some of the documentation, but are not always fully explained in context there.

## Distributions

Major versions of ROS are called [**distributions**](http://wiki.ros.org/Distributions), and are named using adjectives that start with with successive letters of the alphabet. (This is, for comparison, very similar to the naming schemes used for other large software projects, including Ubuntu and Android.) At the time of this writing, the current distribution is indigo. The next distribution, named [`jade`](http://wiki.ros.org/jade), is due in May 2015. Older distributions include `hydro`, `groovy`, `fuerte`, `electric`, `diamondback`, `C Turtle`, and `box turtle`. These distribution names appear in many places throughout the documentation.

> :warning: To keep things as simple and up-to-date as possible, this book assumes that you areusing `indigo`.

> :fast_forward:  If, for some reason, you need to use `hydro` instead of `indigo`, nearly all of the book’s content still applies without modification. The same is true for `groovy` as well, with one important exception: In distributions newer than `groovy` (and, therefore, in this book), velocity commands for the `turtlesim` simulator have been changed to use a standard message type and topic name that happen to be shared with many real mobile robots.
>
> | Distribution  | Topic name    | Message type  |
> | ------------- | ------------- | ------------- |
> | `groovy` | `/turtle1/command_velocity`  | `turtlesim/Velocity` |
> | `indigo`/`hydro`  | `/turtle1/cmd_vel` | `geometry_msgs/Twist`  |
>
> This change has a few practical implications:
> - When adding dependencies to your package, you’ll need a dependency on `turtlesim`, instead of on `geometry_msgs`.
> - The relevant header file (see page 49) is `turtlesim/Velocity.h` rather than `geometry_msgs/Twist.h`.
> - The `turtlesim/Velocity` message type has only two fields, called linear and angular. These fields play the same roles as the `linear.x` and `angular.z` fields of `geometry_msgs/Twist`. This change applies both on the command line and in C++ code.

## Build systems 

Starting with the `groovy` distribution, ROS made some major changes to the way software is compiled. Older, `pre-groovy` distributions used a build system called `rosbuild`, but more recent versions have begun to replace `rosbuild` with a new build system called `catkin`. It is important to know about this change because a few of the tutorials have separate versions, depending on whether you’re using `rosbuild` or `catkin`. These separate versions are selected using a pair of buttons near the top of the tutorial. This book describes `catkin`, but there may be some cases in which `rosbuild` is a better choice.

