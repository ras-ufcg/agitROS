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

## Reusabilidade de *software*

O rápido progresso de pesquisas na área de robótica resultou no crescimento de um conjunto de bons algoritmos para tarefas recorrentes como navegação, planejamento de trajetória, mapeamento e muitas outras. Evidentemente, a existência destes algoritmos só é verdadeiramente útil se há uma maneira de aplicá-los em novos contextos, sem a necessidade de reimplementá-los a cada novo sistema. O ROS pode ajudar na prevenção deste tipo de problema em pelo menos duas maneiras. 

- Os pacotes padrão do ROS provêem implementações estáveis e depuradas de muitos algoritmos importantes na área de robótica.
- A *message passing interface* do ROS está se tornando uma referência na interoperabilidade de *softwares* robóticos, o que significa que o ROS é quase sempre compatível com os *hardwares* mais recentes e com algoritmos de ponta. Por exemplo, o *website* do ROS lista centenas de [pacotes ROS](http://www.ros.org/browse) de domínio público. Este tipo de compatibilidade reduz significativamente a necessidade de escrever códigos extras para conectar partes já existentes. 

Como resultado, os desenvolvedores que utilizam o ROS podem esperar - após, claro, percorrerem a curva de aprendizagem inicial da ferramenta - aplicar mais tempo na experimentação de novas ideias, e menos tempo reinventando a roda. 


## Testagem rápida

Uma das razões pelas quais o desenvolvimento de software para robótica é ainda mais desafiador do que outros tipos de desenvolvimento é que a testagem pode ser demorada e sujeita a erros. Robôs físicos nem sempre estão disponíveis para experimentações, e quando estão, o processo pode ser lento e minucioso. Trabalhar com o ROS provê duas alternativas efetivas para este problema. 

- Sistemas ROS bem projetados separam o controle direto de baixo-nível do *hardware* e o processamento de alto-nível e de tomada de decisões em programas distintos. Devido a essa separação, podemos substituir temporariamente estes programas de baixo-nível (e o *hardware* correspondente) com um simulador, para testar o comportamento da parte alto-nível do sistema. 
- O ROS também fornece uma maneira simples de gravar e reproduzir dados de sensores e outros tipos de mensagens. Este recurso significa que podemos potencializar o tempo empregado na operação de um robô físico. Ao gravar os dados dos sensores do robô, podemos reproduzi-los inúmeras vezes de modo a testar maneiras diferentes de processar os mesmos dados. No linguajar ROS, estas gravações são chamadas de “bags” e uma ferramenta chamada rosbag é usada para gravá-las e reproduzi-las. Veja o capítulo 9. 

Um ponto crucial destas duas funcionalidades é que a mudança é suave. Pelo fato do robô real, o simulador e o mecanismo de reprodução "bag" proverem interfaces idênticas (ou pelo menos muito semelhantes), seus programas não precisam ser modificados para operar nesses cenários distintos, e de fato nem precisam “saber” se a comunicação se dá com um robô real ou com qualquer outra coisa. 

Obviamente, o ROS não é a única plataforma que oferece estas capacidades. O que é único a respeito do ROS é, pelo menos na visão do autor, o nível de suporte difundido na comunidade de robótica. Esta “massa crítica” de suporte torna razoável a previsão de uma contínua evolução, expansão e melhoramento do ROS no futuro. 

## O ROS não é…

Por fim, vamos reservar um tempo para rever algumas coisas que não são verdade sobre o ROS. 

- *ROS não é uma linguagem de programação*. Na verdade, os programas ROS são normalmente escritos em [C++](http://wiki.ros.org/roscpp), e este livro tem algumas instruções explícitas de como fazer isso. Bibliotecas cliente também são disponibilizadas para [Python](http://wiki.ros.org/rospy), [Java](http://wiki.ros.org/rosjava), [Lisp](http://wiki.ros.org/roslisp), e um punhado de outras [linguagens](http://wiki.ros.org/Client%20Libraries).
- *ROS não é (somente) uma biblioteca*. Apesar do ROS incluir bibliotecas cliente, ele também inclui (entre outras coisas), um servidor central, um conjunto de ferramentas de linha-de-comando, um conjunto de ferramentas gráficas, e um *build system*.
- *ROS não é um ambiente de desenvolvimento integrado*. Muito embora o ROS não prescreva qualquer ambiente de desenvolvimento específico, ele pode ser usado com as [IDEs](http://wiki.ros.org/IDEs) mais populares. É bem compreensível (e, de fato, esta é a preferência pessoal do autor) usar o ROS a partir de um editor de texto e por meio de linhas de comando, sem qualquer IDE.


---

<sup>1</sup> Quando dito em voz alta, o nome “ROS” é quase sempre pronunciado como uma única palavra que rima com “moss”, e quase nunca soletrado como “Érre-ó-ésse”.
