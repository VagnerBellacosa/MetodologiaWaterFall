# Desmistificando as opções de Migração do Legado para a AWS

by [AWS Editorial Team](https://aws.amazon.com/pt/blogs/aws-brasil/author/admin/) | on 14 OCT 2019 | [Permalink](https://aws.amazon.com/pt/blogs/aws-brasil/desmistificando-as-opcoes-de-migracao-do-legado-para-a-aws/) | [ Share](https://aws.amazon.com/pt/blogs/aws-brasil/desmistificando-as-opcoes-de-migracao-do-legado-para-a-aws/#)

Por Phil de Valence, Arquiteto de soluções para Legacy Modernization na AWS

Muitas empresas ou instituições ainda possuem sistemas legados não-x86 em seus datacenters: sistemas proprietários de mainframe, midrange ou UNIX. ![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Image_1.jpg)

A migração dessas cargas de trabalho das arquiteturas de hardware para a Amazon Web Services (AWS) Cloud requer tecnologia de software avançada. As abordagens de migração de curto prazo usam principalmente emulação de hardware, emulação de middleware, refatoração automática ou reformulação de middleware.

Este post destaca as opções de migração de curto prazo, suas principais diferenças técnicas e seus benefícios diferenciados. Essas opções são particularmente adequadas para aplicativos domésticos personalizados em execução em uma plataforma herdada, onde o código fonte completo está disponível. Por outro lado, aplicativos em pacote de terceiros geralmente exigem discussão com o fornecedor de software para opções de modernização para a AWS.

### Opções de migração a curto prazo

Essas opções de migração resultam em uma duração mais curta do projeto para retorno mais rápido sobre o investimento (ROI) e ganhos rápidos.

O diagrama na Figura 1 mostra, para cada opção, componentes que mudam e componentes que permanecem os mesmos durante a migração da plataforma herdada não-x86.

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-1-1024x494.png)

*Figura 1 – Alterações de componentes na migração do legado.*

 

- Emulação de hardware Legado: o emulador de hardware substitui o hardware legado, mas o sistema operacional legado e os aplicativos permanecem os mesmos.
- Emulação de Middleware Legado: O emulador de middleware substitui as APIs de middleware legados e as APIs de SO exigidas pelo aplicativo, permitindo a portabilidade. A maior parte do código fonte do aplicativo é recompilada sem alterações, com algumas adaptações para dependências alteradas.
- Re-fatoração automatizada do legado: código, dados e dependências são convertidos automaticamente em uma linguagem moderna, armazenamento de dados e frameworks, garantindo equivalência funcional às mesmas funções de negócios.
- Re-plataforma de Middleware moderno: aplica-se apenas às linguagens modernas, middleware e runtimes disponíveis em sistemas legados e x86, como Java, PHP e bancos de dados relacionais. Permite reutilizar o código do aplicativo e os bancos de dados.

### Proposições de valores diferenciadas

Cada opção de migração possui seus casos de uso preferenciais e proposta de valor exclusivo, relevantes para uma carga de trabalho legada específica.

Considerando uma carga de trabalho de tamanho médio com alguns milhões de linhas de código, o diagrama na Figura 2 mostra as principais características diferenciadoras, como custo do projeto, duração do projeto e agilidade na nuvem, conforme representado pelo [Modelo de Maturidade em Nuvem-Nativo](https://aws.amazon.com/pt/blogs/apn/journey-to-being-cloud-native-how-and-where-should-you-start/). Esse modelo promove o uso dos [serviços gerenciados da AWS](https://aws.amazon.com/pt/managed-services/features/), dos princípios de design dos [Doze-Fatores de um Aplicativo](https://12factor.net/), dos [Microsserviços](https://aws.amazon.com/pt/microservices/) e da automação, assim como [Integração Contínua/Implantação contínua](https://aws.amazon.com/pt/devops/continuous-integration/) (CI/CD).

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-2-1024x599.png)

*Figura 2 – Opções de migração relativas à duração, custo e agilidade.*

 

Detalhes e explicações sobre cada uma das migrações são fornecidos nas sessões subsequentes.

### Emulação de hardware legado

- **Tipo de migração:** Re-hospedar usando emulação de hardware.
- **Sistemas aplicáveis:** Esta opção se aplica aos mainframes IBM Z, mainframes Unisys ClearPath, máquinas SPARC, computadores AlphaServer, estações VAX, computadores HP 3000 e HP 9000, minicomputadores PDP, e outros. Permite executar sistemas operacionais como IBM z/OS, Unisys ClearPath MCP ou OS2200, Solaris, SunOS, HP-UX, MPE, OpenVMS, Tru64, RSX-11, RSTS-11, RSTS ou RT-11, sobre a infraestrutura da AWS.
- **Descrição:** o software emulador do fornecedor emula o conjunto de instruções de hardware legado. Portanto, ele pode executar os binários legados em cima de um conjunto moderno de instruções Linux e x86-64. Ele permite executar o sistema operacional legado e seus aplicativos sem alterações, sem necessidade de recompilar o código-fonte ou transformar os binários.

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-3-1024x537.png)

*Figura 3 – Emulação de hardware legado.*

 

- **Exemplo de pilha de destino:** Os emuladores de hardware do fornecedor são executados nas instâncias do [Amazon Elastic Compute Cloud](https://aws.amazon.com/pt/ec2/) (Amazon EC2). Por causa do sistema operacional legado, o AWS Managed Services não é usado para computação ou dados.
- **Abordagem de migração:** esse é uma nova hospedagem lift-and-shift do Sistema Operacional legado do hardware legado para o emulador de software, porque o sistema operacional de origem, os binários e os arquivos permanecem inalterados. Geralmente, isso é feito com uma restauração do backup ou restauração do dump do Sistema Operacional legado, e a transferência dos arquivos de backup é através do [AWS Direct Connect](https://aws.amazon.com/pt/directconnect/) ou [AWS Snowbal](https://aws.amazon.com/pt/snowball/)l. Os aplicativos, dados e interfaces permanecem inalterados e a quantidade de testes necessários é reduzida, permitindo migrações em dias ou semanas.
- **Casos de uso típicos:** Migrando ambientes de desenvolvimento e teste para a AWS: Migrando aplicativos de produção estabilizados para a AWS; Manter a mesma pilha de software de desenvolvimento de aplicativos enquanto moderniza o hardware; O datacenter foi descontinuado, incluindo o descomissionamento de hardware legado.
- **Benefícios do emulador de hardware:** Nenhuma alteração no código do aplicativo, no middleware e no sistema operacional. Mesmas interfaces e mesmos protocolos de comunicação; Migração transparente para usuários finais e proprietários de aplicativos.
- **Benefícios da AWS:** Grande variedade de tipos de instância do Amazon EC2 para CPU, memória, armazenamento, largura de banda da rede; Alterações de capacidade e escalabilidade em minutos; Custo otimizado com o modelo de pagamento conforme o uso dos recursos/serviços da AWS ou Instâncias reservadas (RI); Maior disponibilidade nas zonas de disponibilidade (AZ).
- **Cuidado:** A emulação de conjuntos de instruções de hardware requer tradução imediata, o que afeta o desempenho. Dependendo da idade do hardware de origem e do tipo de software emulador, esse impacto no desempenho pode ser mais ou menos perceptível. De qualquer forma, é recomendado um benchmark de desempenho. As instâncias do Amazon EC2 com a velocidade de clock do processador mais rápida, assim como as instâncias z1d com 4,0 GHz, podem ajudar.
- **Exemplos de fornecedores:** [Stromasys Charon](https://aws.amazon.com/blogs/apn/re-hosting-sparc-alpha-or-other-legacy-systems-to-aws-with-stromasys/), [IBM Z Development and Test Environment](https://developer.ibm.com/mainframe/products/z-systems-development-test-environment/), [Unisys ClearPath Forward](https://assets.unisys.com/Documents/Global/ProductInformationSheets/PI_150523_ClearPathForwardSystem.pdf).
- **Melhores práticas de fornecedores:** é importante entender como cada fornecedor otimiza a tradução de instruções do emulador e possíveis opções de ajuste de desempenho com a AWS.

### Emulação de Middleware Legado

- **Tipo de migração:** Re-plataforma com código portado para um emulador de middleware.
- **Sistemas aplicáveis:** Esta opção se aplica a alguns mainframes IBM Z, mainframes Unisys ClearPath, IBM AS/400, iSeries e IBM i. Permite transportar e recompilar aplicativos que anteriormente dependiam de middleware e armazenamentos de dados legados, como IBM CICS, IMS, VSAM, QSAM, Unisys COMS, TIP, IBM DB2 para z/OS, DB2 para i (DB2/400) e Adabas. Esses aplicativos podem ser escritos em linguagens como COBOL, PL/I, RPG e Natural.
- **Descrição:** o software do emulador de fornecedor emula APIs de middleware e sistema operacional necessárias para o código do aplicativo. Por exemplo, emuladores de middleware podem fornecer APIs para acesso aos arquivos indexados, gerenciamento de transações, suporte a telas e protocolos legados, armazenamento temporário e suporte a Batch. Isso permite portar e recompilar o código do aplicativo de origem para execução nativa de x86-64.

Se um idioma específico não for suportado, primeiramente ele precisará ser convertido para um idioma suportado. Devido à recompilação, não há tradução de instruções em tempo real realizada pelo emulador e, consequentemente, nenhum impacto relacionado ao desempenho. Dependências ou utilitários não fornecidos pelo emulador (agendador, impressão, segurança, etc.) precisam ser substituídos por equivalentes x86 com prováveis adaptações de código ou configuração correspondentes.

O formato de dados legado é ou retido (VSAM, QSAM) ou mapeado para um armazenamento de dados relacionais, como [Amazon Aurora](https://aws.amazon.com/pt/rds/aurora/), [Amazon RDS para Oracle](https://aws.amazon.com/pt/rds/oracle/) ou [Amazon RDS para SQL Server](https://aws.amazon.com/pt/rds/sqlserver/).

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-4-1024x517.png)

*Figura 4 – Emulação de middleware legado.*

 

- **Exemplo de pilha de destino:** Os emuladores de middleware do fornecedor geralmente são executados nas instâncias do Amazon EC2. Algumas dependências de segurança, agendamento, impressão ou enfileiramento de mensagens são implantadas em suas próprias instâncias. Os armazenamentos de dados podem ser modernizados para se beneficiar dos serviços gerenciados do Amazon RDS, incluindo o Amazon Aurora. Alguns aplicativos podem se beneficiar do [AWS Auto Scaling](https://aws.amazon.com/pt/autoscaling/) e [Elastic Load Balancing](https://aws.amazon.com/pt/elasticloadbalancing/) entre Zonas de Disponibilidade (AZs).
- **Abordagem de migração:** devido às alterações no SO, no middleware e na dependência, nas adaptações de código, na conversão do formato de dados e na recompilação completa, este é um projeto de reformulação em que os programas e funções de negócios são migrados e testados de maneira incremental.

Começa com a descoberta de todos os programas, dados, dependências e integrações. Ele continua projetando a arquitetura de destino e novas dependências, definindo as conversões e substituições da linguagem de programação e planejando os pacotes de trabalho e as transições. Em seguida, a maior parte da migração acontece com alterações automatizadas em massa no código-fonte, atualizações nas regras de migração de código, conversão de dados correspondente e teste.

Os testes se concentram em alterações de código, dados, dependências e integrações. Depois que os testes de unidade, regressão, integração e desempenho são bem-sucedidos, os aplicativos e os dados são implantados em seus ambientes AWS de destino. Mais detalhes estão disponíveis em [Migrando um mainframe para a AWS em 5 etapas](https://aws.amazon.com/pt/blogs/apn/migrating-a-mainframe-to-aws-in-5-steps/) e em um exemplo de cliente em [Migração completa de mainframe para AWS com parceiros](https://aws.amazon.com/pt/blogs/apn/complete-mainframe-to-aws-migration-with-candid-partners/). Essa migração pode durar entre meses e anos, dependendo do número de linhas de código e de outros fatores.

- **Casos de uso típicos:** migrando de uma pilha legada e cara de hardware e software legado; Reter o investimento no código do aplicativo, mantendo a equipe de desenvolvimento e modernizando a infraestrutura subjacente; Migrando ambientes de desenvolvimento e teste para a AWS; Migrando aplicativos de produção estabilizados para a AWS.
- **Benefícios do emulador de middleware:** Eliminar software e hardware de fornecedores legados; Preservar a linguagem de programação de aplicativos, código e habilidades de desenvolvimento; Mesmas interfaces e protocolos de comunicação; Migração transparente para usuários finais; Facilitar a modernização e integração com serviços em nuvem; Reduzir os riscos preservando a mesma lógica e código.
- **Benefícios da AWS:** inclui os benefícios da AWS descritos para o emulador de hardware, além da capacidade de usar os Serviços Gerenciados da AWS, como Amazon RDS ou Elastic Load Balancing. Alguns aplicativos podem se beneficiar da escalabilidade horizontal e elasticidade com os Grupos de Dimensionamento Automático. Os aplicativos podem se beneficiar dos serviços DevOps para gerenciar um pipeline de CI/CD.
- **Cuidado:** Esses projetos não são *lift-and-shift*. Requer análise e planejamento detalhados para alterações de dependência, adaptações de código, conversão de dados e testes completos. Alguns códigos de aplicativos ou formatos de dados legados podem dificultar o uso das práticas recomendadas da AWS, para escalabilidade e disponibilidade.

Se uma linguagem ou ativo não for suportado pelo emulador (Assembly, código gerado, bancos de dados proprietários), a complexidade aumentará drasticamente. Os aplicativos contam principalmente com o emulador de middleware para integração de serviços da AWS. Diferentes fornecedores de emuladores de middleware têm recursos diferentes para integrações e otimizações da AWS.

- Exemplos de fornecedores: [Micro Focus Enterprise Server](https://aws.amazon.com/quickstart/architecture/micro-focus-enterprise-server/), [NTT DATA UniKix](https://aws.amazon.com/blogs/apn/re-hosting-mainframe-applications-to-aws-with-ntt-data-services/), [TmaxSoft OpenFrame](https://www.tmaxsoft.com/products/openframe/), [Astadia OpenMCS](https://aws.amazon.com/blogs/apn/migrating-a-mainframe-to-aws-in-5-steps/), [Infinite i](https://aws.amazon.com/marketplace/pp/B07JLVHCXF).
- Melhores práticas de fornecedores: os aplicativos se beneficiam de uma melhor disponibilidade, elasticidade, desempenho e otimização de custos ao usar a escalabilidade horizontal da AWS. Os emuladores de middleware devem facilitar a escalabilidade horizontal, especialmente para armazenamentos de dados legados, estruturas de dados compartilhadas na memória, favorecendo arquiteturas ativo/ativo entre Zonas de Disponibilidade (AZs).

Os emuladores de middleware também se diferenciam com o suporte a recursos da AWS, como Amazon Aurora, Amazon RDS, [Amazon Linux](https://aws.amazon.com/pt/mp/solutions/amazonlinux/) e [Amazon CloudWatch](https://aws.amazon.com/pt/cloudwatch/).

### Refatoração automática do legado

- **Tipo de migração:** refatoração automática com conversão de código, dependências e dados.
- **Sistemas aplicáveis:** Esta opção se aplica a linguagens como COBOL, PL/I, RPG, Natural e FORTRAN, incluindo geradores de código, como aplicativos Cool: Gen ou PowerBuilder. Ele converte modelos de dados de armazenamentos de dados, como IBM DB2 z/OS, VSAM, QSAM, IMS DB, DB2 para i (DB2/400), Adabas e Data Management System.

Isso significa que muitos aplicativos hospedados nos mainframes IBM Z, mainframes Unisys ClearPath, IBM AS/400, iSeries e IBM i podem se beneficiar da refatoração automática da AWS.

- **Descrição:** A refatoração automatizada não é uma reescrita manual de código, mas uma conversão e geração automatizada para códigos modernos, do acesso aos dados, do formato de dados e das dependências por completo. Essa transformação exaustiva e coerente garante equivalência funcional, enquanto a automação aumenta a velocidade e reduz os riscos.

Essa transformação aplica padrões e regras para transformar os componentes legados, como telas legadas, acesso aos arquivos indexados e *batch* em uma pilha de destino moderna com aplicativos Orientado a Objetos e Orientado a Serviços. É possível escolher à linguagem de programação (Java ou .NET), escolha de estruturas de *back-end* (por exemplo, Spring) e estruturas de *front-end* (por exemplo, Angular).

As ferramentas de refatoração automatizadas oferecem a você, imediatamente, a capacidade de escolher vários serviços subjacentes da AWS enquanto se transforma em aplicativos nativos da nuvem. A refatoração também pode isolar grupos de programas e dados dependentes, facilitando a identificação e criação de microsserviços.

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-5-1024x468.png)

*Figura 5 – Refatoração Automática do Legado*

 

- **Exemplo de pilha de destino:** por padrão, as ferramentas do fornecedor convertem a pilha de execução nas instâncias do Amazon EC2 para computação, no Aurora ou no Amazon RDS para armazenamento de dados, criando uma arquitetura Web elástica típica. Com a flexibilidade da refatoração automatizada e a capacidade de ajustar as regras de transformação, muitos outros serviços gerenciados da AWS podem ser incorporados, como o [Amazon Simple Queue Service](https://aws.amazon.com/pt/sqs/) (SQS) para mensagens ou o [Amazon ElastiCache](https://aws.amazon.com/pt/elasticache/) para estruturas de dados compartilhadas na memória.

Alguns aplicativos também podem se beneficiar da execução em contêineres no [Amazon Elastic Container Service](https://aws.amazon.com/pt/ecs/) (Amazon ECS) e [Amazon Elastic Container Service para Kubernetes](https://aws.amazon.com/pt/eks/) (Amazon EKS), ou nas funções sem servidor do [AWS Lambda](https://aws.amazon.com/pt/lambda/). Como a nova pilha é habilitada para serviço, as funções de negócios são facilmente publicadas para novos clientes, como aplicativos móveis por meio do Amazon [API Gateway](https://aws.amazon.com/pt/api-gateway/).

- **Abordagem de migração:** a abordagem geral e as fases de um projeto de refatoração automatizada do legado são semelhantes às de um projeto de emulação de middleware legado, porque ambos incluem um inventário de ativos, mapeando as dependências do aplicativo para os novos componentes da pilha, as alterações em massa na origem código, compilação de código e testes extensivos, que podem levar de 60 a 80% do tempo gasto no projeto.

Mais especificamente, as ferramentas de refatoração automatizadas permitem a engenharia reversa do código do aplicativo e dos modelos de dados, a fim de criar um modelo de aplicativo mostrando todas as dependências do programa e dos dados, além de suas principais características. Esse modelo detalhado é usado para definir a estratégia de migração, mapeamentos de componentes e dados, regras de conversão de código e formato de dados, decomposição de pacotes de trabalho e transições.

A maior parte da migração ocorre com conversões automatizadas de código e dados, com transições incrementais, atualizações nas regras de conversão, testes extensivos e sem reescrita manual do código. Mais detalhes estão disponíveis com exemplos de clientes em “[Refatoração automatizada de um mainframe do New York Times para a AWS com sistemas modernos](https://aws.amazon.com/pt/blogs/apn/automated-refactoring-of-a-new-york-times-mainframe-to-aws-with-modern-systems/)” e em “[Refatoração automatizada de um mainframe do Departamento de Defesa dos EUA para a AWS](https://aws.amazon.com/pt/blogs/apn/automated-refactoring-of-a-u-s-department-of-defense-mainframe-to-aws/)“. Essa migração geral pode durar meses ou anos, dependendo do número de linhas de código e outros fatores:

- **Casos de uso típicos:** migrar de idiomas como COBOL, PL/I, RPG e Natural; Modernizar e padronizar a pilha técnica completa, mantendo o investimento das funções de negócios do aplicativo; Resolver às lacunas de habilidades legadas; Inovar com práticas ágeis, serviços gerenciados e tecnologias nativas da nuvem.
- **Benefícios automatizados de refatoração:** Eliminar tecnologias legadas; Preservar as funções de negócios do aplicativo e interfaces semelhantes; Reduzir ou eliminar os custos de licenciamento de software de middleware; Ter agilidade em aplicativos e infraestrutura; Transformar em uma pilha semelhante a um aplicativo nativo da nuvem; Facilitar a definição e decompor em microsserviços; Reduzir os riscos, garantindo equivalência funcional.
- **Benefícios da AWS:** A arquitetura moderna de aplicativos permite melhor escalabilidade horizontal, elasticidade, eficiência de custos e melhores práticas de DevOps. Os dados tornam-se facilmente reutilizáveis nos vários serviços de Big Data e Análise de Dados da AWS. Os programas habilitados para serviço podem ser rapidamente integrados a novos casos de uso, como aplicativo móvel via Amazon API Gateway ou interfaces de voz com o Amazon Alexa.
- **Cuidado:** A ferramenta de refatoração automatizada é um fator crítico de sucesso. Essas ferramentas devem ser avaliadas minuciosamente durante uma prova de conceito (PoC) complexa, demonstrando equivalência funcional, velocidade de conversão, velocidade de testes, além de velocidade, qualidade e desempenho do código. *Batch* pode ser um bom caso de teste para o PoC complexo.

Projetos de refatoração automatizados envolvem extensos testes. Isso pode afetar drasticamente o preço e a duração do projeto, dependendo de quais ferramentas de automação estão sendo usadas, qual é o escopo dos testes, quão completos são os testes e quem é responsável por executá-los.

- **Exemplos de fornecedores:** Blu Age, [TSRI](https://aws.amazon.com/blogs/apn/automated-refactoring-of-a-u-s-department-of-defense-mainframe-to-aws/), [Modern Systems](https://aws.amazon.com/blogs/apn/mainframe-modernization-platform-as-a-service-with-modern-systems-modpaas/), [Heirloom](https://aws.amazon.com/blogs/apn/high-performance-mainframe-workloads-on-aws-with-cloud-native-heirloom-paas/).
- **Melhores práticas de fornecedores:** Muitos fornecedores fornecem ferramentas de engenharia reversa para inventário e análise aprofundada de ativos legados. Porém, poucos fornecedores fornecem engenharia avançada com alta automação (sem reescrita manual de código), conversão abrangente de programas e dados coerentes (não apenas a tradução do código linha por linha), amplo suporte de serviços da AWS (ferramenta certa para o trabalho certo) e qualidade código de manutenção.

O código de manutenção deve eliminar os idiomas COBOL legados, como GO-TOs, PERFORMERs e MOVEs (não é JOBOL). Ele também deve reduzir a complexidade do código (que pode ser medido pelo SonarQube), usar operadores, tipos e métodos de idioma nativo, permitir *multi-threading* para desempenho e adaptar-se às convenções de nomes de clientes e aos padrões de codificação.

### Replataforma de Middleware Modernos

- **Tipo de migração:** Replataforma, mantendo o mesmo middleware moderno, mas com sistemas operacionais diferentes.
- **Sistemas aplicáveis:** Esta opção se aplica aos middlewares ou *runtimes* que estão disponíveis de maneira semelhante (normalmente com a mesma base de código) para o sistema operacional legado e o sistema operacional x86. Por exemplo, aplica-se a aplicativos que dependem do IBM WebSphere Application Server, em *runtimes* PHP ou Perl, em máquinas virtuais Java ou em bancos de dados IBM DB2.
- **Descrição:** como o mesmo middleware está disponível nos sistemas operacionais, o código e os dados do aplicativo podem ser movidos e executados com alterações mínimas ou inexistentes. Por exemplo, as linguagens interpretadas são independentes de plataforma. No lado do banco de dados, o mesmo esquema de dados é reutilizado ou são realizadas adaptações para migrar para um tipo de banco de dados diferente.

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-6-1024x522.png)

*Figura 6 – Replataforma de Middleware Modernos*

 

**Exemplo de pilha de destino:** a replataforma pode usar, dependendo do suporte e dos pré-requisitos de software de middleware, instâncias do Amazon EC2 e AWS Managed Services, como [Amazon Elastic Beanstalk](https://aws.amazon.com/pt/elasticbeanstalk/), Amazon EKS, Aurora e Amazon RDS.

Abordagem de migração: como os aplicativos e os dados dependem de middleware específico de fornecedores terceirizados, procedimentos e instruções de migração específicos dos mesmos fornecedores devem ser seguidos para permanecer no caminho de migração suportado. Esse procedimento pode envolver exportação, importação de pacotes de aplicativos ou backup e restauração de bancos de dados, incluindo *schemas* e dados.

**Casos de uso típicos:** padronizar a pilha técnica do software; Mover para serviços gerenciados; Deixar sistemas operacionais proprietários caros.

**Benefícios da reformulação do middleware:** eliminar os sistemas operacionais legados; Ativar à agilidade da infraestrutura com elasticidade, tipos de instância, práticas recomendadas de DevOps e Infraestrutura como Código (IaC).

**Cuidado:** Pode haver desafios se o aplicativo usar funções nativas do sistema operacional ou se o middleware não suportar o mesmo conjunto de recursos entre plataformas.

### Outras opções que você pode considerar

**A Reescrita Manual** requer a reestruturação da lógica de negócios do zero e manualmente na nova linguagem de programação e a re-arquitetura dos serviços de infraestrutura. Para aplicativos herdados típicos com milhões de linhas de código, essa abordagem tem riscos mais altos:

- Tentando capturar as especificações lógicas antigas.
- Erros com desenvolvimento manual de código.
- Inconsistências de funções de negócios.
- Teste de funções que não são mais parecidas.
- Gerenciando projetos políticos muito grandes com muitas pessoas durante um período de 4-5 anos.

A reescrita manual é mais adequada para funções básicas e para identificar transações ou programas com escopo, interfaces e dados limitados e claros.

**A Recompra** com um pacote de software envolve identificar e substituir o aplicativo doméstico herdado por um aplicativo empacotado de terceiros. Normalmente, isso é mais adequado para aplicativos cuja lógica principal é melhor desenvolvida por um fornecedor terceirizado. Por exemplo, uma solução de pagamento SaaS ou uma solução de cadeia de suprimentos SaaS específica da indústria.

Dependendo do aplicativo legado executar ou não as funções de negócios principais, a padronização para um pacote de software não-diferenciado pode resultar na perda de vantagem competitiva. Com esses projetos, há riscos ao tentar capturar regras de negócios do aplicativo legado, e há riscos na escalada de desenvolvimentos manuais e personalizações manuais, necessárias para atender às necessidades de negócios.

### Migração versus incremento de funcionalidade

A migração trata de mover aplicativos de forma incremental, mas permanente, de uma plataforma legada para a AWS e, eventualmente, desligar o hardware legado. No entanto, alguns clientes desejam manter a plataforma legada por certo tempo e ainda se beneficiam da proposta de valor da AWS. Esses clientes podem incrementar funcionalidade à sua plataforma legada com os serviços da AWS.

Por exemplo, temos clientes que usam com êxito a AWS para análise de dados legados e para habilitar novas interfaces, como mobile ou voz. Esses clientes geralmente usam replicação de dados entre o armazenamento de dados legado e os serviços de dados da AWS.

Outros clientes optam por escalar ambientes de desenvolvimento e teste na AWS. Normalmente, eles utilizam um IDE (Integrated Development Environment) na AWS, e emuladores descritos anteriormente para testes, e promovem código com um pipeline de volta à plataforma legada para produção.

Além disso, existem outros clientes que substituem seu armazenamento caro de backup e arquivamento (como hardware de fita virtual) por soluções de backup em armazenamento em nuvem com custo otimizado.

### Qualidade do serviço

Os sistemas legados geralmente têm requisitos não funcionais rigorosos. A AWS oferece vários serviços e recursos para criar e operar sistemas seguros, de alto desempenho, resilientes e eficientes que suportam cargas de trabalho corporativas. Por exemplo: criptografia de dados de segurança com o [AWS Key Management Service](https://aws.amazon.com/pt/kms/) (KMS); confiabilidade com Zonas de Dispoinbilidade (AZs) e Regiões; elasticidade com grupos de dimensionamento automático; gerenciamento de sistema com o [AWS Systems Manager](https://aws.amazon.com/pt/systems-manager/) e o Amazon CloudWatch.

A [AWS Well-Architected Tool](https://aws.amazon.com/pt/well-architected-tool/) e o [AWS Trusted Advisor](https://aws.amazon.com/pt/premiumsupport/technology/trusted-advisor/) ajudam a criar e operar sistemas seguros, eficientes e econômicos na nuvem. Além disso, a AWS agrega agilidade às cargas de trabalho, fornecendo velocidade na nuvem, serviços gerenciados, grande variedade de serviços e inovação facilitada.

### Abordagem de migração

Não há um modelo único para a modernização legada. Os clientes precisam da ferramenta certa para o trabalho certo, alinhada à estratégia de TI e às restrições técnicas legadas. Devido à complexidade técnica, qualquer definição de abordagem deve incluir uma Prova de Conceito (PoC) prática, confirmando se as recomendações de abordagem e ferramenta são viáveis.

Ao considerar à avaliação para uma migração de carga de trabalho legada, as seguintes entregas facilitam o processo de decisão:

- Inventário de ativos a serem migrados.
- PoC complexo comprovando viabilidade técnica.
- Descrição detalhada da abordagem de migração.
- Plano de projeto em fases para migração completa.
- Estimativas de custo de projeto e dimensionamento da AWS.
- Caso de negócios para migração herdada, incluindo ROI.

Para saber mais sobre os recursos de migração legados para a AWS, entre em contato com seu representante da AWS e analise nossas [soluções de parceiros no Blog da APN](https://aws.amazon.com/pt/blogs/apn/).

------

#### Revisores técnicos – idioma local

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Author_1.png)**João Aragão Pereira**

FSI Solution Architect, Amazon Web Services

 

 

 

 **![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Author_2.png)Erico Penna**

Sr Partner SA, Amazon Web Services

TAGS: [AWS Partner Solutions Architects (SA)](https://aws.amazon.com/pt/blogs/aws-brasil/tag/aws-partner-solutions-architects-sa/), [Enterprise Strategy](https://aws.amazon.com/pt/blogs/aws-brasil/tag/enterprise-strategy/), [Legacy Modernization](https://aws.amazon.com/pt/blogs/aws-brasil/tag/legacy-modernization/), [Mainframe Modernization](https://aws.amazon.com/pt/blogs/aws-brasil/tag/mainframe-modernization/), [Mainframes](https://aws.amazon.com/pt/blogs/aws-brasil/tag/mainframes/), [Migration](https://aws.amazon.com/pt/blogs/aws-brasil/tag/migration/)Desmistificando as opções de Migração do Legado para a AWS

by [AWS Editorial Team](https://aws.amazon.com/pt/blogs/aws-brasil/author/admin/) | on 14 OCT 2019 | [Permalink](https://aws.amazon.com/pt/blogs/aws-brasil/desmistificando-as-opcoes-de-migracao-do-legado-para-a-aws/) | [ Share](https://aws.amazon.com/pt/blogs/aws-brasil/desmistificando-as-opcoes-de-migracao-do-legado-para-a-aws/#)

Por Phil de Valence, Arquiteto de soluções para Legacy Modernization na AWS

Muitas empresas ou instituições ainda possuem sistemas legados não-x86 em seus datacenters: sistemas proprietários de mainframe, midrange ou UNIX. ![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Image_1.jpg)

A migração dessas cargas de trabalho das arquiteturas de hardware para a Amazon Web Services (AWS) Cloud requer tecnologia de software avançada. As abordagens de migração de curto prazo usam principalmente emulação de hardware, emulação de middleware, refatoração automática ou reformulação de middleware.

Este post destaca as opções de migração de curto prazo, suas principais diferenças técnicas e seus benefícios diferenciados. Essas opções são particularmente adequadas para aplicativos domésticos personalizados em execução em uma plataforma herdada, onde o código fonte completo está disponível. Por outro lado, aplicativos em pacote de terceiros geralmente exigem discussão com o fornecedor de software para opções de modernização para a AWS.

### Opções de migração a curto prazo

Essas opções de migração resultam em uma duração mais curta do projeto para retorno mais rápido sobre o investimento (ROI) e ganhos rápidos.

O diagrama na Figura 1 mostra, para cada opção, componentes que mudam e componentes que permanecem os mesmos durante a migração da plataforma herdada não-x86.

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-1-1024x494.png)

*Figura 1 – Alterações de componentes na migração do legado.*

 

- Emulação de hardware Legado: o emulador de hardware substitui o hardware legado, mas o sistema operacional legado e os aplicativos permanecem os mesmos.
- Emulação de Middleware Legado: O emulador de middleware substitui as APIs de middleware legados e as APIs de SO exigidas pelo aplicativo, permitindo a portabilidade. A maior parte do código fonte do aplicativo é recompilada sem alterações, com algumas adaptações para dependências alteradas.
- Re-fatoração automatizada do legado: código, dados e dependências são convertidos automaticamente em uma linguagem moderna, armazenamento de dados e frameworks, garantindo equivalência funcional às mesmas funções de negócios.
- Re-plataforma de Middleware moderno: aplica-se apenas às linguagens modernas, middleware e runtimes disponíveis em sistemas legados e x86, como Java, PHP e bancos de dados relacionais. Permite reutilizar o código do aplicativo e os bancos de dados.

### Proposições de valores diferenciadas

Cada opção de migração possui seus casos de uso preferenciais e proposta de valor exclusivo, relevantes para uma carga de trabalho legada específica.

Considerando uma carga de trabalho de tamanho médio com alguns milhões de linhas de código, o diagrama na Figura 2 mostra as principais características diferenciadoras, como custo do projeto, duração do projeto e agilidade na nuvem, conforme representado pelo [Modelo de Maturidade em Nuvem-Nativo](https://aws.amazon.com/pt/blogs/apn/journey-to-being-cloud-native-how-and-where-should-you-start/). Esse modelo promove o uso dos [serviços gerenciados da AWS](https://aws.amazon.com/pt/managed-services/features/), dos princípios de design dos [Doze-Fatores de um Aplicativo](https://12factor.net/), dos [Microsserviços](https://aws.amazon.com/pt/microservices/) e da automação, assim como [Integração Contínua/Implantação contínua](https://aws.amazon.com/pt/devops/continuous-integration/) (CI/CD).

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-2-1024x599.png)

*Figura 2 – Opções de migração relativas à duração, custo e agilidade.*

 

Detalhes e explicações sobre cada uma das migrações são fornecidos nas sessões subsequentes.

### Emulação de hardware legado

- **Tipo de migração:** Re-hospedar usando emulação de hardware.
- **Sistemas aplicáveis:** Esta opção se aplica aos mainframes IBM Z, mainframes Unisys ClearPath, máquinas SPARC, computadores AlphaServer, estações VAX, computadores HP 3000 e HP 9000, minicomputadores PDP, e outros. Permite executar sistemas operacionais como IBM z/OS, Unisys ClearPath MCP ou OS2200, Solaris, SunOS, HP-UX, MPE, OpenVMS, Tru64, RSX-11, RSTS-11, RSTS ou RT-11, sobre a infraestrutura da AWS.
- **Descrição:** o software emulador do fornecedor emula o conjunto de instruções de hardware legado. Portanto, ele pode executar os binários legados em cima de um conjunto moderno de instruções Linux e x86-64. Ele permite executar o sistema operacional legado e seus aplicativos sem alterações, sem necessidade de recompilar o código-fonte ou transformar os binários.

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-3-1024x537.png)

*Figura 3 – Emulação de hardware legado.*

 

- **Exemplo de pilha de destino:** Os emuladores de hardware do fornecedor são executados nas instâncias do [Amazon Elastic Compute Cloud](https://aws.amazon.com/pt/ec2/) (Amazon EC2). Por causa do sistema operacional legado, o AWS Managed Services não é usado para computação ou dados.
- **Abordagem de migração:** esse é uma nova hospedagem lift-and-shift do Sistema Operacional legado do hardware legado para o emulador de software, porque o sistema operacional de origem, os binários e os arquivos permanecem inalterados. Geralmente, isso é feito com uma restauração do backup ou restauração do dump do Sistema Operacional legado, e a transferência dos arquivos de backup é através do [AWS Direct Connect](https://aws.amazon.com/pt/directconnect/) ou [AWS Snowbal](https://aws.amazon.com/pt/snowball/)l. Os aplicativos, dados e interfaces permanecem inalterados e a quantidade de testes necessários é reduzida, permitindo migrações em dias ou semanas.
- **Casos de uso típicos:** Migrando ambientes de desenvolvimento e teste para a AWS: Migrando aplicativos de produção estabilizados para a AWS; Manter a mesma pilha de software de desenvolvimento de aplicativos enquanto moderniza o hardware; O datacenter foi descontinuado, incluindo o descomissionamento de hardware legado.
- **Benefícios do emulador de hardware:** Nenhuma alteração no código do aplicativo, no middleware e no sistema operacional. Mesmas interfaces e mesmos protocolos de comunicação; Migração transparente para usuários finais e proprietários de aplicativos.
- **Benefícios da AWS:** Grande variedade de tipos de instância do Amazon EC2 para CPU, memória, armazenamento, largura de banda da rede; Alterações de capacidade e escalabilidade em minutos; Custo otimizado com o modelo de pagamento conforme o uso dos recursos/serviços da AWS ou Instâncias reservadas (RI); Maior disponibilidade nas zonas de disponibilidade (AZ).
- **Cuidado:** A emulação de conjuntos de instruções de hardware requer tradução imediata, o que afeta o desempenho. Dependendo da idade do hardware de origem e do tipo de software emulador, esse impacto no desempenho pode ser mais ou menos perceptível. De qualquer forma, é recomendado um benchmark de desempenho. As instâncias do Amazon EC2 com a velocidade de clock do processador mais rápida, assim como as instâncias z1d com 4,0 GHz, podem ajudar.
- **Exemplos de fornecedores:** [Stromasys Charon](https://aws.amazon.com/blogs/apn/re-hosting-sparc-alpha-or-other-legacy-systems-to-aws-with-stromasys/), [IBM Z Development and Test Environment](https://developer.ibm.com/mainframe/products/z-systems-development-test-environment/), [Unisys ClearPath Forward](https://assets.unisys.com/Documents/Global/ProductInformationSheets/PI_150523_ClearPathForwardSystem.pdf).
- **Melhores práticas de fornecedores:** é importante entender como cada fornecedor otimiza a tradução de instruções do emulador e possíveis opções de ajuste de desempenho com a AWS.

### Emulação de Middleware Legado

- **Tipo de migração:** Re-plataforma com código portado para um emulador de middleware.
- **Sistemas aplicáveis:** Esta opção se aplica a alguns mainframes IBM Z, mainframes Unisys ClearPath, IBM AS/400, iSeries e IBM i. Permite transportar e recompilar aplicativos que anteriormente dependiam de middleware e armazenamentos de dados legados, como IBM CICS, IMS, VSAM, QSAM, Unisys COMS, TIP, IBM DB2 para z/OS, DB2 para i (DB2/400) e Adabas. Esses aplicativos podem ser escritos em linguagens como COBOL, PL/I, RPG e Natural.
- **Descrição:** o software do emulador de fornecedor emula APIs de middleware e sistema operacional necessárias para o código do aplicativo. Por exemplo, emuladores de middleware podem fornecer APIs para acesso aos arquivos indexados, gerenciamento de transações, suporte a telas e protocolos legados, armazenamento temporário e suporte a Batch. Isso permite portar e recompilar o código do aplicativo de origem para execução nativa de x86-64.

Se um idioma específico não for suportado, primeiramente ele precisará ser convertido para um idioma suportado. Devido à recompilação, não há tradução de instruções em tempo real realizada pelo emulador e, consequentemente, nenhum impacto relacionado ao desempenho. Dependências ou utilitários não fornecidos pelo emulador (agendador, impressão, segurança, etc.) precisam ser substituídos por equivalentes x86 com prováveis adaptações de código ou configuração correspondentes.

O formato de dados legado é ou retido (VSAM, QSAM) ou mapeado para um armazenamento de dados relacionais, como [Amazon Aurora](https://aws.amazon.com/pt/rds/aurora/), [Amazon RDS para Oracle](https://aws.amazon.com/pt/rds/oracle/) ou [Amazon RDS para SQL Server](https://aws.amazon.com/pt/rds/sqlserver/).

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-4-1024x517.png)

*Figura 4 – Emulação de middleware legado.*

 

- **Exemplo de pilha de destino:** Os emuladores de middleware do fornecedor geralmente são executados nas instâncias do Amazon EC2. Algumas dependências de segurança, agendamento, impressão ou enfileiramento de mensagens são implantadas em suas próprias instâncias. Os armazenamentos de dados podem ser modernizados para se beneficiar dos serviços gerenciados do Amazon RDS, incluindo o Amazon Aurora. Alguns aplicativos podem se beneficiar do [AWS Auto Scaling](https://aws.amazon.com/pt/autoscaling/) e [Elastic Load Balancing](https://aws.amazon.com/pt/elasticloadbalancing/) entre Zonas de Disponibilidade (AZs).
- **Abordagem de migração:** devido às alterações no SO, no middleware e na dependência, nas adaptações de código, na conversão do formato de dados e na recompilação completa, este é um projeto de reformulação em que os programas e funções de negócios são migrados e testados de maneira incremental.

Começa com a descoberta de todos os programas, dados, dependências e integrações. Ele continua projetando a arquitetura de destino e novas dependências, definindo as conversões e substituições da linguagem de programação e planejando os pacotes de trabalho e as transições. Em seguida, a maior parte da migração acontece com alterações automatizadas em massa no código-fonte, atualizações nas regras de migração de código, conversão de dados correspondente e teste.

Os testes se concentram em alterações de código, dados, dependências e integrações. Depois que os testes de unidade, regressão, integração e desempenho são bem-sucedidos, os aplicativos e os dados são implantados em seus ambientes AWS de destino. Mais detalhes estão disponíveis em [Migrando um mainframe para a AWS em 5 etapas](https://aws.amazon.com/pt/blogs/apn/migrating-a-mainframe-to-aws-in-5-steps/) e em um exemplo de cliente em [Migração completa de mainframe para AWS com parceiros](https://aws.amazon.com/pt/blogs/apn/complete-mainframe-to-aws-migration-with-candid-partners/). Essa migração pode durar entre meses e anos, dependendo do número de linhas de código e de outros fatores.

- **Casos de uso típicos:** migrando de uma pilha legada e cara de hardware e software legado; Reter o investimento no código do aplicativo, mantendo a equipe de desenvolvimento e modernizando a infraestrutura subjacente; Migrando ambientes de desenvolvimento e teste para a AWS; Migrando aplicativos de produção estabilizados para a AWS.
- **Benefícios do emulador de middleware:** Eliminar software e hardware de fornecedores legados; Preservar a linguagem de programação de aplicativos, código e habilidades de desenvolvimento; Mesmas interfaces e protocolos de comunicação; Migração transparente para usuários finais; Facilitar a modernização e integração com serviços em nuvem; Reduzir os riscos preservando a mesma lógica e código.
- **Benefícios da AWS:** inclui os benefícios da AWS descritos para o emulador de hardware, além da capacidade de usar os Serviços Gerenciados da AWS, como Amazon RDS ou Elastic Load Balancing. Alguns aplicativos podem se beneficiar da escalabilidade horizontal e elasticidade com os Grupos de Dimensionamento Automático. Os aplicativos podem se beneficiar dos serviços DevOps para gerenciar um pipeline de CI/CD.
- **Cuidado:** Esses projetos não são *lift-and-shift*. Requer análise e planejamento detalhados para alterações de dependência, adaptações de código, conversão de dados e testes completos. Alguns códigos de aplicativos ou formatos de dados legados podem dificultar o uso das práticas recomendadas da AWS, para escalabilidade e disponibilidade.

Se uma linguagem ou ativo não for suportado pelo emulador (Assembly, código gerado, bancos de dados proprietários), a complexidade aumentará drasticamente. Os aplicativos contam principalmente com o emulador de middleware para integração de serviços da AWS. Diferentes fornecedores de emuladores de middleware têm recursos diferentes para integrações e otimizações da AWS.

- Exemplos de fornecedores: [Micro Focus Enterprise Server](https://aws.amazon.com/quickstart/architecture/micro-focus-enterprise-server/), [NTT DATA UniKix](https://aws.amazon.com/blogs/apn/re-hosting-mainframe-applications-to-aws-with-ntt-data-services/), [TmaxSoft OpenFrame](https://www.tmaxsoft.com/products/openframe/), [Astadia OpenMCS](https://aws.amazon.com/blogs/apn/migrating-a-mainframe-to-aws-in-5-steps/), [Infinite i](https://aws.amazon.com/marketplace/pp/B07JLVHCXF).
- Melhores práticas de fornecedores: os aplicativos se beneficiam de uma melhor disponibilidade, elasticidade, desempenho e otimização de custos ao usar a escalabilidade horizontal da AWS. Os emuladores de middleware devem facilitar a escalabilidade horizontal, especialmente para armazenamentos de dados legados, estruturas de dados compartilhadas na memória, favorecendo arquiteturas ativo/ativo entre Zonas de Disponibilidade (AZs).

Os emuladores de middleware também se diferenciam com o suporte a recursos da AWS, como Amazon Aurora, Amazon RDS, [Amazon Linux](https://aws.amazon.com/pt/mp/solutions/amazonlinux/) e [Amazon CloudWatch](https://aws.amazon.com/pt/cloudwatch/).

### Refatoração automática do legado

- **Tipo de migração:** refatoração automática com conversão de código, dependências e dados.
- **Sistemas aplicáveis:** Esta opção se aplica a linguagens como COBOL, PL/I, RPG, Natural e FORTRAN, incluindo geradores de código, como aplicativos Cool: Gen ou PowerBuilder. Ele converte modelos de dados de armazenamentos de dados, como IBM DB2 z/OS, VSAM, QSAM, IMS DB, DB2 para i (DB2/400), Adabas e Data Management System.

Isso significa que muitos aplicativos hospedados nos mainframes IBM Z, mainframes Unisys ClearPath, IBM AS/400, iSeries e IBM i podem se beneficiar da refatoração automática da AWS.

- **Descrição:** A refatoração automatizada não é uma reescrita manual de código, mas uma conversão e geração automatizada para códigos modernos, do acesso aos dados, do formato de dados e das dependências por completo. Essa transformação exaustiva e coerente garante equivalência funcional, enquanto a automação aumenta a velocidade e reduz os riscos.

Essa transformação aplica padrões e regras para transformar os componentes legados, como telas legadas, acesso aos arquivos indexados e *batch* em uma pilha de destino moderna com aplicativos Orientado a Objetos e Orientado a Serviços. É possível escolher à linguagem de programação (Java ou .NET), escolha de estruturas de *back-end* (por exemplo, Spring) e estruturas de *front-end* (por exemplo, Angular).

As ferramentas de refatoração automatizadas oferecem a você, imediatamente, a capacidade de escolher vários serviços subjacentes da AWS enquanto se transforma em aplicativos nativos da nuvem. A refatoração também pode isolar grupos de programas e dados dependentes, facilitando a identificação e criação de microsserviços.

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-5-1024x468.png)

*Figura 5 – Refatoração Automática do Legado*

 

- **Exemplo de pilha de destino:** por padrão, as ferramentas do fornecedor convertem a pilha de execução nas instâncias do Amazon EC2 para computação, no Aurora ou no Amazon RDS para armazenamento de dados, criando uma arquitetura Web elástica típica. Com a flexibilidade da refatoração automatizada e a capacidade de ajustar as regras de transformação, muitos outros serviços gerenciados da AWS podem ser incorporados, como o [Amazon Simple Queue Service](https://aws.amazon.com/pt/sqs/) (SQS) para mensagens ou o [Amazon ElastiCache](https://aws.amazon.com/pt/elasticache/) para estruturas de dados compartilhadas na memória.

Alguns aplicativos também podem se beneficiar da execução em contêineres no [Amazon Elastic Container Service](https://aws.amazon.com/pt/ecs/) (Amazon ECS) e [Amazon Elastic Container Service para Kubernetes](https://aws.amazon.com/pt/eks/) (Amazon EKS), ou nas funções sem servidor do [AWS Lambda](https://aws.amazon.com/pt/lambda/). Como a nova pilha é habilitada para serviço, as funções de negócios são facilmente publicadas para novos clientes, como aplicativos móveis por meio do Amazon [API Gateway](https://aws.amazon.com/pt/api-gateway/).

- **Abordagem de migração:** a abordagem geral e as fases de um projeto de refatoração automatizada do legado são semelhantes às de um projeto de emulação de middleware legado, porque ambos incluem um inventário de ativos, mapeando as dependências do aplicativo para os novos componentes da pilha, as alterações em massa na origem código, compilação de código e testes extensivos, que podem levar de 60 a 80% do tempo gasto no projeto.

Mais especificamente, as ferramentas de refatoração automatizadas permitem a engenharia reversa do código do aplicativo e dos modelos de dados, a fim de criar um modelo de aplicativo mostrando todas as dependências do programa e dos dados, além de suas principais características. Esse modelo detalhado é usado para definir a estratégia de migração, mapeamentos de componentes e dados, regras de conversão de código e formato de dados, decomposição de pacotes de trabalho e transições.

A maior parte da migração ocorre com conversões automatizadas de código e dados, com transições incrementais, atualizações nas regras de conversão, testes extensivos e sem reescrita manual do código. Mais detalhes estão disponíveis com exemplos de clientes em “[Refatoração automatizada de um mainframe do New York Times para a AWS com sistemas modernos](https://aws.amazon.com/pt/blogs/apn/automated-refactoring-of-a-new-york-times-mainframe-to-aws-with-modern-systems/)” e em “[Refatoração automatizada de um mainframe do Departamento de Defesa dos EUA para a AWS](https://aws.amazon.com/pt/blogs/apn/automated-refactoring-of-a-u-s-department-of-defense-mainframe-to-aws/)“. Essa migração geral pode durar meses ou anos, dependendo do número de linhas de código e outros fatores:

- **Casos de uso típicos:** migrar de idiomas como COBOL, PL/I, RPG e Natural; Modernizar e padronizar a pilha técnica completa, mantendo o investimento das funções de negócios do aplicativo; Resolver às lacunas de habilidades legadas; Inovar com práticas ágeis, serviços gerenciados e tecnologias nativas da nuvem.
- **Benefícios automatizados de refatoração:** Eliminar tecnologias legadas; Preservar as funções de negócios do aplicativo e interfaces semelhantes; Reduzir ou eliminar os custos de licenciamento de software de middleware; Ter agilidade em aplicativos e infraestrutura; Transformar em uma pilha semelhante a um aplicativo nativo da nuvem; Facilitar a definição e decompor em microsserviços; Reduzir os riscos, garantindo equivalência funcional.
- **Benefícios da AWS:** A arquitetura moderna de aplicativos permite melhor escalabilidade horizontal, elasticidade, eficiência de custos e melhores práticas de DevOps. Os dados tornam-se facilmente reutilizáveis nos vários serviços de Big Data e Análise de Dados da AWS. Os programas habilitados para serviço podem ser rapidamente integrados a novos casos de uso, como aplicativo móvel via Amazon API Gateway ou interfaces de voz com o Amazon Alexa.
- **Cuidado:** A ferramenta de refatoração automatizada é um fator crítico de sucesso. Essas ferramentas devem ser avaliadas minuciosamente durante uma prova de conceito (PoC) complexa, demonstrando equivalência funcional, velocidade de conversão, velocidade de testes, além de velocidade, qualidade e desempenho do código. *Batch* pode ser um bom caso de teste para o PoC complexo.

Projetos de refatoração automatizados envolvem extensos testes. Isso pode afetar drasticamente o preço e a duração do projeto, dependendo de quais ferramentas de automação estão sendo usadas, qual é o escopo dos testes, quão completos são os testes e quem é responsável por executá-los.

- **Exemplos de fornecedores:** Blu Age, [TSRI](https://aws.amazon.com/blogs/apn/automated-refactoring-of-a-u-s-department-of-defense-mainframe-to-aws/), [Modern Systems](https://aws.amazon.com/blogs/apn/mainframe-modernization-platform-as-a-service-with-modern-systems-modpaas/), [Heirloom](https://aws.amazon.com/blogs/apn/high-performance-mainframe-workloads-on-aws-with-cloud-native-heirloom-paas/).
- **Melhores práticas de fornecedores:** Muitos fornecedores fornecem ferramentas de engenharia reversa para inventário e análise aprofundada de ativos legados. Porém, poucos fornecedores fornecem engenharia avançada com alta automação (sem reescrita manual de código), conversão abrangente de programas e dados coerentes (não apenas a tradução do código linha por linha), amplo suporte de serviços da AWS (ferramenta certa para o trabalho certo) e qualidade código de manutenção.

O código de manutenção deve eliminar os idiomas COBOL legados, como GO-TOs, PERFORMERs e MOVEs (não é JOBOL). Ele também deve reduzir a complexidade do código (que pode ser medido pelo SonarQube), usar operadores, tipos e métodos de idioma nativo, permitir *multi-threading* para desempenho e adaptar-se às convenções de nomes de clientes e aos padrões de codificação.

### Replataforma de Middleware Modernos

- **Tipo de migração:** Replataforma, mantendo o mesmo middleware moderno, mas com sistemas operacionais diferentes.
- **Sistemas aplicáveis:** Esta opção se aplica aos middlewares ou *runtimes* que estão disponíveis de maneira semelhante (normalmente com a mesma base de código) para o sistema operacional legado e o sistema operacional x86. Por exemplo, aplica-se a aplicativos que dependem do IBM WebSphere Application Server, em *runtimes* PHP ou Perl, em máquinas virtuais Java ou em bancos de dados IBM DB2.
- **Descrição:** como o mesmo middleware está disponível nos sistemas operacionais, o código e os dados do aplicativo podem ser movidos e executados com alterações mínimas ou inexistentes. Por exemplo, as linguagens interpretadas são independentes de plataforma. No lado do banco de dados, o mesmo esquema de dados é reutilizado ou são realizadas adaptações para migrar para um tipo de banco de dados diferente.

 

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Demystifying-Mainframe-Migration-6-1024x522.png)

*Figura 6 – Replataforma de Middleware Modernos*

 

**Exemplo de pilha de destino:** a replataforma pode usar, dependendo do suporte e dos pré-requisitos de software de middleware, instâncias do Amazon EC2 e AWS Managed Services, como [Amazon Elastic Beanstalk](https://aws.amazon.com/pt/elasticbeanstalk/), Amazon EKS, Aurora e Amazon RDS.

Abordagem de migração: como os aplicativos e os dados dependem de middleware específico de fornecedores terceirizados, procedimentos e instruções de migração específicos dos mesmos fornecedores devem ser seguidos para permanecer no caminho de migração suportado. Esse procedimento pode envolver exportação, importação de pacotes de aplicativos ou backup e restauração de bancos de dados, incluindo *schemas* e dados.

**Casos de uso típicos:** padronizar a pilha técnica do software; Mover para serviços gerenciados; Deixar sistemas operacionais proprietários caros.

**Benefícios da reformulação do middleware:** eliminar os sistemas operacionais legados; Ativar à agilidade da infraestrutura com elasticidade, tipos de instância, práticas recomendadas de DevOps e Infraestrutura como Código (IaC).

**Cuidado:** Pode haver desafios se o aplicativo usar funções nativas do sistema operacional ou se o middleware não suportar o mesmo conjunto de recursos entre plataformas.

### Outras opções que você pode considerar

**A Reescrita Manual** requer a reestruturação da lógica de negócios do zero e manualmente na nova linguagem de programação e a re-arquitetura dos serviços de infraestrutura. Para aplicativos herdados típicos com milhões de linhas de código, essa abordagem tem riscos mais altos:

- Tentando capturar as especificações lógicas antigas.
- Erros com desenvolvimento manual de código.
- Inconsistências de funções de negócios.
- Teste de funções que não são mais parecidas.
- Gerenciando projetos políticos muito grandes com muitas pessoas durante um período de 4-5 anos.

A reescrita manual é mais adequada para funções básicas e para identificar transações ou programas com escopo, interfaces e dados limitados e claros.

**A Recompra** com um pacote de software envolve identificar e substituir o aplicativo doméstico herdado por um aplicativo empacotado de terceiros. Normalmente, isso é mais adequado para aplicativos cuja lógica principal é melhor desenvolvida por um fornecedor terceirizado. Por exemplo, uma solução de pagamento SaaS ou uma solução de cadeia de suprimentos SaaS específica da indústria.

Dependendo do aplicativo legado executar ou não as funções de negócios principais, a padronização para um pacote de software não-diferenciado pode resultar na perda de vantagem competitiva. Com esses projetos, há riscos ao tentar capturar regras de negócios do aplicativo legado, e há riscos na escalada de desenvolvimentos manuais e personalizações manuais, necessárias para atender às necessidades de negócios.

### Migração versus incremento de funcionalidade

A migração trata de mover aplicativos de forma incremental, mas permanente, de uma plataforma legada para a AWS e, eventualmente, desligar o hardware legado. No entanto, alguns clientes desejam manter a plataforma legada por certo tempo e ainda se beneficiam da proposta de valor da AWS. Esses clientes podem incrementar funcionalidade à sua plataforma legada com os serviços da AWS.

Por exemplo, temos clientes que usam com êxito a AWS para análise de dados legados e para habilitar novas interfaces, como mobile ou voz. Esses clientes geralmente usam replicação de dados entre o armazenamento de dados legado e os serviços de dados da AWS.

Outros clientes optam por escalar ambientes de desenvolvimento e teste na AWS. Normalmente, eles utilizam um IDE (Integrated Development Environment) na AWS, e emuladores descritos anteriormente para testes, e promovem código com um pipeline de volta à plataforma legada para produção.

Além disso, existem outros clientes que substituem seu armazenamento caro de backup e arquivamento (como hardware de fita virtual) por soluções de backup em armazenamento em nuvem com custo otimizado.

### Qualidade do serviço

Os sistemas legados geralmente têm requisitos não funcionais rigorosos. A AWS oferece vários serviços e recursos para criar e operar sistemas seguros, de alto desempenho, resilientes e eficientes que suportam cargas de trabalho corporativas. Por exemplo: criptografia de dados de segurança com o [AWS Key Management Service](https://aws.amazon.com/pt/kms/) (KMS); confiabilidade com Zonas de Dispoinbilidade (AZs) e Regiões; elasticidade com grupos de dimensionamento automático; gerenciamento de sistema com o [AWS Systems Manager](https://aws.amazon.com/pt/systems-manager/) e o Amazon CloudWatch.

A [AWS Well-Architected Tool](https://aws.amazon.com/pt/well-architected-tool/) e o [AWS Trusted Advisor](https://aws.amazon.com/pt/premiumsupport/technology/trusted-advisor/) ajudam a criar e operar sistemas seguros, eficientes e econômicos na nuvem. Além disso, a AWS agrega agilidade às cargas de trabalho, fornecendo velocidade na nuvem, serviços gerenciados, grande variedade de serviços e inovação facilitada.

### Abordagem de migração

Não há um modelo único para a modernização legada. Os clientes precisam da ferramenta certa para o trabalho certo, alinhada à estratégia de TI e às restrições técnicas legadas. Devido à complexidade técnica, qualquer definição de abordagem deve incluir uma Prova de Conceito (PoC) prática, confirmando se as recomendações de abordagem e ferramenta são viáveis.

Ao considerar à avaliação para uma migração de carga de trabalho legada, as seguintes entregas facilitam o processo de decisão:

- Inventário de ativos a serem migrados.
- PoC complexo comprovando viabilidade técnica.
- Descrição detalhada da abordagem de migração.
- Plano de projeto em fases para migração completa.
- Estimativas de custo de projeto e dimensionamento da AWS.
- Caso de negócios para migração herdada, incluindo ROI.

Para saber mais sobre os recursos de migração legados para a AWS, entre em contato com seu representante da AWS e analise nossas [soluções de parceiros no Blog da APN](https://aws.amazon.com/pt/blogs/apn/).

------

#### Revisores técnicos – idioma local

![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Author_1.png)**João Aragão Pereira**

FSI Solution Architect, Amazon Web Services

 

 

 

 **![img](https://d2908q01vomqb2.cloudfront.net/d435a6cdd786300dff204ee7c2ef942d3e9034e2/2019/10/11/Author_2.png)Erico Penna**

Sr Partner SA, Amazon Web Services

TAGS: [AWS Partner Solutions Architects (SA)](https://aws.amazon.com/pt/blogs/aws-brasil/tag/aws-partner-solutions-architects-sa/), [Enterprise Strategy](https://aws.amazon.com/pt/blogs/aws-brasil/tag/enterprise-strategy/), [Legacy Modernization](https://aws.amazon.com/pt/blogs/aws-brasil/tag/legacy-modernization/), [Mainframe Modernization](https://aws.amazon.com/pt/blogs/aws-brasil/tag/mainframe-modernization/), [Mainframes](https://aws.amazon.com/pt/blogs/aws-brasil/tag/mainframes/), [Migration](https://aws.amazon.com/pt/blogs/aws-brasil/tag/migration/)