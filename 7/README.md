---
layout: page
title: Parâmetros
has_children: true
nav_order: 8
---

# Parâmetros

No qual configuramos nós usando parâmetros.
{: .fs-6 .fw-300 }

Além das mensagens que estudamos até agora, o ROS fornece outro mecanismo chamado
[**parâmetros**](http://wiki.ros.org/roscpp/Overview/Parameter%20Server) para obter informações para os nós. A ideia é que um [**servidor de parâmetros**](http://wiki.ros.org/roscpp/Overview/ParameterServer) centralizado mantenha o controle de uma coleção de valores — coisas como números inteiros e de ponto 
flutuante, strings ou outros dados — cada um identificado por um nome de string curto. Como os parâmetros devem ser consultados ativamente pelos nós que 
estão interessados em seus valores, eles são mais adequados para informações de configuração que não mudarão (muito) com o tempo. Este capítulo apresenta 
parâmetros, mostrando como acessá-los a partir da linha de comando, de dentro dos nós e em arquivos de inicialização.
