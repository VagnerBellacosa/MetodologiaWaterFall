![Logo](https://retraining.inf.ufsc.br/guia/images/logo.png)

- [Sobre este guia](https://retraining.inf.ufsc.br/guia/app)
- Técnicas de Elicitação de Requisitos
  - [ Técnicas](https://retraining.inf.ufsc.br/guia/app/classificacoes/tecnicas-de-elicitacao-de-requisitos/entidades)
  - [ Facetas de Classificação](https://retraining.inf.ufsc.br/guia/app/classificacoes/tecnicas-de-elicitacao-de-requisitos/facetas)
- [Abordagens de elicitação de requisitos](https://retraining.inf.ufsc.br/guia/app/abordagens)
- [Publicações](https://retraining.inf.ufsc.br/guia/app/publicacoes)

- COMPARTILHE
-  

 Feedback

[Guia Facetado de Engenharia de Requisitos](https://retraining.inf.ufsc.br/guia/app)[Técnicas de Elicitação de Requisitos](https://retraining.inf.ufsc.br/guia/app/classificacoes/tecnicas-de-elicitacao-de-requisitos)[Técnicas Mapeadas](https://retraining.inf.ufsc.br/guia/app/classificacoes/tecnicas-de-elicitacao-de-requisitos/entidades)[JAD](https://retraining.inf.ufsc.br/guia/app/classificacoes/tecnicas-de-elicitacao-de-requisitos/entidades/tecnicas-de-elicitacao-de-requisitos-jad#)

#  JAD

Joint Application Development (JAD) é uma das técnicas mais utilizadas na indústria, utilizada para elicitar requisitos funcionais e não funcionais. Foi originalmente desenvolvida para uso interno da IBM. São workshops colaborativos que duram de quatro a cinco dias que resultam em um conjunto de requisitos de usuário. Ajuda a coletar muita informação em um período curto. Seu planejamento antecipado é obrigatório para estas sessões, incluindo a presença dos participantes chave. Os participantes compartilham suas opiniões sobre o que precisa ser feito e o que precisa mudar. Todas as sessões são gravadas. Em alguns casos, um protótipo pode ser um dos produtos gerados durante uma sessão. É uma técnica usada para desenvolvimento de novos produtos e para projetos de melhoria. O objetivo é envolver todos stakeholders no processo de planejamento do produto, através de reuniões altamente estruturadas. Tipicamente tem os seguintes participantes: Facilitador, Usuário, principais desenvolvedores e observadores. É similar à técnica Brainstorm, exceto pelo fato de que os stakeholders estão envolvidos na discussão sobre o sistema. A variedade de participantes de uma sessão é muito importante, pois promove uma discussão mais ampla acerca do sistema. A técnica JAD contém 5 fases distintas:

**Definição do projeto**

- Determinar o propósito, escopo e objetivos do sistema.
- Identificar os participantes.
- Estabelecer o cronograma.

**Pesquisa**

- Coletar informações detalhadas sobre os requisitos de usuários.
- Explorar as implicações técnicas, sociais e políticas.
- Considerar questões gerais do sistema, verificação do que precisa ser decidido na sessão.

**Preparação**

- Preparação para a sessão.
- Finalizar a logística para a reunião.
- Adquirir recursos visuais, documentos de trabalho e outros aparatos de reunião.
- Preparar o responsável pelas anotações.

**Sessão JAD**

- Reunir as informações e os conhecimentos dos membros da equipe do JAD na análise de solução potencial.
- Gerar soluções (requisitos de sistemas) durante o período da sessão.
- Finalizar e documentar as decisões da reunião.

**Documento final**

- Preparar o documento final com as decisões e acordos identificados durante o workshop.

## Exemplo

Neste exemplo, a equipe decidiu combinar as duas primeiras etapas da técnica JAD, entrevistando os stakeholders com base em uma série de questões:

- Qual o propósito do projeto?
- Qual seu escopo?
- Quais são as metas gerenciais e de segurança?
- Quais são as funcionalidades, restrições, premissas e problemas do projeto?
- Quem são os usuários?
- Qual é o fluxo de trabalho?

Neste exemplo, a equipe decidiu não usar nenhum recurso visual na fase de preparação, pois a comunicação com os stakeholder era principalmente via teleconferência.Como a técnica é focada no usuário e neste caso existiam algumas questões a tratar sobre a segurança de determinados requisitos, a equipe decidiu não repassar o fluxo de trabalho, os elementos de dados, telas e relatórios de etapas na fase. Portanto, o único passo restante foi discutir questões em aberto sobre a plataforma. Inicialmente os stakeholders levantaram os seguintes problemas em aberto (alguns exemplos):

- Como será fornecido a alta disponibilidade?
- Na camada da Web?
- Na camada do banco de dados?
- Como será tratado o controle de versão?
- Quais são os métodos de teste?
- Por que você está considerando a camada de soquetes seguros (SSL) para autenticar os usuários?
- Quais são os melhores procedimentos para garantir que essas ações sejam registradas?
- Como você vai gerenciar usuários e autorização?
- 100% de tempo de atividade é necessário para o projeto?
- Como a integridade do site deve ser protegida?

Através desta sessão a equipe define determinados requisitos que são relevantes para a situação apresentada, neste exemplo foram levantados requisitos relacionados a segurança:

- O sistema deve fornecer informações confiáveis para os usuários que têm acesso.
- O sistema deve garantir que apenas usuários autenticados possam acessar o conteúdo protegido.
- O sistema deve garantir a integridade do conteúdo que é fornecido aos usuários usando autenticação, autorização e controle de acesso.
- O sistema deve habilitar o controle de versão tanto no conteúdo apresentado quanto no desenvolvimento da plataforma.

![Exemplo JAD](https://retraining.inf.ufsc.br/guia/images/tecnicas-re/jad-01.png)

[2] [3] [4] [6] [7] [8] [9]

------

##  Prós

- Diminui o tempo e o custo do processo de elicitação de requisitos.
- Acelera o projeto do sistema.
- Estimula a geração de novas ideias para saídas criativas.
- Promove o feedback do usuário.
- Aumenta a satisfação dos usuários.
- Melhora a comunicação entre os stakeholders, analistas e demais profissionais.
- Recursos visuais e ferramentas usadas tornam as sessões interativas.
- Fornece uma abordagem estruturada bem formatada.
- Promove mudanças rápidas nos requisitos.

[3] [5]

##  Contras

- Se não for devidamente planejada ou se muitos stakeholders estiverem envolvidos, pode resultar em um desperdício de tempo e recursos.
- Requer facilitadores treinados.
- Requer muito planejamento e esforço.
- É uma técnica cara.
- Requer uma equipe com enorme experiência e especialização no domínio do problema.
- Se a quantidade de sessões é alta, os usuários tendem a inferir que o desenvolvedor está transferindo a responsabilidade do projeto para eles.

[1] [3] [5] [6]

##  Classificação completa

Geral

**Categoria**

Grupo

**Fonte principal**

Analistas e Stakeholders

Elicitor

**Treinamento na técnica de elicitação**

Alto

**Experiência do elicitor**

Alto

**Experiência com técnicas de elicitação**

BaixoAlto

**Familiaridade com o domínio**

BaixoAlto

Domínio do problema

**Tipo de dado**

Qualitativo

**Comunicação**

Bidirecional

**Tipo de informação a elicitar**

EstratégicaTática

**Nível de informação disponível**

Superior

**Definição do problema**

Baixo

Stakeholder

**Pessoas por sessão**

Em massa

**Consenso entre os stakeholders**

*Não informado*

**Interesse do stakeholder**

Alto

**Especialidade**

EspecialistaBem informadoIniciante

**Articulação**

MédioAlto

**Disponibilidade de tempo**

Alto

**Local/Acessibilidade**

Perto

Características gerais da técnica

**Tipo de técnica**

Direta

**Restrição de tempo do projeto**

Baixo

**Tempo de processo**

Início

------

##  Referências

- [1] YOUSEF, R.; ALMARABEH, T. An enhanced requirements elicitation framework based on business process models.Scientific Research and Essays, Academic Journals, v. 10,n. 7, p. 279–286, 2015.
- [2] KHAN, K. et al. Requirement development life cycle: The industry practices. In:IEEE.Software Engineering Research, Management and Applications (SERA), 2011 9th International Conference on. [S.l.], 2011. p. 12–16.
- [3] YOUSUF, M.; ASGER, M. Comparison of various requirements elicitation techniques.International Journal of Computer Applications, Foundation of Computer Science,v. 116, n. 4, 2015.
- [4] SHARMA, S.; PANDEY, S. Revisiting requirements elicitation techniques. International Journal of Computer Applications, Foundation of Computer Science, v. 75, n. 12, 2013.
- [5] ARIF, Q. K. Shams-ul; GAHYYUR, S. Requirements engineering processes, tools/technologies, & methodologies. International Journal of Reviews in Computing, p. 41–56, 2009.
- [6] SADIQ, M.; GHAFIR, S.; SHAHID, M. An approach for eliciting software requirements and its prioritization using analytic hierarchy process. In: IEEE. Advances in Recent Technologies in Communication and Computing, 2009. ARTCom’09. International Conference on. [S.l.], 2009. p. 790–795.
- [7] MULLA, N. Comparison of various elicitation techniques and requirement prioritisationtechniques.International Journal of Engineering Research & Technology (IJERT), v. 1,n. 3, p. 8, 2012.
- [8] MEAD, Nancy. Requirements Elicitation Case Studies Using IBIS, JAD, and ARM. 2006.
- [9] DUGGAN, E.W. & THACHENKARY, C.S. Information Technology and Management (2003) 4: 391. https://doi.org/10.1023/A:1025134318528