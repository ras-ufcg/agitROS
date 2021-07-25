---
layout: page
title: Parâmetros
has_children: true
nav_order: 8
---

# Parâmetros

In which we configure nodes using parameters.
{: .fs-6 .fw-300 }

In addition to the messages that we've studied so far, ROS provides another mechanism
called [**parameters**](http://wiki.ros.org/roscpp/Overview/Parameter%20Server) to get information to nodes. The idea is that a centralized [**parameter
server**](http://wiki.ros.org/roscpp/Overview/ParameterServer) keeps track of a collection of values — things like integers, floating point numbers,
strings, or other data — each identified by a short string name. Because parameters
must be actively queried by the nodes that are interested in their values, they are most
suitable for configuration information that will not change (much) over time.
This chapter introduces parameters, showing how to access them from the command
line, from within nodes, and in launch files.
