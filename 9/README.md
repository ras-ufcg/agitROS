# Gravando e Reproduzindo uma Mensagem
*No qual nós utilizamos arquivos .bag para gravar e reproduzir mensagens*.

Uma das principais características de um sistema bem feito de tipo ROS é que as partes
do sistema que *consumem* informação não devem se importar com o mecanismo de *produção*
da mesma. Este tipo de arquitetura é fácil de ser visualizada no modelo de comunicação 
publish-subscriber que o ROS utiliza. Um bom node do tipo subscriber deve funcionar sempre que mensagens
estão sendo publicadas, independente de qual node ou quais nodes publicam a informação. 
  Este capítulo descreve uma ferramenta denominada *rosbag*, que é um exemplo deste tipo de flexibilidade.
  Utilizando *rosbag*, é possível **gravar** as mensagens que são publicadas em um ou mais tópicos de um arquivo e, posteriormente, 
**reproduzir** essas mensagens. No geral, essas duas funções formam um método eficaz e poderoso para testar
alguns tipos de software de robôs: Nós podemos testar o robô apenas algumas vezes, gravando os tópicos importantes e, então,
reproduzir essas mensagens inúmeras vezes, utilizando e testando o software que faz o processamento desses dados. 
