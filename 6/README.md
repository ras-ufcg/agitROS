---
layout: page
title: Arquivos de launch
has_children: true
nav_order: 7
---

# Arquivos de inicialzação

*Nos quais configuramos e executamos muitos nós de uma só vez usando arquivos de inicialização.*
{: .fs-6 .fw-300 }

Se você trabalhou com todos os exemplos até este momento, agora você pode estar ficando frustrado com a necessidade de iniciar tantos nós diferentes, sem mencionar o `roscore`, manualmente em tantos terminais diferentes. Felizmente, o ROS fornece um mecanismo para iniciar o mestre e muitos nós de uma só vez, usando um arquivo chamado **arquivo de inicialização**. O uso de arquivos de inicialização é difundido em muitos pacotes ROS. Qualquer sistema que use mais de um ou dois nós provavelmente tirará proveito dos arquivos de ativação para especificar e configurar os nós a serem usados. Este capítulo apresenta esses arquivos e a ferramenta `roslaunch` que os utiliza.
