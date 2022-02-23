# Ataque de negação de serviço

Origem: Wikipédia, a enciclopédia livre.

| [![img](https://upload.wikimedia.org/wikipedia/commons/thumb/9/99/Question_book-new.svg/50px-Question_book-new.svg.png)](https://pt.wikipedia.org/wiki/Ficheiro:Question_book-new.svg) | Esta página [cita fontes](https://pt.wikipedia.org/wiki/Wikipédia:Livro_de_estilo/Cite_as_fontes), mas estas **não cobrem todo o conteúdo**. Ajude a [inserir referências](https://pt.wikipedia.org/wiki/Wikipédia:Livro_de_estilo/Referências_e_notas_de_rodapé). Conteúdo não [verificável](https://pt.wikipedia.org/wiki/Wikipédia:Verificabilidade) poderá ser [removido](https://pt.wikipedia.org/wiki/Wikipédia:Verificabilidade#Política_de_verificabilidade).—*Encontre fontes:* [Google](https://www.google.com/search?as_eq=wikipedia&as_epq=Ataque+de+negação+de+serviço) ([notícias](https://www.google.com/search?hl=pt&tbm=nws&q=Ataque+de+negação+de+serviço&oq=Ataque+de+negação+de+serviço), [livros](http://books.google.com/books?&as_brr=0&as_epq=Ataque+de+negação+de+serviço) e [acadêmico](https://scholar.google.com.br/scholar?hl=pt&q=Ataque+de+negação+de+serviço)) *(Julho de 2013)* |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|                                                              |                                                              |

[![img](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3f/Stachledraht_DDos_Attack.svg/220px-Stachledraht_DDos_Attack.svg.png)](https://pt.wikipedia.org/wiki/Ficheiro:Stachledraht_DDos_Attack.svg)

Diagrama de um Ataque *DDoS Stacheldraht*.

Um **ataque de negação de serviço** (também conhecido como **DoS Attack**, um [acrônimo](https://pt.wikipedia.org/wiki/Acrônimo) em [inglês](https://pt.wikipedia.org/wiki/Língua_inglesa) para *Denial of Service*), é uma tentativa de tornar os recursos de um sistema indisponíveis para os seus utilizadores. Alvos típicos são [servidores web](https://pt.wikipedia.org/wiki/Servidor_web), e o ataque procura tornar as páginas hospedadas indisponíveis na [rede](https://pt.wikipedia.org/wiki/WWW). Não se trata de uma invasão do sistema, mas sim da sua invalidação por sobrecarga. Os ataques de negação de serviço são feitos geralmente de duas formas:

- forçar o sistema vítima a reinicializar ou consumir todos os recursos (como [memória](https://pt.wikipedia.org/wiki/Memória_(computador)) ou [processamento](https://pt.wikipedia.org/wiki/Processamento), por exemplo) de forma que ele não possa mais fornecer seu serviço;
- obstruir a mídia de comunicação entre os utilizadores e o sistema vítima de forma a não se comunicarem adequadamente.

## Índice



- [1Ataque distribuído](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#Ataque_distribuído)
- 2Ataques de negação de serviços
  - [2.1Ataques por inundação](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#Ataques_por_inundação)
  - [2.2Ataques por amplificação](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#Ataques_por_amplificação)
  - [2.3Ataques por exploração de protocolos](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#Ataques_por_exploração_de_protocolos)
- [3Ver também](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#Ver_também)
- [4Referências](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#Referências)

## Ataque distribuído

Num ataque distribuído de negação de serviço (também conhecido como **DDoS**, um [acrônimo](https://pt.wikipedia.org/wiki/Acrônimo) em [inglês](https://pt.wikipedia.org/wiki/Língua_inglesa) para *Distributed Denial of Service*), um computador mestre denominado *master* pode ter sob seu comando até milhares de computadores *zombies*, literalmente zumbis. Nesse caso, as tarefas de ataque de negação de serviço são distribuídas a um "exército" de máquinas escravizadas.

O ataque consiste em fazer com que os *zombies* (máquinas infectadas e sob comando do Mestre) se preparem para aceder a um determinado recurso num determinado servidor numa mesma hora de uma mesma data. Passada essa fase, na determinada hora, todos os *zombies* (ligados e conectados à rede) acedem ao mesmo recurso do mesmo servidor. Como servidores web possuem um número limitado de utilizadores que pode atender simultaneamente (*slots*), o grande e repentino número de requisições de acesso esgota esse número, fazendo com que o servidor não seja capaz de atender a mais nenhum pedido.

Dependendo do recurso atacado, o servidor pode chegar a reiniciar ou até mesmo ficar travado.

Vírus conhecidos criados para a distribuição de rotinas de ataque de negação de serviço incluem "Codered", "Slammer", "MyDoom", que escravizam o infectado. Ferramentas conhecidas de ataques DDos incluem "Fabi" (1998), "Blitznet", "Trin00" (jun/1999), "TFN" (ago/1999), "Stacheldraht" (set/1999), "Shaft", "TFN2K" (dez/1999), "Trank".

Uma outra estratégia de ataque seria por meio dos *[botnets](https://pt.wikipedia.org/wiki/Botnet)* praticando ataques de negação de serviço contra alvos remotos.

## Ataques de negação de serviços

O principal objetivo de um ataque de negação de serviço é deixar um recurso computacional inacessível aos seus utilizadores legítimos. As duas classes principais de métodos de ataque são diminuição de largura de banda e esgotamento de recursos. Ataques de diminuição de largura de banda são caracterizados pelos ataques por inundação e amplificação. Ataques de esgotamento de recursos são ataques que fazem uso indevido dos protocolos de comunicação de rede ou enviam pacotes de rede malformados.[[1\]](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#cite_note-ROCHARodrigoCO-1)

### Ataques por inundação

Ataques por inundação se caracterizam por enviarem um grande volume de tráfego ao sistema da vítima primária de modo a congestionar a sua banda. O impacto deste ataque pode variar entre deixar o sistema lento, derrubá-lo ou sobrecarregar a banda da rede da vítima. Ataques por inundação podem usar pacotes UDP ([User Datagram Protocol](https://pt.wikipedia.org/wiki/User_Datagram_Protocol)) ou ICMP ([Internet Control Message Protocol](https://pt.wikipedia.org/wiki/Internet_Control_Message_Protocol)).[[1\]](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#cite_note-ROCHARodrigoCO-1) Um dos grandes problemas desse ataque é que qualquer tipo de pacote pode ser usado, bastando ele ter permissão de andar pelos enlaces até o sistema visado, e dessa forma, consumindo toda a capacidade do servidor.

### Ataques por amplificação

Ataques por amplificação se caracterizam por enviarem requisições forjadas para uma grande quantidade de computadores ou para um endereço IP de *broadcast*, que por sua vez responderão às requisições. Forjando o endereço IP de origem das requisições para o endereço IP da vítima primária fará com que todas as respostas sejam direcionadas para o alvo do ataque. O endereço IP de *broadcast* é um recurso encontrado em roteadores. Quando uma requisição possui um endereço IP de *broadcast* como endereço de destino, o roteador replica o pacote e o envia para todos os endereços IP dentro do intervalo de *broadcast*. Em ataques por amplificação, endereços de *broadcast* são usados para amplificar e refletir o tráfego de ataque, reduzindo então a banda da vítima primária.[[1\]](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#cite_note-ROCHARodrigoCO-1)

### Ataques por exploração de protocolos

Ataques por exploração de protocolos se caracterizam por consumir excessivamente os recursos da vítima primária explorando alguma característica específica ou falha de implementação de algum protocolo instalado no sistema da vítima.

Os principais ataques por exploração de protocolos são por uso indevido de pacotes TCP SYN (Transfer Control Protocol Synchronize) ou de pacotes TCP PUSHACK.[[1\]](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#cite_note-ROCHARodrigoCO-1)

## Ver também

| [![Portal](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c9/Portal.svg/36px-Portal.svg.png)](https://pt.wikipedia.org/wiki/Ficheiro:Portal.svg) | A Wikipédia tem o portal:[Portal das tecnologias de informação](https://pt.wikipedia.org/wiki/Portal:Tecnologias_de_informação) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|                                                              |                                                              |

- [Ataque man-in-the-middle](https://pt.wikipedia.org/wiki/Ataque_man-in-the-middle)
- [LOIC](https://pt.wikipedia.org/wiki/LOIC)
- [Ping flood](https://pt.wikipedia.org/wiki/Ping_flood)
- [SYN Flood](https://pt.wikipedia.org/wiki/SYN_Flood)
- [Botnet](https://pt.wikipedia.org/wiki/Botnet)
- [Phreaking](https://pt.wikipedia.org/wiki/Phreaking)

## Referências

1. ↑ ***[Ir para:a](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#cite_ref-ROCHARodrigoCO_1-0)*** ***[b](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#cite_ref-ROCHARodrigoCO_1-1)*** ***[c](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#cite_ref-ROCHARodrigoCO_1-2)*** ***[d](https://pt.wikipedia.org/wiki/Ataque_de_negação_de_serviço#cite_ref-ROCHARodrigoCO_1-3)*** ROCHA, Rodrigo C. O. (Junho de 2012). [«Detecção em Tempo-Real de Ataques de Negação de Serviço na Rede de Origem usando um Classificador Bayesiano Simples»](https://sites.google.com/site/rcorcs/technical-reports/undergraduatedegreedissertationmajorpaperportuguese). Consultado em 10 de Março de 2013

- [![img](https://upload.wikimedia.org/wikipedia/commons/thumb/5/5f/Tomada_Brasileira_-_NBR_14136%2C_20A%2C_250V.jpg/25px-Tomada_Brasileira_-_NBR_14136%2C_20A%2C_250V.jpg)](https://pt.wikipedia.org/wiki/Ficheiro:Tomada_Brasileira_-_NBR_14136,_20A,_250V.jpg) **[Portal da tecnol](https://pt.wikipedia.org/wiki/Portal:Tecnologia)**