---
layout: page
title: Serviços
has_children: true
nav_order: 9
---

# Serviços

No qual chamamos serviços e respondem a requisições de serviço. 
{: .fs-6 .fw-300 }

Nos [capítulos 2](https://ras-ufcg.github.io/agitROS/2/README.html) e [3](https://ras-ufcg.github.io/agitROS/3/README.html), focamos em como mensagens trafegam entre nós. Embora sejam o método principal de comunicação no ROS, as mensagens têm algumas limitações. Este capítulo introduz um método alternativo de comunicação denominado  **chamadas de serviço**. As chamadas de serviço diferem de mensagens em duas maneiras. 

- Chamadas de serviço são **bi-direcionais**. Um nó envia uma informação para outro nó e espera por uma resposta. A informação trafega em ambas as direções. Por outro lado, quando uma mensagem é publicada, não há o conceito de resposta, muito menos qualquer garantia de que alguém esteja inscrito para receber essas mensagens. 

- Chamadas de serviço implementam a comunicação **um-a-um**. Cada serviço é iniciado por um nó, e a resposta volta para este mesmo nó. Em contrapartida, cada mensagem é associada a um tópico que pode ter vários publishers e subscriberss. 

Apesar destas diferenças (muito importantes!), serviços são similares a mensagens. Neste capítulo, veremos como inspecionar e chamar serviços a partir da linha de comando e como escrever nós que agem tanto como clientes de serviço, quanto como servidores. 
