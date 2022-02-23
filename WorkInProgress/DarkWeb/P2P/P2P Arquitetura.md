## Arquitetura

Princípios, modelos e algoritmos de funcionamento

[![img](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/images/p2p_model.png)](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/arquitetura.html#)

### P2P

 Arquitetura P2P (*peer-to-peer*) é uma arquitetura de redes em que cada par, ou nó, coopera entre si para prover serviços um ao outro, sem a necessidade a priori de um servidor central. Todos os pares são clientes e servidores.

### Diferenças entre arquitetura Par-a-Par e Cliente-Servidor

| Par-a-Par                                                    | Cliente-Servidor                                             |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| A informação está distribuída                                | A informação fica concentrada                                |
| Conecta-se através de uma rede                               | Conecta-se através de um servidor                            |
| A transferência de informações estará sempre ativa, pois possui vários nós na rede | Quando um servidor está inoperante, as solicitações dos clientes não podem ser satisfeitas |
| Não requer clientes e servidores fixos                       | Requer um servidor e um cliente pelo menos                   |
| Não há nós com funções especiais, ou seja, todos os nós são iguais ou podem ter as mesmas funções | As funções são limitadas para o servidor e para cada cliente |

[![img](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/images/scalability.png)](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/arquitetura.html#)

### Redes Sobrepostas

É uma rede de computadores construída sobre outra rede. Sistemas p2p utilizam redes sobrepostas, que são criadas na camada de aplicação, sobre as redes físicas. Os nós em uma rede de sobreposição são conectados por links virtuais/lógicos, por meio de muitos links físicos na rede subjacente. Redes sobrepostas são usadas para encontrar e reconhecer os pares para tornar a rede p2p independente da topologia da rede física. Quando existe uma conexão entre dois pares, diz-se que existe uma aresta entre eles, o gráfico contendo todos os pares ativos e as arestas entre eles compõem a rede de sobreposição.

Redes sobrepostas são divididas em:

- Redes Não Estruturadas
- Redes Estruturadas

[![img](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/images/Overlay_p2p.jpg)](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/arquitetura.html#)



### Redes não estruturadas

As redes não-estruturadas não possuem uma estrutura definida na rede de sobreposição e não usam algoritmos específicos para organizar as conexões da rede. Cada nó estabelece conexões aleatoriamente entre outros nós.

[![img](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/images/P2P-N%C3%A3o-Estruturados_adaptado.jpg)](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/arquitetura.html#)

| Vantagens                                                    | Desvantagens (Sistema de busca por inundação)            |
| :----------------------------------------------------------- | :------------------------------------------------------- |
| Simplicidade: São fáceis de construir                        | A requisição de dados causa muito tráfego de sinalização |
| Permitem otimizações em diferentes regiões da sobreposição   | Não garante a busca do conteúdo pesquisado               |
| Altamente robustas devido as altas taxas de “rotatividade” dos pares na rede |                                                          |

Existem três tipos de redes não estruturadas:

- P2P pura: Uma arquitetura de rede p2p pura é completamente descentralizada, não há um elemento central (diferentemente do modelo cliente-servidor), apenas uma camada de roteamento, pois todos os nós possuem papel equivalente, como visto anteriormente, o sistema de busca é por inundação, que gera certas desvantagens. No entanto, aplicações P2P “puras” são raras. A maioria das arquiteturas P2P é híbrida, utilizando alguns elementos centralizadores na execução de tarefas cujo desempenho é crítico.
  Exemplo:Gnutella,Freenet.
- P2P híbrida: Nesse tipo de arquitetura existem alguns nós especiais, chamados de supernós. Supernós concedem o ingresso dos nós na rede, indexam os recursos compartilhados pelos nós e liberam a busca por estes recursos. Quando localizado um determinado recurso pode ser obtido a partir da interação direta entre os nós. Uma falha em um supernó pode ser tolerada elegendo dinamicamente outro supernó.
  Exemplo: Kazza e Bittorrent.
- P2P centralizada: São redes híbridas, mas também possuem servidores centrais que controlam as entradas e saídas de nós na rede. Os nós registram no servidor central os recursos que compartilharão na rede. As pesquisas por recursos disponíveis nos pares são executadas pelo servidor central, o servidor prove banda e processamento, enquanto o acesso aos recursos é efetuado diretamente entre os pares (transferência de dados é P2P).
  Exemplo: eMule, Napster.

Exemplos de protocolos P2P não estruturados: Gnutella, Gossip, Kazaa.

### Redes Estruturadas

As redes estruturadas usam algoritmos e critérios específicos para organizar as conexões da rede. Possuem protocolos que garantem que qualquer nó possa encaminhar uma busca a outro nó que dispõe do arquivo desejado. O procedimento mais utilizado é usando o protocolo DHT (Distributed Hash Tables), ele organiza os processos através de uma tabela hash distribuída. O DHT garante que qualquer nó pode eficientemente buscar na rede um recurso ou arquivo, mesmo quando esse dado recurso é muito raro.



### Distributed Hash Table (DHT)

Esta classe de sistema distribuído, diferentemente das demais, oferece uma forma de roteamento mais estruturada de modo a obter tanto descentralização quanto eficiência. Uma DHT é particularmente útil quando deseja-se criar um banco de dados distribuído de modo a alcançar maior escalabilidade.

Isso é feito distribuindo-se pares de chaves e valores *(key, value)* entre os nós da rede de maneira que cada nó tenha posse de apenas um pequeno subconjunto da dupla (chave, valor). Qualquer nó na rede pode realizar uma consulta no banco de dados com uma chave. O banco de dados localizará os nós que possuem o par (chave, valor) correspondente e retorná a informação para o nós que iniciou a consulta.

...

**Circular Distributed Hash Table**

To be continued...





## Algoritmos e Modelos

### Diretório Centralizado

Um modelo em que os pares se conectam a um diretório central onde publicam informação sobre o conteúdo que oferecem para compartilhar e que se tornou popular com o Napster (serviço de música online P2P, encerrado em 2002). Quando um nó realiza um pedido, o diretório central responde associando o pedido ao melhor nó no diretório que o corresponde. Para definir qual o melhor nó é usada uma métrica que pode levar em conta o custo, a velocidade ou a disponibilidade. Por requerer o servidor do diretório para fins de gerenciamento (hospedar informação dos participantes), esse modelo pode ser classificado como em uma rede híbrida. Sendo assim, é evidente um problema de escalabilidade pois a medida que o número de usuários aumenta são necessários servidores maiores.

[![img](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/images/centraldirectory.png)](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/arquitetura.html#)



### Busca por Inundação

Diferentemente do modelo do Diretório Centralizado, esse é um modelo que pode ser considerado P2P puro. Isso significa que não há um sistema central de gerencialemtno que anuncia o compartilhamento de recursos. A busca por determinado arquivo é feita enviando um mensagem a todos os nós adjacentes. Esses nós adjacentes também enviam uma mensagem aos demais nós conectados a eles e assim por diante até obterem uma resposta positiva ou um número máximo de saltos (TTL). Embora não seja muito eficiente se o objetivo é alcançar todos os nós na rede ou obter conteúdo raros, este modelo mostra-se eficaz em comunidades menores.

[![img](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/images/floodrequest.png)](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/arquitetura.html#)



### Roteamento de Documento

Trata-se de uma abordagem mais recente, adotada por aplicações como FreeNet (uma plataforma par-a-par de comunicação anticensura). Este modelo funciona atribuindo um ID aleatório a cada par presente na rede e garantindo que cada par saiba o número de alguns outros pares. Um documento ou arquivo compartilhado na rede também tem um ID atribuído a si baseado em um código *Hash* do seu nome e conteúdo. O arquivo será roteado por cada par para aquele que possui ID com maior semelhança ao ID do arquivo. Este processo de roteamento é repetido até que o arquivo "chegue" ao par de ID mais próximo. É importante destacar que a cada operação de rotamento é reservada uma cópia local do arquivo.

O processo de busca é análogo ao de armazenar um arquivo recém compartilhado na rede. Isto é, o pedido é direcionado ao par com ID mais próximo do ID do arquivo desejado. Isto é repetido até que o arquivo seja encontrado e enviado ao nó que realizou o pedido. Um detalhe a ser observado é que uma cópia local do arquivo é mantida em cada par particpante do roteamento. No entanto, o fato de ser necessário saber o ID do documento antemão torna a busca mais complicada do que no modelo de inundação por exemplo.

[![img](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/images/documentrouting.png)](https://www.gta.ufrj.br/ensino/eel878/redes1-2018-1/trabalhos-v1/p2p/arquitetura.html#)



### Tit-for-Tat

Em protocolos como BitTorrent é usado um mecanismo de incentivo conhecido como "Tit-for-Tat". Quando um par seleciona a quem enviar pedaços do arquivo, é realizada uma medição da taxa em que recebe pacotes de outros nós. Com esta informação em mãos, esse par prioriza os nós que mais contribuem com o seu download. Se os pares estiverem satisfeitos com o compartilhamento, eles colocaram cada um no top de suas listas e continuarão trocando dados até que algum dos pares ache um parceiro melhor.