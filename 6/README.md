---
layout: page
title: Arquivos de launch
has_children: true
nav_order: 7
---

# Launch files

In which we configure and run many nodes at once using launch files.
{: .fs-6 .fw-300 }

If you've worked through all of the examples so far, by now you might be getting frustrated by the need to start so many different nodes, not to mention `roscore`, by hand in
so many different terminals. Fortunately, ROS provides a mechanism for starting the master and many nodes all at once, using a file called a **launch file**. The use of launch files
is widespread through many ROS packages. Any system that uses more than one or two
nodes is likely to take advantage of launch files to specify and configure the nodes to be
used. This chapter introduces these files and the roslaunch tool that uses them.
