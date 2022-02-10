[![Alvaro Paçó](https://miro.medium.com/fit/c/96/96/0*yxel7B5e8yVYtEKl.)](https://alvaropaconeto.medium.com/?source=post_page-----c57fa9da985c-----------------------------------)

[Alvaro Paçó](https://alvaropaconeto.medium.com/?source=post_page-----c57fa9da985c-----------------------------------) - Dec 20, 2018

# Processo de Modernização de Software Legado

Estudo de Caso

Modernização de esteira de prevenção a Fraudes e Lavagem de dinheiro.

Considere o cenário em que você é um engenheiro de sistemas sênior e será responsável por analisar os sistemas legados do domínio de Prevenção Fraudes e Prevenção Lavagem de dinheiro. Os sistemas legados possuem mais de 20 anos e estão suportados em diferentes tecnologias e plataformas (mainframe e distribuída).

Uma das principais funções que temos no domínio de Prevenção à Fraude e Prevenção Lavagem de dinheiro é o monitoramento de transações, onde busca-se detectar a partir de regras e modelos estatísticos quais transações financeiras ou não-financeiras podem ser apontadas como fraude. Existe ainda a possibilidade de derivação de casos para uma análise humana (BackOffice), caso exista incerteza quanto à possibilidade de uma transação ser fraudulenta.

No cenário atual, os sistemas são segregados por produto, ou seja, existe um sistema responsável pela monitoração de transações de cartão de crédito e outro responsável pela monitoração de transações ‘banco’, por exemplo, pagamento de contas, transferências, saques e outros. Cada um desses sistemas resolve o problema de ponta a ponta, ou seja, é responsável por receber as transações, aplicar as regras, verificar listas restritivas, apresentar um workflow para análise de transações, gerar relatórios, etc.

O seu desafio como engenheiro de sistemas sênior será buscar recortes² (desacoplar funcionalidades) e desenhar uma proposta de solução técnica (apresente peças técnicas e o papel de cada uma delas) de forma que resolva a necessidade de negócio.

# Perguntas

# Qual é a sua estratégia para modernizar esse legado?

Em um contexto de modernização de aplicações legadas é necessário aplicar técnicas para a gestão do processo de migração, homologação e disponibilização dos produtos migrados. As principais diretrizes à serem levados em consideração num processo de migração são;

- Tecnologia à prova de futuro
- TCO (Capex + Opex), custo da migração
- Facilidade de operação e manutenção

![img](https://miro.medium.com/max/1400/0*pUI3-8h8lqp1evnf)

Para atingir os resultados esperados baseado nestas diretrizes a minha abordagem é implementar um fluxo simples mas eficaz:

Implementar o seguinte roteiro se atingir o resultado final:

1. **Estratégia de migração**: saber onde está e onde quer chegar. Isso inclui analisar os artefatos dos projetos legados, conversar com os desenvolvedores e projetistas do legado, com as diversas camadas como de sustentação, implementação e suporte.
2. **Conhecer os riscos do projeto**: analisar profundamente as soluções legadas e analisar os possíveis riscos. É necessário o contato constante com os engenheiros que construíram a solução e o suporte.
3. **Contingenciar os riscos**: tomar ações efetivas para prevenção dos riscos conhecidos na migração. Por exemplo no “case” em questão, como são utilizados mainframes podem ocorrer problemas com grande volume de dados processados. É importante se cercar de possíveis soluções como utilizar serviços cloud escaláveis de alta disponibilidade ou técnicas modernas de clusterização e tomar a melhor decisão. uma vez tomada, adiantar a implementação da solução, bem como realizar os testes e a homologação, garantindo que a soluções que forem implantadas não serão afetadas por esse gargalo.
4. **Estratégia de transição**: é uma etapa crítica onde o que foi implementado irá entrar em operação, ocupando o lugar da funcionalidade legada. Existem diversas técnicas de migração e, dependendo do projeto a ser transacionado devemos escolher a que melhor se encaixa. No “case” eu poderia imaginar um cenário de operação paralela em que você constrói aplicações que irão um dia substituir as antigas ao mesmo tempo vai validando elas e colocando-as para funcionar.
5. **Instalação e Configuração**: após a transição segue-se ao processo de instalação e configuração dos diversos ambientes que irão suportar as aplicações.
6. **Comissionamento da instalação**: garantir que tudo está instalado, configurado, hospedado de acordo com as necessidades do projeto e mantendo as padrões das aplicações legadas.
7. **Cut-over**: realizar a transição definitiva, colocando os novos produtos em produção para serem consumidos, tomando o lugar do legados.
8. **Operação assistida**: monitorar o funcionamento de todo a esteira de operação das soluções implementadas analisando os artefatos disponíveis como sistemas de monitorização, logs, tráfego de rede, carga de servidor, acessos, etc…
9. **Homologação, backup e documentação**: homologar as aplicações e o processo que foi utilizado para implantar a solução bem como realizar os backups dos sistemas legados e atuais e escrever toda documentação do processo de modernização.

Além disso é importante manter um processo de gerenciamento de mudanças onde tudo que for alterado, implementado ou removido é registrado sobre quem mudou, quando e qual foi a mudança. Também importante ter um sistema de Big Data para analisar os impactos que todos esse processo está causando e manter o foco na cibersegurança.

# Escolha uma funcionalidade prioritária para modernizar.

Para priorizar uma ou outra aplicação é necessário analisar o número de usuários e transações afetadas por este. Em um cenário em que a maioria dos cliente possuem cartão e realizam operações realizadas com ele mas a minoria utilizam operações “banco”, então eu priorizaria modernizar o projeto de menor impacto. Uma vez que este tenha sido bem sucedido e refinado, podemos aplicá lo ao produto de maior demanda, corrigindo potenciais erros ou deficiências constatados anteriormente. No caso eu escolheria o Software de transações banco, imaginando que seja o menos utilizado.

# Quais os critérios você adotou para priorizar a funcionalidade a ser modernizada?

Como o exposto acima, vou priorizar migrar as aplicações de menor impacto nos negócios e na vida da empresa. Ao meu ver, no “case”, a aplicação de transações banco teria menor impacto, por tanto, priorizaria ela.

# Quais seriam os requisitos imprescindíveis para essa funcionalidade?

Os requisitos são artefatos que ajudaram de maneira imprescindível a processo de modernização. Os requisitos imprescindíveis são:

- Acesso ao código fonte, ambiente, infra-estrutura e repositórios dos projetos legados.
- Acesso à documentação dos projetos à serem modernizados: arquitetura, projeto de Software, documentação de casos de uso, etc…
- Acesso à camada de dados e persistência.
- Acesso ao modelo de negócio da aplicação.
- Como será a convivência desta funcionalidade modernizada com o legado? (Visão técnica)

Vai depender da estratégia de transição. No caso, como exemplificado na questão um deste estudo de caso, utilizando a estratégia de operação paralela, o desenvolvimento, implantação e operação co-existe com as aplicações existentes, inter-operando entre elas. Na medida em que o legado é substituído, as aplicações modernas são testadas e validadas. Dessa maneira a co-existência com sistemas legados deve ser suavizada e harmonizada, com o moderno e o legado operando entre si e suavizando qualquer impacto que possa ser causado.

Pode haver a necessidade de se criar “middlewares” ou “pontes” entre novos sistemas e sistemas antigos e isso vai ser levantado na fase de contingenciamento de riscos.

No caso de uma migração de Mainframes para plataformas Cloud existem diversos desafios envolvidos principalmente no armazenamento e compartilhamento de ativos. É necessário pesquisar serviços de migração de larga escala e virtualização de diretórios, por exemplo

# Quais serão os fatores críticos para o sucesso da modernização dessa funcionalidade?

Existem diversos fatores críticos na modernização de sistemas legados. Podemos apontar, no caso desse projeto como fatores críticos para uma bem-sucedida modernização os fatores:

- Estratégia de Modernização bem definida;
- Equipe de inspeção e modernização experiente e qualificada, que conheça o sistema legado;
- Um time de transição que vai trabalhar para entender as duas pontas (legado e moderno) do Software.
- Inspeção e monitorização contínua
- Testes
- Documentação
- Quais seriam as linguagem e tecnologias envolvidas na solução e por quê?

Existem diversas linguagens que atendem à necessidades e problemas específicos hoje em dia. Para cada tipo de problema existe uma linguagem e tecnologia que se encaixa melhor. Os pontos que devem ser considerados na escolha de uma linguagem de programação para implementar uma solução de Software devem ser a segurança, linguagens OO que garantem a abstração, modularidade e manutenibilidade de código, o tipo de licença (código aberto ou não), o tamanho da comunidade desenvolvedora, o tempo de projeto da linguagem e versões (quanto mais evoluída menor a chance de ter problemas), a cobertura de código, a curva de aprendizagem e os requerimentos de sistema para rodar.

Vamos optar por linguagens de código aberto, que significa que a comunidade do mundo todo poderá contribuir e ajudar a aperfeiçoar seu código-fonte, corrigindo e reduzindo o número de “bugs”. A segurança é um item essencial em nossa aplicação, por isso, vamos descartar linguagens de programação e tecnologias que tenham falhas conhecidas de segurança, como NodeJs, Javascript e PHP. Também vamos optar por uma linguagem com uma comunidade grande. Comunidade de desenvolvedores significa mais artigos, módulos, extensões e posts que auxiliam na resolução de problemas e melhoram a curva de aprendizado.

Nossa linguagem também deve possuir um nível de maturação muito boa, um tempo rodando no mercado, principalmente de meios de pagamento, garantindo assim que vamos possuir soluções para todos os tipos de problemas. Nossa linguagem ainda deve possuir grande cobertura de código (waterline 90–100), reduzindo os riscos de “bugs”. Para garantir que o projeto seja bem sucedido a longo prazo, é muito importante garantir que seja possível contratar programadores que consigam aprender a linguagem e a solução em si. Por isso precisamos de uma linguagem que curva íngreme de aprendizado, garantindo a facilidade em se aprender a tecnologia. Por último devemos avaliar os requisitos necessários para rodá-la no ambiente do banco. Não adianta optar por uma linguagem e tecnologia que não é viável para a estrutura existente na empresa.

Seguindo esses aspectos temos algumas opções:

- Java: é provavelmente a linguagem mais utilizado no mundo corporativo pelo seu tempo de mercado, confiabilidade, segurança e tamanho da comunidade. Java também possui frameworks e projetos para muitos tipos de aplicações, desde mobile até sistemas de pagamento. Apesar do java ser uma especificação de código aberto, seu SDK, JEE e JRE não só de código aberto, o que significa que dependeremos sempre de uma empresa terceira. Outro ponto negativo é que Java não é a preferência entre os desenvolvedores, não tem uma curva de aprendizado das melhores e é relativamente caro manter um sistema java rodando. Java é “cross-platform”, o que significa que as aplicações criadas podem ser usadas em qualquer ambiente.
- C#: originalmente foi criada para competir diretamente com o Java e feito para rodar em plataformas .Net. pesar de no início o C# possuir código fonte fechado e rodar apenas em ambiente windows, a Microsoft abriu seu código recentemente e hoje já está disponível para Unix. C# possui uma grande comunidade desenvolvedora e uma curva de aprendizado bem íngreme graças ao suporte da Microsoft. Além disso C# possui muita semelhança com o Java na sintaxe de código. C# é “cross-platform”.
- Python: é uma ótima opção. Python é uma linguagem de programação feita para desenvolver aplicações rapidamente. Existem aplicações de todos os tipos desenvolvidas com Python, desde jogos a ferramentas de teste de penetrabilidade de sistemas. Python é muito versátil e a sua linguagem natural é muito vantajosa na manutenção e inspeção de código. Python é a linguagem que tem a melhor curva de aprendizado entre às 3 recomendadas, possui um grande comunidade desenvolvedora, é modular, possui diversos frameworks de desenvolvimento, é muito performática e segura.

Levando em conta essas características a minha opção seria usar Python por se tratar de uma linguagem confiável, madura, com uma comunidade sólida e colaborativa, que possui aspectos de linguagens de desenvolvimento modernas e é segura. Comparado ao Java, Python é mais lento porém os programas desenvolvidos utilizando esta linguagens normalmente são de 3 à 5 vezes menores que os programas em Java, por isso, no resultado final, uma aplicação Python roda mais rapidamente e performaticamente que uma aplicação em Java, segundo a fonte https://www.python.org/doc/essays/comparisons/.

Além da linguagem de programação, o sucesso da modernização vai se deve muito ao conjunto de tecnologias empregado no desenvolvimento, manutenção e entrega que vão suportar o novo projeto. Para se trabalhar de maneira paralela com a aplicação legada é essencial utilizar tecnologias que possibilitem uma entrega contínua. Eu utilizarei tecnologias como micro-serviços, apis RESTful, chamadas assíncronas, ambiente de desenvolvimento “conternizado”, automação de testes, deploy e entrega contínua com Docker, GOD entre outras ferramentas. Outra frente muito importante é a monitorização do desempenho e dos logs de atividades. Eu utilizaria um sistema de monitorização com kibana, elasticsearch, NetData, Prometheus, cAdivisor. Utilizaria essencialmente um “stack” com tecnologias open-source madura em ambiente “contenizado”, garantindo um projeto à prova de futuro.

# Como você irá armazenar esses dados (tecnologias e modelos)?

Mantendo o foco em tecnologias modernas, seguras e de fácil manutenção eu optaria por migrar para soluções em nuvem. O principal não será qual tecnologia usar mas sim a que melhor se encaixe na migração de dados existentes. Como o sistema legado já tem mais de 20 anos provavelmente se trata de um modelo relacional. Por tanto utilizaremos bancos de dados relacionais para à persistência de dados. Outro fator importante é escolher um serviço de cloud para armazenamento de dados que seja realmente rápido e performático. Hoje em dia os serviços de cloud oferecem muitas opções.

![img](https://miro.medium.com/max/1082/0*eE118qcCIS-jpiPM)

O Primeiro passo será obter os diagramas de MER, analisá los e criar POC’s para testar qual o melhor tipo de serviço e SGBD utilizar. caso esses diagramas simplesmente não existam será necessário criá-los ( contingenciamento de risco). Para garantir o pleno funcionamento em um cenário real, eu criarei uma massa de testes para execução de carga e sobrecarga de dados para garantir a performance e integridade de informações.

# Como a performance será otimizada de um jeito que ficará fácil de escalar?

A escalabilidade depende da arquitetura de software que será implementada mas basicamente garanto a escalabilidade do projeto implementando uma arquitetura em micro serviços ao invés de sistemas monolíticos. Arquiteturas em micro-serviços não são recomendadas para todos os casos. Há casos em que se trabalhar com micro-serviços prejudica ao invés de ajudar mas pelo “overview” uma arquitetura em micro-serviços irá ajudar a modularizar a aplicação legada e facilitar na migração paralela dos serviços, além de se tratar de uma arquitetura extremamente escalável e de fácil manutenção.

Em uma arquitetura de micro-serviços a implementação das diversas funcionalidades do Software fica distribuídas e diversos nós que podem ser escalados individualmente aliviando e facilitando o balanceamento de cargas.

# Dado que é um projeto importantíssimo para a organização, como você faria para acelerar o desenvolvimento, entregando valor para o cliente em menor tempo?

A velocidade do projeto depende diretamente da agilidade e gerenciamento dos times. Um time experiente normalmente é mais ágil que um time que não tem um grande conhecimento das tecnologias e do projeto em si. Para acelerar o desenvolvimento do projeto eu montaria um time experiente nas tecnologias adotadas, fornecendo uma especificação muito bem definida e documentada. Também adotaria técnicas modernas de desenvolvimento ágil de Software como Scrum e kanban, que facilitam e auxiliam o cumprimento dos prazos do projeto. Com técnicas modernas de desenvolvimento e gestão de projetos é possível traçar um “roadmap” do projeto e estimar uma data de entrega e o número de recursos necessários para concluir o trabalho.

Além de um time experiente e técnicas modernas de agilidade é necessário usar ferramentas que vão auxiliar o time no dia-à-dia do desenvolvimento. Há ferramentas de gerenciamento de equipes de desenvolvimento muito boas no mercado que ajudam a criar os cenários, histórias, tarefas e estimar tudo com uma fidelidade muito próxima da realidade como o Jira, o Trello e o Redmine.

![img](https://miro.medium.com/max/1400/0*yXcLcv0OLiye4pcY)

33









## [More from Alvaro Paçó](https://alvaropaconeto.medium.com/?source=post_page-----c57fa9da985c-----------------------------------)