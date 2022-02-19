[Skip to content](https://engenhariasoftware.wordpress.com/#content)



# [Engenharia de Software](https://engenhariasoftware.wordpress.com/)

Este blog tem como meta apresentar algumas discussões e opiniões relacionadas a engenharia de software. O blog foi criado pelo professor José Augusto Fabri da Universidade Tecnológica Federal do Paraná em 2008. Espero que vocês aproveitem os textos aqui apresentados.

# [ESG! O que significa? Será que traz grandes revelações?](https://engenhariasoftware.wordpress.com/2021/07/21/esg-o-que-significa-sera-que-traz-grandes-revelacoes/)

Pessoal, espero que todos estejam bem!

Neste semestre (2021-1) ouvi muito sobre ESG. 

O conceito foi criado em 2004 durante Pacto Global, evento liderado pelo Banco Mundial. Três palavras da língua inglesa compõe a sigla:

- Environmental 
- Sustainability
- Governance

A ideia é aplicar esse conceito dentro de organizações estruturadas ou empresas. Essas organizações não devem pensar no lucro somente, aspectos ligados a adequação ambiental, sustentabilidade e governança devem ser considerados no *core* da gestão.

Além do ROI (Retorno Sobre o Investimento) e da sustentabilidade financeira, a empresas devem ter como métrica:

**O Ambiente**

Para que essa métrica seja atingida a empresa deve responder positivamente algumas questões: 

1. A organização usa recursos naturais e os repõe? 
2. Não emite gás que provoca o efeito estufa? 
3. Prima pela eficiência energética? 
4. Evita poluição e realiza gestão de resíduos? 

Todas as questões levantadas nessa métrica podem ser compactadas em uma: Como a empresa lida com o meio ambiente? 

**A Sociedade**

Para que essa métrica seja atingida a empresa deve responder positivamente algumas questões:

1. Os colaboradores recebem um pagamento justo e digno?
2. Não considera em hipótese alguma a mão de obra escrava?
3. Não considera em hipótese alguma a mão de obra infantil?
4. Prevê a inclusão dos grupos discriminados?
5. Prima pela diversidade?
6. Possui aproximação com a comunidade local?

Todas as questões levantadas nessa métrica podem ser compactadas em uma: Como a empresa se relaciona com os seus colaboradores?

**A Governança**

 Para que essa métrica seja atingida a empresa deve responder positivamente algumas questões:

1. A empresa possui um conselho deliberativo independente?
2. Ela prima pela ética e transparência?
3. A remuneração dos gestores (CEOs, CIOs) não extrapolam?
4. Existe inclusão e diversidade na Gestão (CEOs, CIOs)?
5. Aspectos ligados a processo, planejamento, gestão são amplamente considerados na estrutura organizacional?

Todas as questões levantadas nessa métrica podem ser compactadas em uma: Como a empresa se relaciona com a sociedade?

Veja quem investiu em em ESG no mundo entre 2016 e 2018(Fonte: Inovação e ESG, da consultoria ACE Cortex).

- Japão: aumento de 307%;
- Austrália: aumento de 46%;
- Canadá: aumento de 42%;
- Estados Unidos: aumento de 38%;
- Europa: aumento de 11%;

No Brasil cerca de 50% das grandes empresas se preocupam com o ESG. E em uma pesquisa com os consumidores brasileiros é possível considerar que 87% prefere comprar de uma empresa sustentável e 70% não se importam em pagar um pouco a mais por isso.

Para finalizar afirmo que o conceito ESG não revela nada de novo. Algo que todos nós devemos internalizar no nosso processo de **EDUCAÇÃO**. 

**RESPEITO AO MEIO AMBIENTE**

**RESPEITO AO PRÓXIMO**

**ÉTICA E TRANSPARÊNCIA**

Nome novo para algo que já pregamos (ou deveríamos pregar) há muito tempo.

por José Augusto Fabri

Posted on [July 21, 2021](https://engenhariasoftware.wordpress.com/2021/07/21/esg-o-que-significa-sera-que-traz-grandes-revelacoes/) by [José Augusto Fabri](https://engenhariasoftware.wordpress.com/author/engenhariasoftware/)Posted in [off topic](https://engenhariasoftware.wordpress.com/category/off-topic/)[Leave a comment](https://engenhariasoftware.wordpress.com/2021/07/21/esg-o-que-significa-sera-que-traz-grandes-revelacoes/#respond)

# [É possível customizar uma métricas de software tradicional?](https://engenhariasoftware.wordpress.com/2021/07/19/e-possivel-customizar-uma-metricas-de-software-tradicional/)

Uma excelente questão apresentada no título deste post.

Verifique o posicionamento de alguns profissionais da área de engenharia de software.

Apenas 26,3% acreditam que sim.

![Gráfico de respostas do Formulários Google. Título da pergunta: Eu posso alterar o peso do ALI na complexidade baixa de 7 para 15?. Número de respostas: 19 respostas.](https://lh5.googleusercontent.com/B3S1gCdmUQsJKGKhwTZuuCNEH25_70BJBIiS0HV-kcJ5ccV6Pq_QkusBNaBbmdeKRf1TtylQRzaO19Aq7PA4dNdId64D16JdNBZm6tNGFs135gZ7bQ1DZfeipfBhMMbAGxpoSgMk)

Para respondê-la, vamos apresentar formalmente duas métricas tradicionais:

1. Pontos por Função
2. Pontos por Caso de Uso

A técnica para mapear a complexidade de um software por Pontos de Caso de Uso foi proposta em 1993 por Gustav Karner. Ela é baseada em duas outras técnicas – Pontos de Função e o Mk II (adaptação da técnica dos pontos por função, comumente utilizada pelos ingleses). A técnica mapeia a complexidade dos atores e dos casos de uso. Aprofunde-se nessa métrica por meio deste [link](https://engenhariasoftware.wordpress.com/2013/08/28/aplicando-os-pontos-por-caso-de-uso-para-mapear-a-complexidade-de-um-software/).

Pontos por Função é uma das técnicas (ou métodos) que proporcionam estimar a complexidade de um software. Formalmente, FPA é caracterizado como um método que busca medir a complexidade de um software pela quantificação das funcionalidades. É importante ressaltar que tal método foi criado em 1974 pela IBM e foi, posteriormente, desenvolvido por Caper Jones e pelo International Function Point Users Group. Você encontra mais informações sobre Pontos por Função neste [link](https://engenhariasoftware.wordpress.com/2013/04/09/tutorial-sobre-pontos-por-fucao/).

Após a definição de duas métricas tradicionais da área de engenharia de software, vamos a customização customização de uma delas.

Vamos partir da métrica de pontos por função, mais precisamente dos Arquivos Lógicos Aritméticos – os ALIs. Na métrica em questão um arquivo nativo da aplicação é classificado dentro de 3 parâmetros:

- Complexidade Baixa;
- Complexidade Média;
- Complexidade Alta.

Os parâmetros de complexidade são mapeados a partir da quantidade de campos, presente no arquivo, e da forma de organização das tuplas (ou linhas) que os compõem. Quanto maior o número de campos e quanto maior as formas de organização das tuplas, mais complexo é o arquivo. Veja só:

Arquivos que possuem a quantidade de campos entre 1 a 19 e uma forma de organização de registro (ou tupla) possuem uma complexidade baixa.

Arquivos que possuem a quantidade de campos entre 20 a 50 e uma forma de organização de registro (ou tupla) possuem uma complexidade baixa.

Arquivos que possuem mais de 50 campos e uma forma de organização de registro (ou tupla) possuem uma complexidade média.

Para conferir toda a complexidade dos arquivos, das entradas, das saídas e das consultas você pode consultar essa [planilha](https://www.dropbox.com/s/6kvtt5uwlag71bg/fpaCocomo.xls?dl=0).

Você pode alterar as faixas para mapeamento da complexidade, sempre respeitando os parâmetros de sua base histórica de projetos. Uma proposta:

Arquivos que possuem a quantidade de campos entre 1 a 9 e uma forma de organização de registro (ou tupla) possuem uma complexidade baixa.

Arquivos que possuem a quantidade de campos entre 10 a 20 e uma forma de organização de registro (ou tupla) possuem uma complexidade baixa.

Arquivos que possuem mais de 20 campos e uma forma de organização de registro (ou tupla) possuem uma complexidade média.

Perceba que você está mexendo na linha 8 da [planilha](https://www.dropbox.com/s/6kvtt5uwlag71bg/fpaCocomo.xls?dl=0).

Para finalizar nossa resposta. É possível customizar uma métricas de software tradicional desde que você tenha parâmetros em sua base histórica de projetos muito bem definidos. Para ter parâmetros bem definidos é necessário possuir um processo de software institucionalizado. 

Mas lembre-se de uma premissa, quando você tiver que participar de uma concorrência ou licitação para vender um software, e essa licitação estabelecer como métrica pontos por função, você deverá utilizar a forma tradicional da métrica.

Fica uma provocação: Vamos criar uma métrica de software para sua empresa? A sua métrica!

por José Augusto Fabri – fabri@utfpr.edu.br

Posted on [July 19, 2021](https://engenhariasoftware.wordpress.com/2021/07/19/e-possivel-customizar-uma-metricas-de-software-tradicional/) by [José Augusto Fabri](https://engenhariasoftware.wordpress.com/author/engenhariasoftware/)Posted in [gestão de projetos](https://engenhariasoftware.wordpress.com/tag/gestao-de-projetos/)[Leave a comment](https://engenhariasoftware.wordpress.com/2021/07/19/e-possivel-customizar-uma-metricas-de-software-tradicional/#respond)

# [A relação entre analista de sistemas e usuários. DevOpS! Correto?](https://engenhariasoftware.wordpress.com/2021/06/22/a-relacao-entre-analista-de-sistemas-e-usuarios-devops-correto/)

Nós engenheiros de software, analistas de sistemas e desenvolvedores sempre proclamamos a ideia de termos uma relação próxima entre nós e nossos usuários – as (pessoas que manipulam e usam o software). Essa relação, atualmente é chamada de DevOpS.

Vários autores classificam DevOps como uma cultura que aproxima DEsenVolvedores de software (Dev) e os OPeradores de Software (OpS). A ideia central é proporcionar uma comunicação mais clara entre os papéis supracitados. Trabalhar com a automação e monitoramento em todas as fases da construção de software também é algo defendido por vários autores. 

**Novamente, ressalto que DevOpS é um nome novo para algo que já fazemos há anos.**

A aproximação entre Desenvolvedores e Usuários proporciona a liberação de pacotes de software com o alinhamento mais próximo com os objetivos do negócio da organização. Fato este preconizado pela engenharia de software.

Automatizar o processo de produção de software, capturando as informações sobre a construção do produto também preconizado pelas velhas Fábricas de Software da Década de 1960, fato explicitado por Cusumano em sua obra Japans Software Factories. 

Por fim, às vezes acreditamos que estamos usando um conceito inovador dentro do ambiente produtivo, porém se formos a fundo nos pressupostos da engenharia de software, o conceito já é usado com sucesso há tempos. 

Fica a dica!

por José Augusto Fabri – [fabri@utfpr.edu.br](mailto:fabri@utfpr.edu.br) 

**Referências**

Engenharia de Software. [http://www.dimap.ufrn.br](http://www.dimap.ufrn.br/). Consultado em 26 de julho de 2019.

Pant, Rajiv (17 de março de 2009). Organizing a Digital Technology Department of Medium Size in a Media Company

Samovskiy, Dmitriy (2 de março de 2010). The Rise of DevOps. Fubaredness Is Contagious. Consultado em 19 de março de 2013. 

Posted on [June 22, 2021](https://engenhariasoftware.wordpress.com/2021/06/22/a-relacao-entre-analista-de-sistemas-e-usuarios-devops-correto/) by [José Augusto Fabri](https://engenhariasoftware.wordpress.com/author/engenhariasoftware/)Posted in [Ensino de engenharia de software](https://engenhariasoftware.wordpress.com/category/ensino-de-engenharia-de-software/)[Leave a comment](https://engenhariasoftware.wordpress.com/2021/06/22/a-relacao-entre-analista-de-sistemas-e-usuarios-devops-correto/#respond)

# [Refinement Scrum](https://engenhariasoftware.wordpress.com/2021/06/06/refinement-scrum/)

Pessoal, nessa semana recebi diversas dúvidas sobre *Grooming* Scrum. Neste *post* vou definir a referida técnica, apresentar um processo simples e elegante que proporciona a qualquer profissional da área de processos e executar essa técnica. Importante, eu vou apresentar, eu não vou descrever, institucionalizar o processo.

Antes de iniciar a definição é necessário substituirmos o termo *Grooming* por **Refinement**. *Grooming* na nossa língua portuguesa receba a tradução de aliciamento de crianças na Internet.

**Refinement** é definido como o ato de preparação de sua **Product Backlog** (**PB**). Lembre-se que a **PB** se caracteriza como tudo aquilo que você necessita executar para construir um determinado produto. Na Engenharia de Software, a **PB** acondiciona as características ou requisitos de um determinado Software.

Eu, particularmente, relaciono o ato de preparação com o ato de cuidar. Isso mesmo, cuidar. O cuidado com algo ou alguém remete a ideia de zelo e proteção. Neste caso o **Refinement** se refere ao zelo com as características ou requisitos de seu produto de software.

Diante do contexto apresentado, podemos elencar algumas questões para serem respondidas:

I – Como proteger e zelar a sua **PB**?

O zelo e a proteção nesse caso refere-se ao entendimento, detalhamento (componentização), descoberta (e não especulação) de novos itens e estimativas de tempo de produção de um determinado requisito de software.

II – Existem boas práticas para proteger e zelar a sua **PB**? Existem boas práticas para implementar o **Refinement**?

Não existe uma fórmula pronta para implementar o **Refinement** durante a construção de um software, podemos elencar aqui algumas ações que executamos dadas as características de projetos que gerenciamos. Vamos a elas:

1. Priorize: Reúna o **Scrum Team** e o **Product Owner**. A reunião tem como pauta a priorização dos requisitos. O que deve ser implementado primeiro? O que é mais importante? Qual a relação de dependência dos requisitos? É possível quebrar essa relação de dependência?

1. Componentize: **Scrum Team** e **Product Owner (PO)** devem ter a capacidade de dividir as grandes pedras e pedras menores. Certamente será muito mais fácil carregar pedras menores durante a **Sprint**. O saciamento da sede da equipe de usuários também será melhor gerenciada com as entregas constantes. Você pode utilizar o velho e bom diagrama de componentes proposto, nas décadas de 1970 e 1980, pelo Edward Yourdon. 

1. Descubra: Isso mesmo, descubra novos itens, novas características, novos requisitos de software. Eu escrevi **descubra,** eu não escrevi especule. Durante o processo de componentização você pode descobrir junto ao **PO** novos componentes de software. Quando partirmos para uma maior granularidade, vamos percebemos características que não tínhamos percebido antes.

1. Estime: Qual é o tempo e esforço para a construção de um determinado componente? Qual é o tempo e esforço para executar um determinada **Sprint**? Você consegue responder essas questões com uma base histórica de projetos institucionalizada. Já publiquei vários textos dentro deste tema no *blog*.

O processo apresentado é simples e não traz nenhuma inovação conceitual para a engenharia de software. Priorizar, Componentizar, Descubrir requisitos e Estimar tempo e esforço já é realizado pelos Engenheiros de Software a décadas. Neste caso, no meu ponto de vista, **Refinement** é um termo novo na boa e “**velha**” Engenharia de Software. 

por José Augusto Fabri – fabri@utfpr.edu.br



Posted on [June 6, 2021](https://engenhariasoftware.wordpress.com/2021/06/06/refinement-scrum/) by [José Augusto Fabri](https://engenhariasoftware.wordpress.com/author/engenhariasoftware/)Posted in [Papo de Empresa](https://engenhariasoftware.wordpress.com/category/papo-de-empresa/), [processo de produção de software](https://engenhariasoftware.wordpress.com/category/processo-de-producao-de-software/)[Leave a comment](https://engenhariasoftware.wordpress.com/2021/06/06/refinement-scrum/#respond)

# [A Atividade de Refactoring](https://engenhariasoftware.wordpress.com/2021/05/04/a-atividade-de-refactoring/)

Embora esta atividade proponha apenas exercitar o refactoring de um código feito por outra pessoa e expor a experência, eu gostaria de expor uma ocasião real que tive quando trabalhei como programador para um projeto especifico.

O projeto era de uma aplicação que pretendia organizar o fluxo de aprovação de novos produtos de uma empresa de cartão de crédito.

Foi escolhido o Lotus Notes/Domino como plataforma, pela facilidade que o software apresentava na criação de sistemas com fluxo, aprovações e integração com sistemas de email.

Eramos 2 programadores, eu (programador1) ficava responsável por criar os módulos, formularios e eventos, enquanto o outro (programador2) era responsavel por acoplar os “objetos” que eu criava no sistema principal. Claro, alteração e refinamento do meu trabalho, era parte da responsabilidade do outro programador.

Então de certa forma, eu entendo que faziamos uma especie de refactoring, já que o meu códio era refatorado imediatamente ao ser implementado no sistema final, portanto listo algumas das caracteristicas do refactoring, que colaboram com a minha afirmação.

**Reestruturação do Código:** a reestruturação do código era inerente neste caso, pois o programador1 nem sempre tinha visibilidade do sistema como um todo, e o programador2 precisava entender o código para acopla-lo no sistema principal.

**Manter o Comportamento:** O programador2, precisava manter o comportamento dos modulos feitos pelo programador1, caso contrário o modulo era devolvido ao programador1 para reescrita.

**Melhorar a Forma e Estrutura:** O programador2 era responsável por adaptar o codigo que recebia ao sistema principal.

**Preservar a funcionalidade:** durante a integração dos modulos novos, o programador2 precisava garantir a preservação das funcionalidade oferecidas originalmente.

**Melhorar a Leitura e manutanção:** O programador1, precisava escrever o código de forma que fosse possivel o trabalho do programador2 sem ajuda, enquanto que o segundo precisava fazer o mesmo ao acoplar no sistema principal.

**Escalabilidade:** Ponto chave na maneira em que trabalhávamos, era importantíssimo que tivessemos esta caracteristica em mente o tempo todo, de outro modo não teria sido possivel aplicar nossa maneira de trabalho.

Concluindo, claro que tivemos momentos de incertezas e problemas no fluxo de nosso trabalho, mas funcionou e nós conseguimos entregar o que foi planejado usando este modelo de trabalho, que no caso foi aplicado por nós por questões logisticas que nos impediam de estar ao mesmo tempo executando este projeto.

por Thomaz Martins – Especialização em engenharia de software.

Posted on [May 4, 2021](https://engenhariasoftware.wordpress.com/2021/05/04/a-atividade-de-refactoring/) by [José Augusto Fabri](https://engenhariasoftware.wordpress.com/author/engenhariasoftware/)Posted in [gestão de projetos](https://engenhariasoftware.wordpress.com/tag/gestao-de-projetos/), [Papo de Empresa](https://engenhariasoftware.wordpress.com/category/papo-de-empresa/)[Leave a comment](https://engenhariasoftware.wordpress.com/2021/05/04/a-atividade-de-refactoring/#respond)

# [Gestão de projetos. Treinamento e Brinquedos.](https://engenhariasoftware.wordpress.com/2021/04/21/gestao-de-projetos-treinamento-e-brinquedos/)

Pessoal, hoje vamos falar de um tema importante que venho estudando há alguns anos, o treinamento em gestão de projetos com a utilização de brinquedos.

O termo brinquedo se caracteriza como um vocábulo do século XIX e sua derivação vem de **brinco ou brincar**. É importante ressaltar que para brincar não necessitamos de um brinquedo ou objeto lúdico – brincar de **pega pega** é um exemplo. Alguns historiadores relacionam o sufixo **edo** com a madeira. A madeira foi utilizada na confecção dos primeiros artefatos que foram utilizados na ação de brincar.

Ao utilizar um brinquedo durante o contato com um determinado conceito abstrato, o aluno pode tornar o processo de aprendizado mais atraente e interessante, gerando uma positividade no desenvolvimento cognitivo. Quando combinamos os brinquedos com as aulas, certamente o processo de absorção do conhecimento pode ser potencializado.

Dado o pressuposto que: Brincar pode ser positivo em um treinamento. Um questionamento surge: Como o aluno pode aprender o conceito de **Gestão de Projetos** a partir da utilização de um brinquedo ou de uma brincadeira?

Vamos tentar responder o questionamento com um exemplo prático.

Vamos trabalhar a **Introdução a Gestão de Projetos** utilizando um brinquedo. Definir as grandes atividades de gestão – **Planejamento**, **Execução** e **Controle de Projetos** – será o nosso foco. Vamos trabalhar também o conceito de **Base Histórica de Projetos** e inserir a técnica **Kanban** dentro de tudo isso.

**A brincadeira e o Brinquedo**

Solicite que cada aluno ou colaborador tenha em mãos 6 folhas de papel sulfite e uma caneta azul ou preta.

Cada aluno ou colaborador deve gerar uma folha Kanban (vide figura abaixo).

Cada aluno ou colaborador deve recortar uma folha com 3 *post-its*. Cada *post-it* deve conter as seguintes informações: Produto a ser gerado, nome, data, tempo planejado e tempo de execução (vide figura abaixo).

Cada aluno ou colaborador vai construir 3 aviões – seguindo as orientações do vídeo abaixo:



Solicite que cada aluno ou colaborador preencha as informações no primeiro *post-it*.

_______________________________

Produto a ser gerado: Avião 1

Nome: José Augusto Fabri

Data: 21/04/2021

Tempo planejado: 4 minutos.

Tempo realizado: Deixe em branco. Essa informação será preenchida somente quando o *post-it* atingir o quadro **pronto**.

_______________________________

Solicite que cada aluno ou colaborador preencha as informações nos próximos post-it.

_______________________________

Produto a ser gerado: Avião 2

Nome: José Augusto Fabri

Data: 21/04/2021

Tempo planejado: Deixar em branco. Essa informação será preenchida com base no **tempo realizado** do primeiro *post-it*.

Tempo realizado: Deixe em branco. Essa informação será preenchida somente quando o post-it atingir o quadro **pronto**.

_______________________________

A Figura abaixo e o vídeo acima apresentam a configuração da brincadeira e a montagem do brinquedo.

[![img](https://engenhariasoftware.files.wordpress.com/2021/04/kanban.png?w=901)](https://engenhariasoftware.files.wordpress.com/2021/04/kanban.png)

**Brincando**

Agora é só brincar seguindo os passos abaixo:

1. Solicite que cada aluno ou colaborador coloque todos os *post-its* no quadro **para fazer**.
2. Assim que o aluno ou colaborador iniciar a construção do primeiro avião ele pode colocar o *post-it* no quadro **fazendo**.
3. Peça para cada aluno ou colaborador marcar o tempo que ele leva para construir o avião.
4. Terminada a construção, cada aluno ou colaborador deve movimentar o *post-it* para o quadro **pronto** e anotar o tempo realizado.
5. Solicite que cada aluno ou colaborador **planeje o tempo de construção** para o próximo avião.
6. Volte ao passo 2.
7. Após construir os 3 aviões, solicite que todos gerem a relação apresentada na tabela abaixo.

| Produto | Nome               | Data       | Planejado     | Realizado     |
| ------- | ------------------ | ---------- | ------------- | ------------- |
| Avião 1 | José Augusto Fabri | 21/04/2021 | 4 minutos     | 3 minutos     |
| Avião 2 | José Augusto Fabri | 21/04/2021 | 3 minutos     | 2m30 segundos |
| Avião 3 | José Augusto Fabri | 21/04/2021 | 2m30 segundos | 2m35 segundos |

**Trabalhando os conceitos**

Agora vamos trabalhar alguns conceitos inerentes a **Introdução a Gestão de Projetos**.

1. Para construir o primeiro avião você fez o planejamento do tempo de construção. Perceba que você não possuía informação alguma sobre a sua capacidade produtiva.
2. No planejamento para a construção do segundo e o do terceiro avião, você utilizou a informação **tempo realizado**. Aqui já podemos abordar a importância de uma base histórica de projetos.
3. Com o Kanban você controla constantemente a execução do projeto. Perceba que na figura acima você possui 1/3 do projeto pronto.
4. A tabela acima já se configura como uma base histórica de projetos. Você pode utilizá-la em um próximo projeto para a construção de novos aviões.

Ah… Para encerrar, achou a construção do avião complexa, pode construir um mais simples.

Por José Augusto Fabri – fabri@utfpr.edu.br

Posted on [April 21, 2021](https://engenhariasoftware.wordpress.com/2021/04/21/gestao-de-projetos-treinamento-e-brinquedos/) by [José Augusto Fabri](https://engenhariasoftware.wordpress.com/author/engenhariasoftware/)Posted in [gestão de projetos](https://engenhariasoftware.wordpress.com/tag/gestao-de-projetos/), [gestão do conhecimento](https://engenhariasoftware.wordpress.com/category/gestao-do-conhecimento/), [Introdução a Engenharia de Software](https://engenhariasoftware.wordpress.com/category/introducao-a-engenharia-de-software/)[Leave a comment](https://engenhariasoftware.wordpress.com/2021/04/21/gestao-de-projetos-treinamento-e-brinquedos/#respond)

# [Business Impact Analysis (BIA)](https://engenhariasoftware.wordpress.com/2021/04/19/business-impact-analysis-bia/)

Pessoal, hoje vamos falar um pouco sobre Análise de Impacto no Negócio.

É importante ressaltar que toda organização pode ser impactada de forma negativa dada a efusão de um evento externo não programado ou dada a tomada de decisão incorreta na modelagem de um processo de negócio. Analisar este impacto e definir ações que minimizem o estrago é de extrema importância dentro de qualquer ambiente de negócio. É aí que entra o Business Impact Analysis (BIA).

Em resumo, a BIA tem como objetivo avaliar os riscos que um determinado projeto pode oferecer à sua organização. Desenvolver uma boa análise de impacto que um projeto pode trazer ao seu negócio pode evitar a execução de procedimentos que apresentem riscos à sua organização. 

Para realizar a Análise de Impacto em seu Negócio sob a luz da execução de um projeto qualquer execute os passos abaixo:

1. Selecione a unidade de negócio e verifique qual projeto você deseja executar dentro daquela unidade.
2. Faça o mapeamento das atividades do projeto que você quer executar.
3. Analise o impacto de cada atividade mapeada no projeto sob a luz de dois prisma:
   - Ocorrência de um evento externo durante a execução da atividade;
   - Problemas de modelagem ou concepção na sua atividade. Se problemas de modelagem ou concepção foram detectados, retorno ao passo 2.

A BIA deve gerar alguns artefatos importantes:

- Processo mapeado.
- Relato dos impactos mapeados.
- Plano de contingência caso algum evento externo ocorra.

Perceba que a BIA depende de diversas ações importantes dentro da atividade de gerenciamento. Destacamos aqui algumas delas:

- Definição do escopo do projeto.
- Mapeamento das atividades e tarefas do projeto.
- Modelagem do projeto em uma linguagem clara, concisa e consistente.
- Análise das variáveis que compõem o ambiente externo.
- Avaliação do projeto modelado.

Para finalizar, a figura abaixo tenta apresentar de forma simples e elegante os 3 passos da Análise de Impacto no Negócio.

[![img](https://engenhariasoftware.files.wordpress.com/2021/04/processo.png?w=824)](https://engenhariasoftware.files.wordpress.com/2021/04/processo.png)

por José Augusto Fabri

Posted on [April 19, 2021](https://engenhariasoftware.wordpress.com/2021/04/19/business-impact-analysis-bia/) by [José Augusto Fabri](https://engenhariasoftware.wordpress.com/author/engenhariasoftware/)Posted in [gestão de projetos](https://engenhariasoftware.wordpress.com/tag/gestao-de-projetos/), [gestão do conhecimento](https://engenhariasoftware.wordpress.com/category/gestao-do-conhecimento/)[Leave a comment](https://engenhariasoftware.wordpress.com/2021/04/19/business-impact-analysis-bia/#respond)

# [O talento que você procura pode estar ao seu lado](https://engenhariasoftware.wordpress.com/2021/04/04/o-talento-que-voce-procura-pode-estar-ao-seu-lado/)

Muitas vezes sou questionado:

Onde posso encontrar um profissional com um perfil X?

Sempre respondo com uma novas questões:

1 – Você já procurou em sua própria empresa ou instituição?

2 – Você já pensou em desenvolver os talentos ou perfis profissionais que necessita dentro da sua própria empresa?

3 – Você possui um mecanismo de gestão de conhecimento que possibilite a construção de uma plataforma de conhecimento?

4 – Você conhece o potencial de seus colaboradores?

Geralmente as respostas para as questões acima são negativas.

A primeira ação que você tem que desenvolver é gerar uma matriz de talentos com seus colaboradores. Procure verificar as suas habilidades e competências para resolver os problemas que a empresa enfrenta.

A segunda ação é construir uma plataforma de talentos. Para isso é necessário que você estabeleça um mecanismo ou processo de gestão de conhecimento dentro da própria empresa. Neste texto vou apresentar rapidamente quais são as etapas para construir este mecanismo que irá derivar na plataforma.

**Etapa 1 – Áreas Chaves**

Faça o mapeamento das áreas chaves da empresa. Quais são as suas células de produção? Quais os principais produtos gerados por estas células? Qual é o diferencial de cada célula? Existem intersecções/relações entre as células? Estas questões podem delinear as áreas chaves dentro de sua organização.

**Etapa 2 – Mapeamento das necessidades da áreas**

Verifique com os seus colaboradores quais os treinamentos ou necessidades de aprendizagem de cada célula. A partir destas necessidades, você pode realizar um mapeamento do perfil profissional ou o talento que cada célula ainda necessita para aumentar a sua produtividade. Vetorize as necessidades mapeadas em ordem de prioridade junto com os colaboradores.

**Etapa 3 – Validação gerencial**

Valide o vetor com os gerentes de células e com os gestores da empresa.

**Etapa 4 – Mapeamento do conhecimento interno**

Faça o mapeamento dos colaboradores que possuem algum conhecimento dentro do vetor sequencializado. Possibilidade de refinar a sua matriz de talentos desenvolvida na ação 1.

**Etapa 5 – Colaboradores e novos talentos**

Faça o mapeamento dos colaboradores que querem desenvolver um novo talento dentro da organização.

**Etapa 6 – Validação gerencial dos colaboradores e novos talentos**

Faça uma validação do mapeamento gerado nas etapas 4 e 5 com os gerentes de células e com os gestores da empresa.

**Etapa 7 – Recheio do vetor do conhecimento** 

Com a lista validada, recheie o vetor do conhecimento com os treinamentos necessários. Cada elemento de vetor direciona um treinamento que deve ser oferecido aos colaboradores da empresa. Verifique se alguém mapeado na etapa 4 consegue oferecer o treinamento. Caso contrário você deverá buscar o treinamento no mercado.

**Etapa 8 – Desenvolvimento de competência e habilidades**

Por fim, ofereça o treinamento e deixe o conhecimento explicitado por ele na base de conhecimento. Ofereça o treinamento aos colaboradores mapeados na etapa 5. Insira os colaboradores treinados na produção de bens e serviços.

[![img](https://engenhariasoftware.files.wordpress.com/2021/04/fugura.png?w=1024)](https://engenhariasoftware.files.wordpress.com/2021/04/fugura.png)

Por fim, sempre ressalto que as vezes o talento que você procura pode estar ao seu lado.

por José Augusto Fabri

fabri@utfpr.edu.br











Posted on [April 4, 2021](https://engenhariasoftware.wordpress.com/2021/04/04/o-talento-que-voce-procura-pode-estar-ao-seu-lado/) by [José Augusto Fabri](https://engenhariasoftware.wordpress.com/author/engenhariasoftware/)Posted in [Sem-categoria](https://engenhariasoftware.wordpress.com/category/sem-categoria/)[Leave a comment](https://engenhariasoftware.wordpress.com/2021/04/04/o-talento-que-voce-procura-pode-estar-ao-seu-lado/#respond)

# [Lean digital é a melhor forma de conduzir a transformação da TI, dizem especialistas](https://engenhariasoftware.wordpress.com/2021/04/04/lean-digital-e-a-melhor-forma-de-conduzir-a-transformacao-da-ti-dizem-especialistas/)

A adoção de “digital first” é prioridade para a estratégia de negócios de 42% dos executivos líderes de empresas, de acordo com [pesquisa recente do Gartner com CEOs](http://www.gartner.com/smarterwithgartner/2017-ceo-survey-infographic/). Para a [Ci&T](http://www.ciandt.com/home), fornecedora brasileira de serviços de TI e soluções digitais, o conceito lean digital é a melhor forma de conduzir essas transformações tecnológicas necessárias para atender às mudanças nas jornadas dos consumidores, que têm impactado negócios em todos os setores — de serviços, agricultura e indústria.

Seja enxuto, leve para transformar culturalmente a forma de produzir de sua empresa.

Texto completo em: https://computerworld.com.br/inovacao/lean-digital-e-melhor-forma-de-conduzir-transformacao-da-ti-dizem-especialistas/



Posted on [April 4, 2021](https://engenhariasoftware.wordpress.com/2021/04/04/lean-digital-e-a-melhor-forma-de-conduzir-a-transformacao-da-ti-dizem-especialistas/) by [José Augusto Fabri](https://engenhariasoftware.wordpress.com/author/engenhariasoftware/)Posted in [mercado produtor de software](https://engenhariasoftware.wordpress.com/category/mercado-produtor-de-software/), [Papo de Empresa](https://engenhariasoftware.wordpress.com/category/papo-de-empresa/)[Leave a comment](https://engenhariasoftware.wordpress.com/2021/04/04/lean-digital-e-a-melhor-forma-de-conduzir-a-transformacao-da-ti-dizem-especialistas/#respond)

# [Tomato-Timer](https://engenhariasoftware.wordpress.com/2021/03/16/tomato-timer/)

Ferramenta simples e rápida para utilizar a técnica [Pomodoro](https://engenhariasoftware.wordpress.com/2009/12/09/utilizando-tomates-no-planejamento-de-seu-tempo/).

https://tomato-timer.com/

Dica de Nicolas Oliveira – Pós-Java UTFPR-CP (2021-1)



Posted on [March 16, 2021](https://engenhariasoftware.wordpress.com/2021/03/16/tomato-timer/) by [José Augusto Fabri](https://engenhariasoftware.wordpress.com/author/engenhariasoftware/)Posted in [gestão de projetos](https://engenhariasoftware.wordpress.com/tag/gestao-de-projetos/), [processo de produção de software](https://engenhariasoftware.wordpress.com/category/processo-de-producao-de-software/)[Leave a comment](https://engenhariasoftware.wordpress.com/2021/03/16/tomato-timer/#respond)

## Posts navigation

[Older posts](https://engenhariasoftware.wordpress.com/page/2/)

BUSCA:Search for:

ÚLTIMOS TEXTOS[ESG! O que significa? Será que traz grandes revelações?](https://engenhariasoftware.wordpress.com/2021/07/21/esg-o-que-significa-sera-que-traz-grandes-revelacoes/)[É possível customizar uma métricas de software tradicional?](https://engenhariasoftware.wordpress.com/2021/07/19/e-possivel-customizar-uma-metricas-de-software-tradicional/)[A relação entre analista de sistemas e usuários. DevOpS! Correto?](https://engenhariasoftware.wordpress.com/2021/06/22/a-relacao-entre-analista-de-sistemas-e-usuarios-devops-correto/)[Refinement Scrum](https://engenhariasoftware.wordpress.com/2021/06/06/refinement-scrum/)[A Atividade de Refactoring](https://engenhariasoftware.wordpress.com/2021/05/04/a-atividade-de-refactoring/)[Gestão de projetos. Treinamento e Brinquedos.](https://engenhariasoftware.wordpress.com/2021/04/21/gestao-de-projetos-treinamento-e-brinquedos/)[Business Impact Analysis (BIA)](https://engenhariasoftware.wordpress.com/2021/04/19/business-impact-analysis-bia/)[O talento que você procura pode estar ao seu lado](https://engenhariasoftware.wordpress.com/2021/04/04/o-talento-que-voce-procura-pode-estar-ao-seu-lado/)[Lean digital é a melhor forma de conduzir a transformação da TI, dizem especialistas](https://engenhariasoftware.wordpress.com/2021/04/04/lean-digital-e-a-melhor-forma-de-conduzir-a-transformacao-da-ti-dizem-especialistas/)[Tomato-Timer](https://engenhariasoftware.wordpress.com/2021/03/16/tomato-timer/)

## JOSÉ AUGUSTO FABRI

[Artigos](https://engenhariasoftware.wordpress.com/tag/artigos/) [conhecimento](https://engenhariasoftware.wordpress.com/tag/conhecimento/) [desenvolvimento cognitivo](https://engenhariasoftware.wordpress.com/tag/desenvolvimento-cognitivo/) [engenharia](https://engenhariasoftware.wordpress.com/tag/engenharia/) [engenharia de software](https://engenhariasoftware.wordpress.com/tag/engenharia-de-software/) [engenharia do como](https://engenhariasoftware.wordpress.com/tag/engenharia-do-como/) [gestão de projetos](https://engenhariasoftware.wordpress.com/tag/gestao-de-projetos/) [Guia](https://engenhariasoftware.wordpress.com/tag/guia/) [matemática](https://engenhariasoftware.wordpress.com/tag/matematica/) [mindstorms](https://engenhariasoftware.wordpress.com/tag/mindstorms/) [processo de software](https://engenhariasoftware.wordpress.com/tag/processo-de-software/) [programação](https://engenhariasoftware.wordpress.com/tag/programacao-2/) [teoria e prática](https://engenhariasoftware.wordpress.com/tag/teoria-e-pratica/)

CATEGORIAS[astah](https://engenhariasoftware.wordpress.com/category/astah/) (15)[Aulas](https://engenhariasoftware.wordpress.com/category/aulas/) (8)[Banco de Dados](https://engenhariasoftware.wordpress.com/category/banco-de-dados/) (2)[Ensino de engenharia de software](https://engenhariasoftware.wordpress.com/category/ensino-de-engenharia-de-software/) (21)[Ferramentas](https://engenhariasoftware.wordpress.com/category/ferramentas/) (11)[gestão de projetos](https://engenhariasoftware.wordpress.com/category/gestao-de-projetos/) (154)[gestão do conhecimento](https://engenhariasoftware.wordpress.com/category/gestao-do-conhecimento/) (42)[Introdução a Engenharia de Software](https://engenhariasoftware.wordpress.com/category/introducao-a-engenharia-de-software/) (38)[mercado produtor de software](https://engenhariasoftware.wordpress.com/category/mercado-produtor-de-software/) (38)[off topic](https://engenhariasoftware.wordpress.com/category/off-topic/) (67)[Papo de Empresa](https://engenhariasoftware.wordpress.com/category/papo-de-empresa/) (11)[processo de produção de software](https://engenhariasoftware.wordpress.com/category/processo-de-producao-de-software/) (126)[Programação](https://engenhariasoftware.wordpress.com/category/aulas/programacao/) (2)[qualidade de software](https://engenhariasoftware.wordpress.com/category/qualidade-de-software/) (18)[Sem-categoria](https://engenhariasoftware.wordpress.com/category/sem-categoria/) (20)

LINKS[Blog do Palazzo](http://palazzo.pro.br/wordpress/)[Blog do Silvio Meira](http://smeira.blog.terra.com.br/)[Change Vision](http://changevision.wordpress.com/)[Democracia e transparência em C&T](http://democracia-e-transparencia-em-ct.blogspot.com/)http://jmmwrite.wordpress.com/[http://visaoagil.wordpress.com](http://visaoagil.wordpress.com/)http://www.agileway.com.br/[Linguagem C Descomplicada](http://programacaodescomplicada.wordpress.com/)[Provocações – Por Xexeo](http://xexeo.wordpress.com/)[web5internet](http://web5internet.wordpress.com/)

## [![RSS](https://s-ssl.wordpress.com/wp-includes/images/rss.png?m=1354137473h)](https://engenhariasoftware.wordpress.com/feed/) [BLOG SOBRE ENGENHARIA DE SOFTWARE](https://engenhariasoftware.wordpress.com/)

- ESG! O que significa? Será que traz grandes revelações?

  July 21, 2021

  Pessoal, espero que todos estejam bem! Neste semestre (2021-1) ouvi muito sobre ESG. O conceito foi criado em 2004 durante Pacto Global, evento liderado pelo Banco Mundial. Três palavras da língua inglesa compõe a sigla: Environmental Sustainability Governance A ideia é aplicar esse conceito dentro de organizações estruturadas ou empresas. Essas organizaçõ […]

  José Augusto Fabri

ACESSOS634,694

| S    | M    | T    | W    | T    | F    | S    |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |
|      | 1    | 2    | 3    | 4    | 5    |      |
| 6    | 7    | 8    | 9    | 10   | 11   | 12   |
| 13   | 14   | 15   | 16   | 17   | 18   | 19   |
| 20   | 21   | 22   | 23   | 24   | 25   | 26   |
| 27   | 28   |      |      |      |      |      |

[« Jul](https://engenhariasoftware.wordpress.com/2021/07/)  

[Create a free website or blog at WordPress.com.](https://wordpress.com/?ref=footer_website)

[Engenharia de Software](https://engenhariasoftware.wordpress.com/)

[Create a free website or blog at WordPress.com.](https://wordpress.com/?ref=footer_website)



 