# Mainframe: MVS – Multiple Virtual Storage (z/OS)

Em [Segurança da Informação](https://tiagosouza.com/seguranca-informacao/)

O MVS *(Multiple Virtual Storage – Armazenamento Virtual Múltiplo)* é o **sistema operacional para mainframes da IBM** e o JCL é a linguagem de controle de tarefas para o mainframe. Você pode correlacionar o MVS ao Linux e o JCL ao Bash, por exemplo.

É executado em muitos dos mainframes e grandes servidores da IBM. Apesar de desenvolvido pela IBM, não possui vínculo com outros sistemas operacionais da empresa, como o VSE e o VM.

**Índice – Vá direto ao ponto:**

- [Introdução](https://tiagosouza.com/mainframe-mvs-multiple-virtual-storage-z-os/#introducao)
- [Comandos MVS](https://tiagosouza.com/mainframe-mvs-multiple-virtual-storage-z-os/#comandos)
- [Mensagens de MVS](https://tiagosouza.com/mainframe-mvs-multiple-virtual-storage-z-os/#mensagens)
- [Tasks de MVS](https://tiagosouza.com/mainframe-mvs-multiple-virtual-storage-z-os/#tasks)

## Introdução

O MVS é o nome que é dado a um sistema mainframe, é o nome do sistema operacional conhecido como z/OS.

###### LPAR:

O sistema MVS é uma Imagem Virtual em uma memória física. É chamado de partição lógica ou *Logical Partition* (LPAR). Muito parecido quando se “particiona” o HD de um PC, e monta-se partições lógicas de um HD físico.

###### TASK:

O MVS sem seus aplicativos, não é nada. Os aplicativos que ajudam o MVS são chamados de **TASK.**

Uma Task (ou “tarefa”), é um aplicativo que está no sistema por algum motivo específico. Esta Task pode ser para acessar os dados que o Mainframe processa e armazena, pode ser para controlar a entrada de usuários ou para manter um Buffer da memória do sistema.

Uma Task ou aplicativo em especial é o JES. Este cuida da entrada e saída de Jobs no sistema, controla o número de usuários que vão estar utilizando sistema e até outras Tasks.

###### JOB:

Em um sistema Mainframe, além dos aplicativos, existem outras entidades, o JOB e o USUÁRIO. Os dois serão citados em outros tópicos.

Um Job é parecido com um aplicativo, mas é temporário, não fica instalado no sistema como um programa. O Job funciona por passos chamados **STEPS**, sendo que cada passo executa um programa. Uma atividade pode conter vários Job’s para que seja realizada.

Para entender melhor como o MVS gerencia seus aplicativos, é possível comparar a lista de entidades ativas no MVS ao **Task Manager** (gerenciador de tarefas) em um PC. Tudo o que estiver executando como aplicativo em um sistema, mesmo estando transparente ao usuário, estará na lista de ativos do MVS.

O JES tem sua própria lista de ativos, mas esta será comentada no tópico sobre JES.

O MVS possui várias entidades em sua arquitetura, e cada uma terá um tópico específico, mas poderá ver aqui uma breve explicação.

O Mainframe possui três partes distintas no processamento dos dados: **entrada de dados**, **processamento de dados** e **armazenamento de dados**. Veja detalhes a seguir:

1. Para a **entrada dos dados**, existem os terminais de Mainframe para usuários e as conexões com servidores.
2. Para **processamento de dados**, o Mainframe usa o MVS, que tem TASKS e Jobs que acessam e processam dados.
3. Para a **saída e armazenamento de dados**, o Mainframe tem os bancos de dados e Datasets que são armazenados em discos (**DASD**) e fitas (**TAPE**), e também as impressoras, que imprimem relatórios de processos.

###### Console:

A console de um sistema é uma das interfaces entre um operador e o sistema. A *console* ou *Master Console* é uma tela que mostra todo o Log do sistema passando por esta tela. Ela pode ser usada para enviar comandos diretamente ao sistema ou aos aplicativos do sistema.

A tela da console lembra *Matrix*, uma tela preta com letras verdes.

Algumas mensagens podem vir em cores diferentes, o que pode indicar um problema, ou pode ser apenas informativa, ou, ainda, pode enviar um Reply, que é uma mensagem que pede ação do operador. Alguns comandos relacionados a console e seu funcionamento estarão no tópico de comandos.

O Mainframe ainda possui algumas subdivisões bem distintas do modo de tratar os dados que ele deve processar e armazenar. Aqui serão mostradas e comparadas estas subdivisões:

- Batch e Online
- Dataset e Database
- Job e Task

###### BATCH e ONLINE:

O processo Batch de um sistema Mainframe tem como principais funções: ler, alterar, criar e apagar dados. E qual seria a diferença entre Batch e Online se o processo Online faz o mesmo? O processo Batch, que é realizado através de Job, geralmente, faz alterações **PROGRAMADAS**, enquanto que o **ONLINE** se utiliza de aplicativos como o IMS e CICS para manusear os dados em **TEMPO REAL.**

Um bom exemplo de Online é o acesso a uma conta bancária: quando alguém está acessando uma conta bancária, este usuário tem toda autoridade para ver e alterar esta conta sacando dinheiro, por exemplo; esta ação está ocorrendo em Tempo Real. Já quando um usuário tenta acessar a conta na madrugada e o sistema do banco se mostra indisponível, este é o momento de processamento Batch. O processamento Batch é usado para alterações programadas que podem ser cópias de segurança dos dados, ou uma transferência bancária, como por exemplo, um DOC, que não é feito na hora, pois demanda mais trabalho e procedimentos mais complexos.

###### DATASET e DATABASE:

Um **Dataset** é um pacote de dados que é usado para armazenar todo tipo de informação, seja ela interna do sistema, ou referente ao próprio sistema, ou até informações para operadores e suportes técnico deste sistema. Se fôssemos comparar, um dataset se parece com o Word ou bloco de notas, estes mesmos que se usa para anotar textos, etc.

Já o **Database** é um banco de dados que é usado para arquivar informações que serão disponibilizadas a usuários, ou seja, toda informação, sigilosa ou não, que a empresa dona do sistema quiser que seja processada e armazenada em um sistema Mainframe estará em um banco de dados. O Database se utiliza de arquitetura de armazenamento de dados em tabelas, ou seja, se parece com o Excel.

###### JOB e TASK:

Uma **TASK**, como já mencionado acima, é um aplicativo de sistema, ou seja, é igual aos aplicativos que se tem em um PC que ficam instalados no sistema operacional e podem servir para utilização dos usuários ou para o funcionamento do próprio sistema. Muitas Task’s são transparentes aos usuários.

Um **JOB** é um processo que inicia, faz o que tem que fazer e termina. Um programador, um suporte técnico, ou até um usuário pode criar um Job para fazer exatamente aquilo que se quer, como por exemplo, atualizar dados, reorganizar dados, apagar dados, etc. Os Jobs se utilizam de programas para fazer aquilo para que foram criados. No tópico sobre JOB, este tema será debatido.

###### XCF – COUPLING FACILITY:

O **XCF** é um aplicativo que acompanha o MVS quando se deseja colocar dois ou mais sistemas em compartilhamento de recursos. Funciona em transparência para o usuário, mas ajuda muito quando se fala em recursos como fitas, discos, etc.

## Comandos MVS

Alguns comandos que podem ajudar no bom andamento de um sistema.

###### Comandos Gerais:

`d iplinfo` : este comando mostra os dados do sistema, como por exemplo, a última data de IPL, em qual volume está o Dataset, em qual Drive estão os parâmetros que forram carregados no sistema, etc. Exemplo:

```
SYSTEM IPLED AT 14.02.46 ON 31/02/2100
RELEASE z/OS 01.09.00 LICENSE = z/OS
USED LOADWW IN DATA.DATASET ON 9999
ARCHLVL = X MTLSHARE = Z
IEASYM LIST = 00
IEASYS LIST = (00) (YY)
IODF DEVICE 8888
IPL DEVICE 7777 VOLUME ONONON
```

** Os números acima são fictícios.*

.

`d a,XXXXXXX` : este comando mostra o estado de uma das entidades ativas no MVS, podendo ser um Job, uma Task ou usuário. Seguem alguns exemplos do comando:

`d a,xxxxxxxx`, onde `xxxxxxxx` é um nome de Job.

```
JOBS - M/S - TS USERS SYSAS - INITS - ACTIVE/MAX VTAM OAS
00010 00115 00006 - 000042 - 00085 - 00006/00450 00053

XXXXXXXX JS000 OWT J A=0109 PER=NO SMC=000
PGN=N/A DMN=N/A AFF=NONE
CT=000.119S ET=020.543S
WUID=JOB99999 USERID=ONONON
WKL=BATCH SCL=BATMED P=1
RGP=N/A SRVR=NO QSC=NO
ADDR SPACE ASTE=ZZZZZZZ
```

Neste comando é possível ver tudo o que diz respeito em relação a um Job que está em um sistema, tais como o tempo de CPU utilizado, o número de JES de um Job, a prioridade do Job no sistema, etc. E mais algumas informações extras mostradas na primeira linha, tais como quantidade de Job no sistema no momento, o número de usuários de TSO no sistema no momento, o máximo de usuários de TSO que podem acessar o sistema ao mesmo tempo, etc.

.

`d a,l` : este comando mostra uma lista de tudo o que está ativo no MVS, sendo Tasks e Jobs.

.

`d r,l` : este comando mostra a lista de Reply dos sistemas. Exemplo:

```
ID:R/K T SYSNAME JOB ID MESSAGE TEXT
000011 R XXXX CA7ICOM 11 CA-7.999 (CA7ICOM ) ENTER REQUEST
```

A resposta do comando acima mostra todos os Replies do sistema, neste caso o reply do CA-7, onde aparece o nome do Job, o número do Reply, etc.

.

`d grs,c` : este comando é usado para verificar contenções em um sistema. Quando dois ou mais Job’s ou usuários tentam acessar um mesmo recurso exclusivamente, estes entram em contenção, e alguém terá que esperar. Duas entidades podem acessar um recurso ao mesmo tempo, desde que nenhum deles queira exclusividade sobre o recurso. A contenção pode ainda envolver uma Task, o que gera uma situação mais séria. Se um Job ou usuário estiverem atrapalhando o funcionamento de uma Task (o HSM, por exemplo), este normalmente tem que ser parado imediatamente, pois pode causar um CRASH no sistema.

Exemplo de uma resposta normal de contenção:

```
NO ENQ RESOURCE CONTENTION EXISTS
NO LATCH CONTENTION EXISTS
```

Outro Exemplo:

```
S=SYSTEM SYSDSN aaaaa.bbbbbbb.ccccc.dddddd.eeeeeeee
SYSNAME JOBNAME ASID TCBADDR EXC/SHR STATUS
xxxxxx - wxyzwxyz 00C6 007FF448 SHARE OWN
xxxxxx - zzzzzzzz 010E 007FF448 EXCLUSIVE WAIT
xxxxxx - www 003A 007E67F8 SHARE WAIT
```

Neste exemplo de contenção, pode se ver o recurso, que é um Dataset, os Jobs que estão em contenção, o tipo de utilização (SHARE/EXCLUSIVE), o status dos Jobs, etc. O terceiro Job `zzzzzzzz`, requer o recurso exclusivamente, por isso, ele vai esperar o primeiro usar `wxyzwxyz` e o terceiro, `www`, terá que esperar até o segundo terminar. Quem estiver verificando a contenção terá que verificar o que está em contenção, pois se apresenta como Job, e nem sempre o é.

.

`f tso,usermax=0` : este é um comando de MODIFY que configura para 0, neste caso, o número máximo de usuários de TSO que podem entrar no sistema.

###### Comandos para Job

O comando de Display `d a,jobname` pode ser usado.

.

`c jobname` : comando usado para *cancelar* um Job.

.

`c jobname,a=asid` : comando usado para cancelar um Job pelo seu Address Space. Para ver o AS de um Job, é só usar o comando de Display.

.

`c jobname,dump` : outra opção para cancelar, esta faz um DUMP quando cancela.

.

`force jobname,arm` : este comando cancela o job de uma forma mais bruta, inclusive gera uma mensagem de END OF MEMORY, deve ser usado quando um suporte pede.

.

`force jobname,a=asid` : este comando cancela o job de uma forma mais bruta, inclusive gera uma mensagem de END OF MEMORY, deve ser usado quando um suporte pede.

.

`force jobname,a=asid` : faz o mesmo que o command acima, porém, força o job de seu address space.

.

`force jobname` : este comando forca o job mais brutalmente que o comando que usa arm.

.

`jobname,srvclass=batchhot` : este comando muda o parâmetro SRVCLASS de um Job, que é um parâmetro de execução, ou seja de performance. Neste caso, o Job foi colocado em HOT BATCH, que significa que terá mais atenção do sistema para ele.

As opções para se colocar na Classe SRV são:

- `BATCHDFT` : opção Default, que é a que vem com o Job.
- `BATCHPRD` : opção de classe de produção.
- `SLEEP` : opção que coloca o Job em posição sem processamento, funciona como um HOLD.
- `RESUME` : opção que retira o status de SLEEP da Classe de um Job.

###### Comandos de MVS Console

`K` : comando que *limpa* a console.

`K Q` : clear, limpa a console das mensagens comuns e deixa as Highlighted Messages.

`K S,DEL=R` : coloca a console em status ROLL, ou seja, as mensagens rolam na console, inclusive as Highlited Messages .

`K S,DEL=RD` : coloca a console em status ROLL DELETE, ou seja a console rola e deleta as mensagem comuns e segura as Highlited.

`K S,DEL=N` : coloca a console em NO ROLL, ou seja as mensagens ficam travadas na console, mas pode gerar contenção na console, vale somente para copiar uma mensagem e liberar em seguida.

`K E,1` : comando usado para apagar as Highlighted uma por uma.

`K E,D e K E,NONE` : estes comandos são usados para mudar a divisão da console, as vezes ela fica dividida no meio, dai usando estes comandos ela volta ao normal.

`V CN(XXXXMSTR),MSCOPE=XXXX` : onde `XXXX`, leia-se a LPAR desta console. Comando usado para que uma console pare de receber mensagem de outra LPar, as vezes as Lpares dentro de um Sysplex dividem as consoles, então se usar este comando colocando a mesma LPar, a console passa a receber somente suas mensagens.

###### Comandos de Usuário

`d ts,l` : este comando mostra a lista de usuários que estão no sistema no momento

`d ts,a` : este comando mostra os usuários ativos no sistema, detalhadamente.

`c u=userid` : comando que cancela o usuário.

`c u=userid,a=asid` : comando que cancela o uauario pelo ‘ADDRESS SPACE’

###### Comandos de SMS

`V SMS,PDSE,ANALYSIS` : comando usado para checar o estado do PDSE do SMS quando alguma mensagem de PDSE aparecer.

O resultado tem que ser algo como:

```
++NO EXCEPTIONS
```

.

`V SMS,PDSE,RESTART` : comando usado para reinicializar o PDSE. Usado somente com instrucao do MVS suporte.

###### Comandos de DEVICE

`d m=dev(xxxx)`, onde `xxxx` seria o número do DEVICE.

Comando que mostra a situação de um Device, se ele está ativo, se está em uso, se está funcionando normalmente, se a parte física e lógica estão ok.

.

`d m=chp(xx)`, onde `xx` seria o número do CHIPID.

Comando parecido com o acima, mas mostra as informações para um CHIPID, que é o ponto de conexão físico para DEVICES no Mainframe.

.

`d u, , , ,xxxx`, onde `xxxx` seria o número de DEVICES.

Este comando mostra a quantidade de DEVICES no sistema, se estão ONLINE, OFFLINE, ALLOC, etc.

O comando tem parâmetros para ajudar a especificar o Display dos DEVICES.

1. `DEVTYPE` : parâmetro que pode ser usado logo após a primeira vírgula e possibilita mostrar um DEVICE específico (DASD, TAPE, ALL, etc).
2. Ex.: `d u,TAPE,online` : comandos que mostrarão todos os DEVICES tipo TAPE disponíveis para uso (ONLINE) no sistema.

3. `ONLINE/OFFLINE` : parâmetro que permite mostrar todos os DEVICES que estao em um estado especifico.
4. Ex.: `d u,DASD,offline` : parâmetro usado, neste caso, para mostrar os DASDs OFFLINE no sistema.

5. `DEVNUM` : parâmetro que vai após a terceira vírgula para poder colocar o número do DEVICE especificado e partir destes números, mostrar todos os outros no sistema.
6. Ex.: `d u,,,FFFF,256` : neste caso, o parâmetro indica para serem mostrados 256 DEVICES a partir do `ffff`.

7. `NNNN` : este parâmetro, o último, pode ser usado para mostrar uma quantidade determinada de DEVICES, seja para um determinado tipo ou para todos definidos no sistema.
8. Ex.: `d u,tape,aaaa,100` : comando que mostra 100 unidades de DEVICES no sistema a partir da unidade `aaaa`.

## Mensagens de MVS

###### Mensagens de SARS:

```
SARSTC05 SUBSYSTEM ALLOCATION FAILED - ERROR CODE 0478, INFO CODE 0000
```

Esta mensagem vem de uma Task chamada **SARS**.

.

```
SARSTC05 JOB JOBNAME(JOB99999), DATA SET DATA.SET.DATA.SET.JESJCLIN
```

Esta mensagem geralmente vem junto com a acima, e mostra o nome do job que pode estar causando o problema.

###### Mensagem de TASK no MVS:

```
STC99999 #AUS9999E Message flood automation message rate equals or exceeds 2000.
AUS9999E Count at (27514). Contact MVS Support On-Call during working hours

AUS9999E Global variable for Message Flood Automation time is invalid. Value is (15).
AUS9999E Requested format is HH:MM:SS. Default used. Contact Mainframe Automation On-Call during working hours.
```

Estas mensagens podem vir de várias Tasks, por isso, deve-se olhar e investigar qual Task está enviando a mensagem, no próprio corpo da mensagem há o número da Task. Então, deve-se contatar o grupo correspondente. Na dúvida, chame o MVS.

###### Mensagem de Expiração de Licenca de Produto:

```
CAS9012A 00001 KEY WARNINGS/VIOLATIONS ON CPU 999XXX

CAS9013A PRODUCT YY ABOUT TO EXPIRE OR IS EXPIRED AND IS IN USE
```

Mensagem que indica que algum produto que está instalado no Mainframe perdeu o tempo de licença ou está para perder este tempo. Geralmente, esta mensagem não causa um problema grave, mas o **MVS** deve ser informado.

```
LDM1729S Unexpected CVT flag(s) at offset X'04F8'. Contents of this byte: X'40'.
LDM1035S LDMF is attempting to execute in a system environment that has not been tested.
```

*Manual Explanation: The CVT on this MVS system indicates an unsupported release of the operating system, or the presence of an unsupported feature.*

*It appears not to be related to an expired authentication code.*

Aparentemente, este é um software utilizado pelo time de Storage.

###### Mensagem do SMS:

```
ATR202D GAP FOUND IN ATR.SYSXXXX.RM.DATA. REPLY RETRY OR ACCEPT TO ACCEPT THE DATA LOSS

IGD706D SMS RECORD STATISTICS ERROR. REPLY 'U' TO RETRY, 'C' TO CANCEL, 'S' TO SUSPEND, 'T' TO TERMINATE OR 'F' TO FORCE
```

Mensagens de erro em DASD que são geradas em conjunto com Reply. Normalmente, o time de MVS deve ser contatado, pois há o **SMS** na mensagem e esta Task possui muita importância para o bom funcionamento do sistema.

###### Mensagem do MIM:

```
MIM0620I COMPATLEVEL 11.50 activation in progress
MIM0621I COMPATLEVEL 11.50 activation complete
```

Mensagem que pode indicar algum problema na ativação do aplicativo **MIM**. Por isso, o MVS deve ser consultado.

###### Mensagem de SMR:

```
SMR unable to allocate syslog dataset; contact MVS during normal business hours
```

Mensagem que indica que o **SMR**, um aplicativo ligado ao Log do sistema, está com problemas. Logo, o MVS deve ser contatado.

###### Mensagem de SUNLOC e SUNGLOB:

```
(IEF450I) SUNLOCXX ABENDED. CONTACT APPROPRIATE SUPPORT ASAP! REPLY Y

(SSMMON) SUNLOCXX IS NOT UP DUE TO ERRORS INVESTIGATE AND CONTACT SUPPORT FOR SUNLOCXX -REPLY Y
```

Mensagem de um aplicativo de Mainframe chamado **SUNLOC**. Portanto, neste caso, o MVS deve ser chamado para o “abend”.

```
AUS9999E IF BATCH MAINTENANCE IS ACTIVE-IGNORE SUNCOM50 MSGAUS9999E SUNGLOBL HAS ISSUED *SUNCOM50-SIGNAL LOST* MESSAGE.
```

Mensagem que indica que o aplicativo pode estar com problema. Por isso, o time de MVS deve ser contatado.

###### Mensagem de CA SPOOL:

```
!ESF200 ESF RESOURCE CLEANUP FAILED FOR ST XXXXCICS.CICS .XXXXZZZZ
```

Aparentemente, houve uma falha no processo de “cleanup” de algum CICS. Logo, o MVS deve ser contatado, visto que o CA Spool seria suportado pelo MVS.

```
ESF126 NODE SP999999 - NOT REDEFINED, BECAUSE IT WAS ACTIVE
```

Mensagem que indica problema com uma impressora de CA-SPOOL. Deve-se então conversar com o time de MVS suporte.

###### Mensagem de CA-DATACOM:

```
CACM335E CA-DATACOM AREA ACH IS 80% FULL
```

Alguma área do **CA-DATACOM**, que geralmente é de responsabilidade do time de MVS, está ficando cheio. Alguém do time de suporte MVS deve ser avisado, a não ser que se tenha algum procedimento específico para isso.

###### Mensagens de SYSPLEX:

Algumas mensagens de **SYSPLEX** podem aparecer durante um problema. As mensagens aparecem para todas as LPares.

```
No EAXAlert Communication from lpar for 20 mins or more
COUPLING FACILITY 002064.IBM.83.000000010FB4
PARTITION: 09 CPCID: 00

IXL158I PATH 99 IS NOW NOT-OPERATIONAL TO CUID: FFF6
COUPLING FACILITY 002064.IBM.83.000000010FB4
PARTITION: 09 CPCID: 00

IXL158I PATH 85 IS NOW NOT-OPERATIONAL TO CUID: FFEF
COUPLING FACILITY 002064.IBM.83.000000010FB4
PARTITION: 09 CPCID: 00

IXL158I PATH 89 IS NOW NOT-OPERATIONAL TO CUID: FFF6
COUPLING FACILITY 002064.IBM.83.000000010FB4

IOS050I CHANNEL DETECTED ERROR ON 0A80,37,0B,**02

// IOS050I CHANNEL DETECTED ERROR ON 0A80,37,01,**02//

xx* IXC402D lpar LAST OPERATIVE AT 10:34:25. REPLY
DOWN AFTER SYSTEM RESET, OR INTERVAL=SSSSS TO
SET A REPROMPT TIME.

xx* IXC402D 3033 LAST OPERATIVE AT 10:34:26. REPLY
DOWN AFTER SYSTEM RESET, OR INTERVAL=SSSSS TO
SET A REPROMPT TIME.

IXL040E CONNECTOR NAME: SIGPATH_04000B4A,
JOBNAME: XCFAS, ASID: 0006
HAS NOT RESPONDED TO THE USER SYNC POINT EVENT.

IXL040E CONNECTOR NAME: SIGPATH_06000B44,
JOBNAME: XCFAS, ASID: 0006
HAS NOT RESPONDED TO THE USER SYNC POINT EVENT.
USER SYNC POINT PROCESSING

IXL040E CONNECTOR NAME: SIGPATH_01000B43,
JOBNAME: XCFAS, ASID: 0006
HAS NOT RESPONDED TO THE USER SYNC POINT EVENT.
FOR STRUCTURE IXC_LIST04 CANNOT CONTINUE.//

MONITORING FOR RESPONSE STARTED: 99/99/9999
USER SYNC POINT PROCESSING
FOR STRUCTURE IXC_LIST02 CANNOT CONTINUE.

DIAG: 0000 0000 00000000

MONITORING FOR RESPONSE STARTED: 99/99/9999
DIAG: 0000 0000 00000000//

IXL040E CONNECTOR NAME: SIGPATH_04000B4A,
JOBNAME: XCFAS, ASID: 0006
HAS NOT RESPONDED TO THE USER SYNC POINT EVENT.

IXL040E CONNECTOR NAME: SIGPATH_06000B44,
JOBNAME: XCFAS, ASID: 0006
HAS NOT RESPONDED TO THE USER SYNC POINT EVENT.

//MONITORING FOR RESPONSE STARTED: 99/99/9999

IXL040E CONNECTOR NAME: SIGPATH_01000B43,
JOBNAME: XCFAS, ASID: 0006
HAS NOT RESPONDED TO THE USER SYNC POINT EVENT.

FOR STRUCTURE IXC_LIST04 CANNOT CONTINUE.
MONITORING FOR RESPONSE STARTED: 99/99/9999

USER SYNC POINT PROCESSING
FOR STRUCTURE IXC_LIST02 CANNOT CONTINUE.
MONITORING FOR RESPONSE STARTED: 99/99/9999

USER SYNC POINT PROCESSING
FOR STRUCTURE IXC_LIST02 CANNOT CONTINUE.
MONITORING FOR RESPONSE STARTED: 99/99/9999

DIAG: 0000 0000 00000000
DIAG: 0000 0000 00000000
DIAG: 0000 0000 00000000
```

Portanto, não hesite em chamar o MVS.

.

```
IXC404I SYSTEM(S) ACTIVE OR IPLING: lpar
IXC405D REPLY I TO INITIALIZE THE SYSPLEX, J TO JOIN SYSPLEX xxxxPLX, OR R
TO REINITIALIZE XCF
```

Exemplo de Reply que pode ser utilizado durante o IPL. Na dúvida, chame o MVS antes de responder.

.

```
NO MVSHeartbeat WARNING EAXAlert.
```

Em geral, indica um problema sério no **SYSPLEX**. Deve-se verificar o sistema e chamar o MVS em caso de dúvidas.

###### Mensagem de ETR:

```
IEA272I ETR SERVICE IS REQUESTED. REASON CODE = 47
```

Esta mensagem é oriunda do aplicativo **ETR**, que sincroniza os horários do sistema.

A mensagem acima é meramente informativa, mas caso o código da mensagem terminar com as letras **W**, **S** ou **E**, então o time de MVS deve ser contatado.

## Tasks de MVS

###### Sobre as Tasks:

As Tasks são aplicativos instalados em um sistema mainframe, assim como existem vários aplicativos e programas instalados no seu PC. E, assim como em seu PC, muitas das Tasks podem ser escolhidas versões diferentes e de fabricantes distintos.

As Tasks se dividem em algumas categorias e que serão explicadas aqui.

.

###### Tasks Internas do Sistema:

São Tasks que o sistema necessita para funcionar, assim como os programas que seu PC precisa para funcionar bem. São alguns executáveis instalados e que são transparentes para o cliente.

Alguns exemplos seriam **RMF**, **LLA**, **DLF**, **CAS9**, **TSO**, etc.

.

###### Tasks Necessárias ao Sistema:

São Tasks necessárias ao bom funcionamento do sistema, mas que geralmente o cliente as escolhe para instalação, levando em conta suas próprias necessidades e suas disposição financeira. São Tasks de banco de dados, acesso a banco de dados, rede, seguranca, *Scheduling,* automação, gerenciamento de recurso, gerenciamento de hardware, controle de acesso de Jobs, etc.

Estas são maioria: **JES2**, **CICS, DB2, IMS, VTAM, CA-7, Control-, ACF2, RACF, VPS, MIM, HSM,** etc.

###### Tasks Específicas:

Estas são as Tasks específicas para algum cliente, ou seja, algum aplicativo que somente este cliente usa para uma necessidade específica deste cliente.

Estas Tasks não são muitas e, como são específicas, fica difícil apresentar algum exemplo.

###### Subtasks:

São Tasks secundárias atreladas a alguma Task principal. São extremamente importantes para o funcionamento da Task principal, pois a Task principal precisa delegar funções para que não fique sobrecarregada.

Quase todos os aplicativos ou Tasks tem suas Subtasks no sistema, o **CICS**, o **IMS**, o **DB2**, o **VTAM**, etc.

###### CAS9:

**CATALOG ADDRESS SPACE**: Task do MVS, pelo nome, esta Task cataloga o Adress Space (espaço lógico) no sistema para cada Task na inicialização do mesmo (IPL)

###### ENF:

**CAS9 Event Notification Facility**: É inicializado pelo CAS9.

###### SMF:

**System Management Facility**

Aplicativo do MVS que coleta dados estatísticos sobre as Tasks executando no MVS. O SMF utiliza-se de Datasets para arquivar estas estatísticas.

Se este aplicativo que realiza DUMP’s de informações não estiver de acordo, o sistema não executa várias funções, o que pode ocasionar o travamento do sistema.

`d smf -` é o comando que pode ser usado para Display deste aplicativo.

###### LLA:

**Listlink Lookaside ou Library Lookaside**

É onde residem módulos de bibliotecas que são usadas para conectar Datasets entre si. O LLA cria uma tabela onde todas as bibliotecas de Datasets estão localizadas. Assim, quando um Job precisar buscar seu JCL em uma biblioteca (Library), por exemplo, esta será encontrada mais facilmente do que se um usuário tiver que olhar biblioteca por biblioteca.

.

###### Alguns Comandos de LLA:

Quando alguém cria uma nova biblioteca, a tabela LLA precisa ser atualizada. Isto é feito através de um comando:

```
f lla refresh
```

O comando usado para inicializar (Start) na LLA:

```
s lla
```

ou

```
s lla,sub=mstr
```

###### VLF:

**Virtual Lookaside Facility**

Mantém os Dataset’s mais usados em espaços virtuais que o próprio VLF disponibiliza, tirando da memória virtual do sistema.

###### DLF:

**Data Look Aside Facility** – Provides Hiperbatch decision support.

.

Comandos usados para parar o DLF:

`F DLF,MODE=Q` : este seria o comando próprio do DLF para parar suas funções.

`P DLF` : este seria o comando do MVS para parar o DLF e tirá-lo do sistema.

###### EPWFFST:

**IBM First Failure Support Task**

###### RMF:

**Resource Management Facility**

###### IOFPROC:

**Interactive Output Facility** : uma Task interna do sistema.

###### APSW*:

Task de gerenciamento de impressoras.

###### Computer Associates Dispatch (CA-DISPATCH):

**Description:** Report Writer, Print Utility Report distribution and management task that collects SYSOUT CLASS=R and groups the output in JES under the name of CADSDISP and routes bundles of output to the printer to minimize print time and operation intervention.

Esta seria uma Task de geração de relatórios de sistema e que gerencia distribuição de impressão, otimizando o processo.

###### CAIVCSS:

**VCSS for CA-Dispatch:** SubTask do CA-Dispatch.

###### CONTROLD:

Report Writer. Supports online viewing and report distribution runs like Dispatch.

Task de Dispatch, mas da linha do Control (BMC)

###### CTDP:

Subtask do CONTROLD

###### VSV:

**VPS server component:** Task de gerenciamento de Impressoras.

###### VROS:

Task do aplicativo Roscoe.

###### SYSLOG*:

Task de gerenciamento do **LOG** do sistema.

###### SYSVGSS:

**CA-GSS for MVS: Secondary ISERVE Address Space**

###### SYSVUSER:

User Interface Address Space: Subtask do CA-Sysview

###### HCS:

**HOST COMMAND FACILITY**

TERMINAL EMULATION AND AS400 COMMUNICATION

###### IOASINIT:

CONTROLM EVENT MGR

SubTask do CONTROL-M

###### TSS:

**TOP SECRET SECURITY**

Task de segurança.

###### CCITCP:

Sub task do CA-7 Workstation

###### VMCF:

**VIRTUAL MACHINE COMMUNICATION FACILITY**

STARTS WHEN ITS SUBSYSTEM INITIALIZES, ALSO PROVIDES 3172 INTERFACE FOR NETITCP

###### VPS:

**VIRTUAL PRINTER SYSTEM:** Task de gerenciamento de impressoras.

.

\* * * * *