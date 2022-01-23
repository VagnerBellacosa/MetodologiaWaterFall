# Visão geral da migração de mainframe

Artigo - 04/01/2022
Muitas empresas e organizações se beneficiam de mover algumas ou todas as suas cargas de trabalho de mainframe, aplicativos e bancos de dados para a nuvem. O Azure fornece recursos semelhantes a mainframe em escala de nuvem sem muitas das desvantagens associadas a mainframes.

O termo mainframe geralmente se refere a um sistema de computador grande, mas, atualmente, a grande maioria de mainframes implantados são os servidores IBM System z ou sistemas compatíveis com plug da IBM executando MVS, DOS, VSE, OS/390 ou z/OS. Os sistemas de mainframe continuam sendo usados em muitos setores para executar sistemas de informações vitais, e eles têm um lugar em cenários altamente específicos, como ambientes de TI grandes, de alto volume e intensivos em transações.

Migrar para a nuvem permite que as empresas modernizem sua infraestrutura. Com os serviços de nuvem você pode disponibilizar aplicativos de mainframe e o valor que eles fornecem, como uma carga de trabalho sempre que sua organização precisar. Muitas cargas de trabalho podem ser transferidas para o Azure com apenas pequenas alterações de código, como atualizar os nomes dos bancos de dados. Você pode migrar cargas de trabalho mais complexas usando uma abordagem em fases.

A maioria das empresas da Fortune 500 já estão em executando o Azure para suas cargas de trabalho críticas. Os incentivos de reduções significativos do Azure motivam muitos projetos de migração. As empresas normalmente movem as cargas de trabalho de desenvolvimento e teste primeiro para o Azure e, em seguida, pelo DevOps, email e recuperação de desastre.

Público-alvo
Se você estiver considerando uma migração ou a adição de serviços de nuvem como uma opção para seu ambiente de TI, este guia é para você.

Este guia ajuda as organizações de TI a iniciar a conversa de migração. Você pode estar mais familiarizado com o Azure e infraestruturas de nuvem do que está com mainframes, portanto, este guia começa com uma visão geral de como funcionam os mainframes e continua com várias estratégias para determinar o que e como migrar.

Arquitetura de mainframe
No final de década de 50, os mainframes foram projetados como servidores de expansão para executar grandes volumes de transações online e processamento em lotes. Por isso, mainframes têm software para formulários de transações online (às vezes chamado de telas verdes) e sistemas de e/s de alto desempenho para as execuções em lote de processamento.

Os mainframes têm uma reputação de alta confiabilidade e disponibilidade e são conhecidos por sua capacidade de executar grandes trabalhos em lote e transações online. Uma transação resulta de uma parte do processamento iniciado por uma única solicitação, normalmente de um usuário em um terminal. As transações também podem vir de várias fontes, incluindo páginas da web, estações de trabalho remotas e aplicativos de outros sistemas de informações. Uma transação também pode ser disparada automaticamente em um horário predefinido, como mostra a figura a seguir.



Uma arquitetura típica de mainframe IBM inclui os seguintes componentes comuns:

Sistemas de front-end: Os usuários podem iniciar transações a partir de terminais, páginas da web ou estações de trabalho remotas. Aplicativos de mainframe geralmente têm interfaces do usuário personalizada que podem ser preservadas após a migração para o Azure. Emuladores de terminal (também conhecidos como "terminais de tela verde") ainda são usados para acessar os aplicativos de mainframe.

Camada de aplicativo: Mainframes geralmente incluem um CICS (Sistema de Controle de Informações do Cliente), um conjunto de gerenciamento de transações potenciais para o mainframe do IBM Z/OS que muitas vezes é usado com o IMS (Sistema de Gerenciamento de Informações) da IBM, um gerenciador de transação baseado em mensagem. Os sistemas de lote manipulam atualizações de alta taxa de transferência de dados para grandes volumes de registros de conta.

Código: Linguagens de programação usadas pelos mainframes incluem COBOL, Fortran, PL/I e Natural. A linguagem de controle de trabalho (JCL) é usada para trabalhar com o z/OS.

Camada de Banco de Dados: Um DBMS (sistema de gerenciador de banco de dados relacional) comum para z/OS é o IBM DB2. Ele gerencia as estruturas de dados chamadas dbspaces que contêm uma ou mais tabelas e são atribuídas aos pools de armazenamento físicos de conjuntos de dados chamados dbextents. Dois componentes de banco de dados importantes são o diretório que identifica os locais de dados nos pools de armazenamento e o log que contém um registro das operações executadas no banco de dados. Há suporte para vários formatos de dados de arquivo simples. Normalmente, o DB2 para z/OS usa os conjuntos de dados do VSAM (Método de Acesso de Armazenamento Virtual) para armazenar os dados.

Camada de gerenciamento: Os mainframes IBM incluem o agendamento de software como TWS-OPC, ferramentas para impressão e gerenciamento de saída como CA-SAR e SPOOL e um sistema de controle do código-fonte para código. O controle de acesso seguro para z/OS é tratado pelo recurso de controle de acesso a recursos (RACF). Um gerenciador de banco de dados fornece acesso aos dados no banco de dados e é executado em sua própria partição em um ambiente de z/OS.

LPAR: Partições lógicas ou LPARs, são usados para dividir os recursos de computação. Um mainframe físico é particionado em vários LPARs.

z/OS: Um sistema operacional de 64 bits que é mais comumente usado para mainframes IBM.

Sistemas IBM usam um monitor de transação, como o CICS para acompanhar e gerenciar todos os aspectos de uma transação comercial. O CICS gerencia o compartilhamento de recursos, a integridade dos dados e priorização de execução. O CICS autoriza usuários, aloca recursos e passa as solicitações de banco de dados pelo aplicativo para um gerenciador de banco de dados, como IBM DB2.

Para ajuste mais preciso, o CICS normalmente é usado com o IMS/TM, anteriormente conhecido como IMS/DC (IMS/Comunicações de Dados). O IMS foi projetado para reduzir a redundância de dados, mantendo uma única cópia dos dados. Ele complementa o CICS como um monitor de transação, mantendo o estado ao longo do processo e a gravação de funções de negócios em um repositório de dados.

Operações de mainframe
A seguir estão as operações de mainframe típico:

(Online): As cargas de trabalho incluem o processamento de transações, gerenciamento de banco de dados e conexões. Geralmente, são implementados usando conectores de z/OS, CICS e DB2 da IBM.

Lote: Os trabalhos são executados sem interação do usuário, normalmente em um agendamento regular, como todas as manhãs da semana. Trabalhos em lotes podem ser executados em sistemas baseados em Windows ou Linux usando um emulador JCL como um Micro Focus Server Edição Enterprise ou software Control-M BMC.

Linguagem de controle de trabalho (JCL): Especifique os recursos necessários para processar trabalhos de lote. JCL transmite essas informações para z/OS por meio de um conjunto de instruções de controle de trabalho. O JCL básico contém seis tipos de instruções:,,,, JOBASSGNDLBLEXTENTLIBDEF e EXEC . Um trabalho pode conter várias EXEC instruções (etapas), e cada etapa pode ter várias LIBDEF instruções,, ASSGNDLBL e EXTENT .

Carregamento inicial do programa (IPL): Refere-se ao carregamento de uma cópia do sistema operacional do disco para armazenamento real do processador e para executá-lo. Os IPLs são usados para se recuperar do tempo de inatividade. Um IPL é semelhante a inicialização do sistema operacional nas VMs de Linux ou Windows.

Próximas etapas
Mitos e fatos