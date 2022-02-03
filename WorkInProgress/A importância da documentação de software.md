# A importância da documentação de software

- agosto 9, 2019

  

Antes dos sumérios desenvolverem a escrita, por volta de 3500 a.C., a maneira de transmitir o conhecimento era oral.

Quando o transmissor falecesse, ficaria a cargo dos ouvintes continuar a transmitir. Caso acontecesse alguma fatalidade com aquele povo, o conhecimento deixaria de existir.

Infelizmente, várias empresas do *século XXI* têm o mesmo problema de povos da pré-escrita.

A informação de sistemas complexos, aliada a códigos com grande débito técnico, é transmitida por via oral, formando silos de conhecimento em forma de colaboradores.

Quando esses silos estão inacessíveis, fica a cargo dos desenvolvedores fazerem um *trabalho de arqueólogo* e escavar o código, no meio da sujeira, para tentar entender o que as pessoas que o escreveram queriam dizer.

Como resolver esse problema?

**Conteúdo** [ocultar](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#) 

[1 A documentação de software](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#A_documentacao_de_software)

[2 Itens para evitar na documentação de software](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Itens_para_evitar_na_documentacao_de_software)

[2.1 Documentar o óbvio](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Documentar_o_obvio)

[2.2 Documentar sistema legado que não possui testes automatizados](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Documentar_sistema_legado_que_nao_possui_testes_automatizados)

[2.3 Iniciar pela documentação](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Iniciar_pela_documentacao)

[2.4 Sistemas muito simples](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Sistemas_muito_simples)

[3 Documento como oráculo](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Documento_como_oraculo)

[4 Iniciando a documentação de software](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Iniciando_a_documentacao_de_software)

[4.1 Visibilidade](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Visibilidade)

[4.2 Histórico](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Historico)

[5 Quais ferramentas usar para documentar o software?](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Quais_ferramentas_usar_para_documentar_o_software)

[6 A documentação técnica](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#A_documentacao_tecnica)

[6.1 API’s que serão utilizadas por outros devs.](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#APIs_que_serao_utilizadas_por_outros_devs)

[6.2 Regras muito complexas](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Regras_muito_complexas)

[6.3 Aplicação com execução paralela](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Aplicacao_com_execucao_paralela)

[7 Em conclusão](https://blog.geekhunter.com.br/qual-e-a-importancia-da-documentacao-de-software/#Em_conclusao)

## A documentação de software

![estante com pasta de documentos](https://geekblogti.wpengine.com/wp-content/uploads/2019/08/A-documenta%C3%A7%C3%A3o-de-software.jpg)

Alguns dizem que *software* bem escrito não precisa ser documentado.

Creio que boa parte disso é verdade, mas mesmo que um software possua uma ótima arquitetura e fortes laços com técnicas *clean cod*e, apenas os *devs* têm o controle do fonte e conhecimento em traduzir para uma linguagem de alto nível.

Além de fazer um esforço muito grande, isso cria um gargalo desnecessário e em algumas situações pode não ser o ideal.

Documentar o *software* faz parte do desenvolvimento do produto, mesmo em metodologias ágeis, que trazem no seu manifesto:

> *Working software over comprehensive documentation* .

Não significa que não devemos documentar, mas sim criar documentos cujo esforço de criar — e muito importante, atualizar — seja menor do que o valor que ele entregará.

Isso vai contra metodologias mais antigas, como o cascata.

E que valores são esses? Vale a pena realmente criar documentos? Como costumo ouvir na área da computação: depende!

A resposta não é simples e não costuma ser fácil. O que tem que ser feito é avaliar e balancear o peso da importância dessa documentação.

Como escrevi no parágrafo acima, se o valor atribuído é maior que que o custo de manter, vá em frente e abra uma discussão para começar a escrever. 😄

***>>Leitura Recomendada:\****
A importância da* [***comunicação em Projetos de TI\***](https://geekblogti.wpengine.com/a-importancia-da-comunicacao-em-projetos-de-ti/)

## Itens para evitar na documentação de software

![placas escrito wrong way](https://geekblogti.wpengine.com/wp-content/uploads/2019/08/Itens-para-evitar-na-documenta%C3%A7%C3%A3o-de-software.jpg)

Agora listarei alguns itens muito importantes de serem evitados para fazer seu trabalho da melhor forma possível:

### Documentar o óbvio

Documentar algo apenas por ficar bonito na página principal da wiki da empresa não irá valer a pena, não irá agregar valor e será mais uma informação para manter (ou esquecer).

### Documentar sistema legado que não possui testes automatizados

Um sistema legado pode ter muito código escondido e pode se tornar difícil identificar o comportamento usando testes exploratórios.

Podemos ter pessoas escrevendo uma documentação por semanas para o *software* e o cliente cair em um ponto, devido a um caminho que não tenha sido explorado e fugiu do conhecimento dos especialistas de produto.

Esse processo funciona melhor se tiver andando em paralelo a um processo de refatoração.

Refatorando o código há descobertas de caso de uso que, devido ao tempo do software, falta de documentação e rotação da equipe, pode ter feito o conhecimento se perder.

***>>Leitura Recomendada:\****
[Guia completo] Como*[ ***lidar com software legado\***](https://geekblogti.wpengine.com/lidando-com-codigo-legado/)*?*

### Iniciar pela documentação

Gerar documentação inicial pode ser um grande problema. A ideia inicial, até o fim da concepção, pode pivotar de tantas maneiras que irá demandar alto esforço para manter a documentação atualizada, ou até ser completamente descartada e refeita do zero.

Então, opte por documentar na entrega. Uma observação que faço é a **documentação de funcionalidade** no fim da entrega, e não **documentação de necessidade,** essa sim precisa ser feita antes do desenvolvimento.

### Sistemas muito simples

Possui poucas funcionalidades e é possível transmitir o entendimento durante a pausa para o café? Provavelmente não será utilizado como consulta e cairá no esquecimento.

## **Documento como oráculo**

![tela de computador com codigos de programacao](https://geekblogti.wpengine.com/wp-content/uploads/2019/08/Documento-como-or%C3%A1culo.jpg)

Suporte ao cliente, especialistas de produto e tecnologia utilizam a mesma fonte de informação para entender como o *software* funciona e como os casos de uso e regras de negócio fluem pelo sistema.

O documento *se torna o oráculo*, aquele que possui todas as respostas do produto, além de ser a última palavra e o guia estratégico para a empresa.

Sem isso, o código-fonte e pessoas com muito tempo de empresa é que acabam *virando o oráculo*.

Pessoas como oráculo são um problema porque dependemos de sua disponibilidade de responder, gerando um gargalo problemático, considerando que elas tem seus afazeres;

Além disso, também podem estar ausentes por motivo de férias, doença e licença.

Ou o pior dos casos: quando essas pessoas saem da empresa, levando todo o conhecimento embora, gerando enormes problemas e gastos.

O código-fonte como oráculo também pode ser um problema. Agora o gargalo é outro: o programador.

Quando o programador precisa parar o que está fazendo, abrir o código, pesquisar no código-fonte e traduzir para a linguagem de negócio o que o desenvolvedor deve fazer, as chances de cair num buraco ainda pior que o caso de pessoas como oráculo é altíssima.

[![img](https://geekblogti.wpengine.com/wp-content/uploads/2019/08/CTA-Rodap%C3%A9-Front-end-e-Back-end-5-1024x134.jpg)](https://bit.ly/2JS9hZn)

## Iniciando a documentação de software

![telas de computador com codigos de programacao](https://geekblogti.wpengine.com/wp-content/uploads/2019/08/Iniciando-a-documenta%C3%A7%C3%A3o-de-software.jpg)

Antes de iniciar documentação, você precisa ter em mente pontos muito importantes:

### Visibilidade

Tornar o *software* público. Todos devem estar cientes da sua existência, incentivar seu uso e ele deve ser fácil de navegar.

Esses são requisitos para fazer o software funcionar e não deixá-lo esquecido.

### Histórico

Criar um histórico traz uma maneira fácil de evoluir e manter rastreabilidade, permitindo fazer pequenas evoluções, obter *feedback* de interessados e aplicar novas melhorias, até que os envolvidos estejam perfeitamente satisfeitos.

Ferramentas de versionamento, como o Git, são uma possibilidade.

***>>Leitura Recomendada:**
*[***Git, SVN ou CVS***](https://geekblogti.wpengine.com/git-svn-e-cvs-comparacao-dos-principais-vcs/) *— comparação dos principais VCS*

## **Quais ferramentas usar para documentar o software?**

![codigos de programacao](https://geekblogti.wpengine.com/wp-content/uploads/2019/08/Quais-ferramentas-usar-para-documentar-o-software.jpg)

O objetivo desse artigo não é descrever as ferramentas mais utilizadas. Porém, algumas muito utilizadas que você pode pesquisar mais sobre são: história de usuário, mindmaps, diagrama de contexto, entre outras.

Não precisa utilizar exclusivamente uma, a sua documentação pode ser composta por várias, porém a **fonte de informação deve ser única**.

Usar mais de uma fonte pode causar divergências e/ou conflitos de regras de negócio. Várias ferramentas podem expor tipos de visões de uma funcionalidade definida de uma fonte, nunca ao contrário.

***Leitura Recomendada\****:
***[\*Introdução ao Flutter\*](https://geekblogti.wpengine.com/introducao-ao-flutter-o-framework-do-google/)***, o framework da Google*

## **A documentação técnica**

![mesa com planilhas jornais calculadora um notebook e uma xicara de cafe](https://geekblogti.wpengine.com/wp-content/uploads/2019/08/A-documenta%C3%A7%C3%A3o-t%C3%A9cnica.jpg)

E quanto a documentação técnica, existe algum ponto que um código bem escrito não é o suficiente?

Eu acredito que um código que expressa sua intenção através de código limpo e arquitetura bem definida deve ser suficiente, na maioria das vezes.

Existem, porém, 3 pontos em que documentação pode ser complementar, documentando em alto nível para suprir a pilha de contexto necessário. São eles:

### **API’s que serão utilizadas por outros devs.**

#### Documentação para uso de biblioteca/framework

Documentar a utilização de biblioteca atinge um público específico: desenvolvedores. É comum existir exemplos de código-fonte e uso de muitos termos técnicos.

Geralmente, a **API** não é suficiente para contextualizar o seu comportamento e uso.

Assim, desenvolvedores escrevem documentação de instalação, configuração, arquitetura implementada e exemplos de uso de determinados casos, para diminuir a curvatura de aprendizagem e engenharia reversa como forma de aprendizado.

Aqui você pode checar a utilização de [**documentação técnica de um framework**](https://doc.networknt.com/documentation/) (no qual eu sou contribuidor).

#### Documentação para APIs remotas

Documentar para APIs remotas, que hoje são em maioria composta por webservices, entra no mesmo público que o caso anterior: desenvolvedores.

**Webservice** e **AP**I são um tipo de interface, não possuem visual gráfico e nem usabilidade aplicada a componentes gráficos, ou seja, não há apelo gráfico para demonstrar como utilizar!

Mesmo utilizando protocolos bem definidos, como o *REST, RPC, GraphQL*, é necessário construir uma documentação para os clientes saberem como consumir e interagir.

Principalmente quando o cliente é externo à empresa, não está contextualizado e nem possui a mesma cultura.

Para *APIs* do protocolo *REST*, existe uma especificação bastante conhecida, chamada de *OpenAPI*, que define um conjunto de regras para documentá-la.

### **Regras muito complexas**

Alguns processos possuem muitas *subtarefas* a serem executadas. Com isso, é quase impossível expor de maneira oral — ou mesmo através de códigos — uma visão do processo.

Nesse ponto uma documentação em alto nível pode cair como uma luva. Um bom exemplo é diagrama de atividades ou estado de máquina.

Eles podem expor visualmente as etapas, de uma forma intuitiva e com maior facilidade e melhor absorção do conhecimento.

***>>Leitura Recomendada:\****
Leia nosso artigo sobre as* [***melhores extensões para o Microsoft Visual Studio\***](https://geekblogti.wpengine.com/as-melhores-extensoes-para-o-microsoft-visual-studio/)

### **Aplicação com execução paralela**

Aplicações com execuções paralelas (*multi-thread*) são difíceis de testar e a complexidade para entender é proporcionalmente direta.

Ela está diretamente ligada com o item acima, mas achei melhor criar um parágrafo novo pela possibilidade de tomar decisões um pouco diferentes.

Por se tratar de complexidade, uma documentação de alto nível — como diagrama de atividades com componentes para apresentar fluxos paralelos — também será necessária.

Porém, podemos usar uma abordagem um pouco diferente, como utilizar linguagens de especificações formais, tal qual [TLA](https://learntla.com/introduction/)+.

Apesar de ter uma curvatura de aprendizagem um pouco alta, por causa de conceitos da matemática envolvidos, essa é uma ótima ferramenta para documentar e testar a integridade do modelo em busca de bugs.

[![img](https://geekblogti.wpengine.com/wp-content/uploads/2019/08/CTA-Rodap%C3%A9-Front-end-e-Back-end-6-1024x134.jpg)](https://bit.ly/2JS9hZn)

## Em conclusão

![mesa com maquina de escrever um caderno oculos](https://geekblogti.wpengine.com/wp-content/uploads/2019/08/Em-conclus%C3%A3o-1.jpg)

Documentar pode ser uma excelente ferramenta, quando mantida atualizada e ao alcance de todos.

Mais uma dica é: Caso a atualização seja feita de forma manual, você pode criar gatilhos e incorporá-los ao processo de desenvolvimento.

Por exemplo: Criar um *ticket* de atualização do documento ao finalizar e um *ticket* de criação ou atualização de funcionalidades.

Se quiser aprofundar o [**conhecimento sobre documentação**](http://www.agilemodeling.com/essays/agileDocumentationBestPractices.htm), esse link possui um excelente conteúdo sobre o tema.

Até a próxima!

![img](http://s3.amazonaws.com/blog-geek-midia/wp-content/uploads/2019/01/21164829/perfil.jpeg)

[Jeferson Perito](https://blog.geekhunter.com.br/author/jeferson-perito/)