---
layout: page
title: Serviços
has_children: true
nav_order: 9
---

# Serviços

In which we call services and respond to service requests.
{: .fs-6 .fw-300 }

In Chapters 2 and 3, we focused on how messages travel between nodes. Even though theyare the primary method for communication in ROS, messages do have some limitations. This chapter introduces an alternative method of communication called **service calls**. Service calls differ from messages in two ways.

- Service calls are **bi-directional**. One node sends information to another node and waits for a response. Information flows in both directions. In contrast, when a message is published, there is no concept of a response, and not even any guarantee that anyone is subscribing to those messages.

- Service calls implement **one-to-one** communication. Each service call is initiated by one node, and the response goes back to that same node. On the other hand, each message is associated with a topic that might have many publishers and many subscribers.

Aside from these (very important!) differences, services are similar to messages. In this chapter, we'll see how to inspect and call services from the command line, and how to write nodes that act as either service clients or as servers.
