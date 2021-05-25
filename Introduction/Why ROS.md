# Why ROS?

The robotics community has made impressive progress in recent years. Reliable and inexpensive robot hardware  ——from land-based mobile robots, to quadrotor helicopters, to humanoids — is more widely available than ever before. Perhaps even more impressively, the community has also developed algorithms that help those robots run with increasing levels of autonomy.

In spite of (or, some might argue, because of ) this rapid progress, robots do still present
some significant challenges for software developers. This book introduces a software platform called **Robot Operating System**, or **ROS**,<sup>1</sup> that is intended to ease some of these difficulties. The [official description of ROS](http://wiki.ros.org/ROS/Introduction) is:

> ROS is an open-source, meta-operating system for your robot. It provides the 
> services you would expect from an operating system, including hardware abstraction,
> low-level device control, implementation of commonly-used functionality, message-passing
> between processes, and package management. It also provides tools and libraries for
> obtaining, building, writing, and running code across multiple computers.

This description is accurate — and it correctly emphasizes that ROS does not replace, but instead works alongside a traditional operating system — but it may leave you wondering what the real advantages are for software that uses ROS. After all, learning to use a new framework, particularly one as complex and diverse as ROS, can take quite a lot of time and mental energy, so one should be certain that the investment will be worthwhile. Here are a few specific issues in the development of software for robots that ROS can help to resolve.

## Distributed computation 

Many modern robot systems rely on software that spans many different processes and runs across several different computers. For example:

- Some robots carry multiple computers, each of which controls a subset of the robot's sensors or actuators.
- Even within a single computer, it's often a good idea to divide the robot's software into small, stand-alone parts that cooperate to achieve the overall goal. This approach is sometimes called "complexity via composition."
- When multiple robots attempt to cooperate on a shared task, they often need to communicate with one another to coordinate their efforts.
- Human users often send commands to a robot from a laptop, a desktop computer, or mobile device. We can think of this human interface as an extension of the robot's software.

The common thread through all of these cases is a need for communication between multiple processes that may or may not live on the same computer. ROS provides two relatively
simple, seamless mechanisms for this kind of communication. We'll discuss the details in
Chapters 3 and 8.

## Software reuse 

The rapid progress of robotics research has resulted in a growing collection of good algorithms for common tasks such as navigation, motion planning, mapping, and many others. Of course, the existence of these algorithms is only truly useful if there is a way to apply them in new contexts, without the need to reimplement each algorithm for each new system. ROS can help to prevent this kind of pain in at least two important ways.

- ROS's standard packages provide stable, debugged implementations of many important robotics algorithms.
- ROS's message passing interface is becoming a de facto standard for robot software interoperability, which means that ROS interfaces to both the latest hardware and to implementations of cutting edge algorithms are quite often available. For example, the ROS website lists hundreds of publicly-available [ROS packages](http://www.ros.org/browse). This sort of uniform interface greatly reduces the need to write "glue" code to connect existing parts

As a result, developers that use ROS can expect — after, of course, climbing ROS's initial learning curve — to focus more time on experimenting with new ideas, and less time reinventing wheels.

## Rapid testing

One of the reasons that software development for robots is often more challenging than other kinds of development is that testing can be time consuming and error-prone. Physical robots may not always be available to work with, and when they are, the process is sometimes slow and finicky. Working with ROS provides two effective workarounds to this problem.

- Well-designed ROS systems separate the low-level direct control of the hardware and high-level processing and decision making into separate programs. Because of this separation, we can temporarily replace those low-level programs (and their corresponding hardware) with a simulator, to test the behavior of the high-level part of the system.
- ROS also provides a simple way to record and play back sensor data and other kinds of messages. This facility means that we can obtain more leverage from the time we do spend operating a physical robot. By recording the robot's sensor data, we can replay it many times to test different ways of processing that same data. In ROS parlance, these recordings are called "bags" and a tool called rosbag is used to record and replay them. See Chapter 9.

A crucial point for both of these features is that the change is seamless. Because the real robot, the simulator, and the bag playback mechanism can all provide identical (or at least very similar) interfaces, your software does not need to be modified to operate in these distinct scenarios, and indeed need not even "know" whether it is talking to a real robot or to something else.

Of course, ROS is not the only platform that offers these capabilities. What is unique about ROS, at least in the author's judgment, is the level of widespread support for ROS across the robotics community. This "critical mass" of support makes it reasonable to predict that ROS will continue to evolve, expand, and improve in the future.

## ROS is not...

Finally, let's take a moment to review a few things that are not true about ROS.

- *ROS is not a programming language*. In fact, ROS programs are routinely written in [C++](http://wiki.ros.org/roscpp), and this book has some explicit instructions on how to do that. Client libraries are also available for [Python](http://wiki.ros.org/rospy), [Java](http://wiki.ros.org/rosjava), [Lisp](http://wiki.ros.org/roslisp), and a handful of other [languages](http://wiki.ros.org/Client%20Libraries).
- *ROS is not (only) a library* . Although ROS does include client libraries, it also includes (among other things), a central server, a set of command-line tools, a set of graphical tools, and a build system.
- *ROS is not an integrated development environment*. Although ROS does not prescribe any particular development environment, it can be used with most popular [IDEs](http://wiki.ros.org/IDEs). It is also quite reasonable (and, indeed, it is the author's personal preference) to use ROS from a text editor and the command line, without any IDE.

---

<sup>1</sup> When spoken aloud, the name "ROS" is nearly always pronounced as a single word that rhymes with
"moss," and almost never spelled out "arrr-oh-ess."
