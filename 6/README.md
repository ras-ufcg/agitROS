---
layout: page
title: Arquivos de launch
has_children: true
nav_order: 7
---

# Arquivos de lançamento

Nos quais configuramos e executamos muitos nós de uma vez usando arquivos de inicialização.
{: .fs-6 .fw-300 }

If you've worked through all of the examples so far, by now you might be getting frustrated by the need to start so many different nodes, not to mention `roscore`, by hand in
so many different terminals. Fortunately, ROS provides a mechanism for starting the master and many nodes all at once, using a file called a **launch file**. The use of launch files
is widespread through many ROS packages. Any system that uses more than one or two
nodes is likely to take advantage of launch files to specify and configure the nodes to be
used. This chapter introduces these files and the roslaunch tool that uses them.

Se você trabalhou com todos os exemplos até este momento, agora você pode estar ficando frustrado com a necessidade de iniciar tantos nós diferentes, sem mencionar o `roscore`,
manualmente em tantos terminais diferentes. Felizmente, o ROS fornece um mecanismo para iniciar o mestre e muitos nós de uma vez, usando um arquivo chamado **arquivo de inicialização**. O uso de arquivos de inicialização
é difundido em muitos pacotes ROS. Qualquer sistema que use mais de um ou dois
nós provavelmente tirará proveito dos arquivos de ativação para especificar e configurar os nós a serem
usados. Este capítulo apresenta esses arquivos e a ferramenta roslaunch que os utiliza.
