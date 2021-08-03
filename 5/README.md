---
layout: page
title: Recursos de grafo
has_children: true
nav_order: 6
---


# Recursos de grafo

*No qual nós aprendemos como ROS denomina nodes, tópicos, parâmetros e serviços.*
{: .fs-6 .fw-300 }

No capítulo 3, nós utilizamos strings chamadas "`hello_ros`" e "`publish_velocity`" para denominar
nodes e strings como "`turtle1/cmd_vel`" e "`turtle1/pose`" como nomes de tópicos.
to nodes, and strings like "`turtle1/cmd_vel`" and "`turtle1/pose`" as the names of topics. 
Todos esses são exemplos de **recursos de grafo**. ROS possui um sistema flexível para nomear que
aceita diferentes tipos de nomes. (Esses quatro, por exemplo, são **nomes relativos**.)
Nesse capítulo, nós pegaremos um atalho para entender vários tipos de recursos de grafo para nomear,
bem como ROS os decide. Nós apresentamos essas ideias, que são na verdade simples, em um
capítulo separado porque elas são relevantes para a maioria dos conceitos da segunda metade deste livro.
