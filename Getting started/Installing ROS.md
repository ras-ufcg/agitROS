# Instalando o ROS

Antes de fazer qualquer coisa com o ROS, você deve se certificar que ele está instalado no seu computador. (Se você está trabalhando em um computador no qual outra pessoa já instalou o ROS — incluindo o pacote `ros-indigo-turtlesim` — você pode pular para a próxima seção). O processo de instalação é [bem documentado](http://wiki.ros.org/ROS/Installation) e é bastante direto. Aqui está um resumo dos passos necessários.

## Adicionando o repositório do ROS 

Como superusuário, crie um arquivo chamado
```
/etc/apt/sources.list.d/ros-latest.list
```
contendo uma única linha:
```
deb http://packages.ros.org/ros/ubuntu trusty main
```

> :warning: Esta linha específica para Ubuntu 14.04, cujo codinome é `trusty`. Se você estiver utilizando o Ubuntu 13.10, você pode substituir `saucy` por `trusty`.
>> :fast_forward: Outras versões do Ubuntu — mais antigas ou mais recentes — não são suportadas por pacotes pré-compilados para a distribuição `indigo` do ROS. Entretanto, para versões do Ubuntu mais recentes que 14.04, [instalando ROS de sua fonte](http://wiki.ros.org/indigo/Installation/Source) pode ser uma opção razoável.
> Se você não tem certeza sobre qual versão do Ubuntu está usando, pode descobrir utilizando este comando:
> ``` 
> lsb_release -a
> ```
> A saída deve mostrar o codinome e número de lançamento.

## Instalando a chave de autenticação do pacote

Antes de instalar os pacotes do ROS, você deve obter a chave de autenticação do pacote. Primeiro, faça o download da chave:
```
wget https://raw.githubusercontent.com/ros/rosdistro/master/ros.key
```
Se funcionar corretamente, você terá um pequeno arquivo binário chamado `ros.key`. Depois, você deve configurar o sistema de gerenciamento de pacotes `apt` para usar esta chave:
```
sudo apt-key add ros.key
```
Depois de completar este passo, (`apt-key` deve retornar `OK`), você pode excluir `ros.key` com segurança.

## Downloading the package lists

Once the repositories are configured, you can get the latest lists of available packages in the usual way:
```
sudo apt-get update
```
Note that this will update *all* of the repositories configured on your system, not just the newly added ROS repositories.

## Installing the ROS packages 

Now we can actually install the ROS software. The simplest approach is to perform a complete install of the core ROS system:
```
sudo apt-get install ros-indigo-desktop-full
```
If you have plenty of free disk space — a few GB should suffice — this package is almost certainly the best choice. If you need them, there are also some more compact alternatives, including `ros-indigo-desktop` and `ros-indigo-ros-base`, that omit some packages and tools in favor of reduced disk space requirements.

## Installing turtlesim 

In this book we'll refer many times to a simple "simulator" called `turtlesim` to illustrate how things work. If you plan to follow along with any of the examples — Recommended answer: Yes — you'll need to install `turtlesim`. Use a command like this:
```
sudo apt-get install ros-indigo-turtlesim
```

## Setting up `rosdep` systemwide 
After installing the ROS packages, you'll need to execute this command:
```
sudo rosdep init
```
This is a one-time initialization step; once ROS is working correctly, many users will not need to revisit `rosdep`.

> :fast_forward: As its name suggests, the purpose of this command is to initialize [`rosdep`](http://wiki.ros.org/rosdep), which is a tool for checking and installing package dependencies in an OS-independent way. On Ubuntu, for example, rosdep acts as a front end to `apt-get`. We won't use `rosdep` directly, but we will use a few tools that invoke it behind the scenes. Those tools will be very unhappy if `rosdep`is not set up correctly.

> :warning: The online documentation occasionally mentions a tool called `rosinstall`, whose job is to [install ROS software from source](http://wiki.ros.org/rosinstall). The software that we'll need in this book is all available in Ubuntu `deb` packages, which do not require `rosinstall`.

