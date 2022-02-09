**IBM Integration Bus, Versão 10.0.0.18** Sistemas operacionais: AIX, HP-Itanium, Linux, Solaris, Windows, z/OS



------

# Regras para Utilizar Comandos

Observe as seguintes regras ao utilizar os comandos do IBM® Integration Bus em sistemas distribuídos.

Se você estiver utilizando comandos no z/OS, consulte a seção sobre comandos do z/OS em [Comandos](https://www.ibm.com/docs/pt-br/SSMKHH_10.0.0/com.ibm.etools.mft.doc/an07060_.htm).

- Cada comando deve ser emitido no sistema no qual o recurso ao qual ele se relaciona é definido (ou deve ser criado).

- Cada comando inicia com uma palavra-chave principal (o nome do comando executável) seguido por um ou mais espaços em branco.

- Após a palavra-chave principal, poderão ocorrer sinalizadores (parâmetros) em qualquer ordem.

- Os sinalizadores são mostrados neste manual no formato **-t**, por exemplo. Em todos os casos, o caractere **/** pode ser substituído pelo caractere **-**.

- Se um sinalizador tiver um valor correspondente, seu valor deverá seguir o sinalizador ao qual está relacionado. Um sinalizador pode ser seguido por seu valor diretamente ou ser separado por qualquer número de espaços em branco.

- Sinalizadores podem ser concatenados caso não tenham valores correspondentes, embora o último sinalizador em um grupo concatenado

   

  pode

   

  ter um valor associado a ele. Por exemplo, o comando:

  ```plaintext
  mqsireadlog IBNODE -u -e default -o trace.xml -f
  ```

  

  pode ser inserido como:

  ```plaintext
  mqsireadlog IBNODE -ufedefault -o trace.xml
  ```

  

  em que o nome do servidor de integração,

   

  padrão

  , está relacionado com a tag

   

  -e

  . Para esclarecer, todos os exemplos fornecidos nesta documentação são mostrados com sinalizadores separados e com um espaço antes de qualquer valor associado.

- Sinalizadores repetidos não são permitidos.

- As sequências que contêm espaços em branco ou caracteres especiais devem ser colocadas entre aspas duplas. Exemplo:

  ```plaintext
  mqsireadlog "My Integration node" -u -e default -o trace.xml -f
  ```

  

  Além disso, é possível especificar uma sequência nula ou vazia com aspas duplas sem nada entre elas: "".

- 

  Se você estiver executando um comando ao enviar um dos utilitários JCL (consulte

   

  Conteúdo do PDSE do nó de integração

  ), e um argumento para um dos parâmetros contiver um caractere em branco, deve-se substituir o espaço em branco pelo mnemônico

   

  &#0032;

   

  antes de enviar o JCL. Por exemplo, se estiver utilizando

   

  BIPDPLY

   

  para executar o comando

   

  mqsideploy

   

  para excluir um arquivo

   

  .jar

   

  implementado que é chamado

   

  my jar.jar

   

  do servidor de integração

   

  padrão

  , modifique a JCL para conter a amostra a seguir:

  ```plaintext
  mqsideploy IIB9BROKER -e default -d my&#0032;jar.jar
  ```

  

- A diferenciação de maiúsculas e minúsculas em palavras-chave principais e parâmetros depende do sistema operacional subjacente. Em plataformas Windows, as palavras-chave não fazem distinção entre maiúsculas e minúsculas; **mqsistart**, mqsiSTART e MQSISTART são aceitáveis. Em plataformas Linux e UNIX, é necessário usar minúsculas; somente **mqsistart** é aceitável.

**Referências relacionadas**:

[Caracteres permitidos em nomes de objetos](https://www.ibm.com/docs/pt-br/SSMKHH_10.0.0/com.ibm.etools.mft.doc/an07070_.htm)

[Comandos](https://www.ibm.com/docs/pt-br/SSMKHH_10.0.0/com.ibm.etools.mft.doc/an07060_.htm)

[Respostas a Comandos](https://www.ibm.com/docs/pt-br/SSMKHH_10.0.0/com.ibm.etools.mft.doc/an19510_.htm)