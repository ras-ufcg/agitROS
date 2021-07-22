# Graph resource names

*In which we learn how ROS resolves the names of nodes, topics, parameters, and services.*

In Chapter 3, we used strings like "`hello_ros`" and "`publish_velocity`" to give names 
to nodes, and strings like "`turtle1/cmd_vel`" and "`turtle1/pose`" as the names of topics. 
All of these are examples of **graph resource names**. ROS has a flexible naming system that 
accepts several different kinds of names. (These four, for example, are all **relative names**.) 
In this chapter, we’ll take a short detour to understand the various kinds of graph resource 
names, and how ROS resolves them. We present these ideas, which are actually quite simple, as 
a separate chapter because they’re relevant to most of the concepts in the second half of this 
book.
