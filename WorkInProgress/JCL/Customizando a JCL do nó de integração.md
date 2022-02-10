[BM Integration Bus](https://www.ibm.com/docs/pt-br/integration-bus)[10.0](https://www.ibm.com/docs/pt-br/integration-bus/10.0)

[Feedback](mailto:ibmdocs@us.ibm.com?Subject=Feedback to IBM Documentation&body=URL: https%3A%2F%2Fwww.ibm.com%2Fdocs%2Fpt-br%2Fintegration-bus%2F10.0%3Ftopic%3Dssmkhh-10-0-0-com-ibm-etools-mft-doc-ae22460--htm)[Lista de produtos](https://www.ibm.com/docs/pt-br/products)

**IBM Integration Bus, Versão 10.0.0.18** Sistemas operacionais: AIX, HP-Itanium, Linux, Solaris, Windows, z/OS

------

# Customizando a JCL do nó de integração

Customize a JCL do nó de integração como parte da criação de um nó de integração no z/OS.

## Antes de Iniciar

Conclua as etapas no [Customizando o conjunto de dados do componente do nó de integração](https://www.ibm.com/docs/pt-br/SSMKHH_10.0.0/com.ibm.etools.mft.doc/ae22450_.htm).

## Sobre Esta Tarefa

Todo o JCL possui um cabeçalho padrão, que inclui os seguintes itens:

- Uma descrição breve de sua função.
- Uma descrição na qual podem ser localizadas informações adicionais relacionadas à função da JCL.
- Se apropriado, um número de tópico.
- A seção que lista as próprias variáveis JCL.

Cada arquivo JCL define seu próprio STEPLIB.

É possível customizar os arquivos usando uma macro de edição do ISPF que você deve customizar, ou é possível alterar cada um dos membros do PDSE manualmente.

BIPEDIT é um programa REXX que pode ser utilizado para ajudá-lo a customizar sua JCL. Depois de customizar o BIPEDIT, você poderá executar este programa REXX novamente nos outros arquivos JCL para alterar suas variáveis JCL.

Ao atualizar o BIPBPROF (o perfil do nó de integração), as mudanças não estarão acessíveis até que você execute BIPGEN para copiar o perfil para o sistema de arquivos e crie o ENVFILE. É necessário executar BIPGEN sempre que você atualizar BIPBPROF para que as mudanças entrem em vigor. Se você possuir perfis específicos de servidor de integração, e alterar BPROF ou BIPEPROF (renomeado para o rótulo do servidor de integração), será necessário executar também BIPGEN.

## Procedimento

1. Customize o arquivo BIPEDIT renomeado.

       Use as informações que você coletou na:

   - [Informações da instalação para um nó de integração](https://www.ibm.com/docs/pt-br/SSMKHH_10.0.0/com.ibm.etools.mft.doc/ae22600_.htm)
   - [Informações do componente para um nó de integração](https://www.ibm.com/docs/pt-br/SSMKHH_10.0.0/com.ibm.etools.mft.doc/ae22620_.htm)

2. Ative o arquivo BIPEDIT renomeado antes de customizar outros arquivos JCL, executando o comando a seguir TSO:

   ```plaintext
       ALTLIB ACTIVATE APPLICATION(EXEC) DA('COMPONENTDATASET')
   ```

   em que

   'COMPONENTDATASET'    

   é idêntico a
    
   ++COMPONENTDATASET++
   .

   Este comando está ativo para a sessão do ISPF local com a qual ele foi emitido. Se você tiver sessões de tela divididas, as outras sessões não poderão usar este comando. Se você usar a opção 6 do ISPF para emitir o comando, use a opção 3.4 do ISPF para editar o conjunto de dados, que permite usar o comando editar.

3. Edite cada arquivo JCL.
    
   Execute o arquivo renomeado
    
   BIPEDIT
    
   digitando seu nome na linha de comandos (por exemplo,
    
   MQ01EDBK

   ). Ao invés de editar um membro, talvez deseje
    

   Visualizá-lo até que resolva todos os problemas no programa REXX. Como alternativa, é possível
    
    

   Editar       em vez de salvá-la.

   É necessário configurar um valor para todas as variáveis que estão listadas na JCL; se isso não for feito, a JCL não funcionará corretamente.

## O que Fazer Depois

Alguns arquivos JCL incluem ++OPTIONS++ para um comando; deve-se substituí-los por parâmetros opcionais adicionais específicos do comando no z/OS ou removê-los. Tipicamente, deve-se substituir ou remover essas opções, além de executar BIPEDIT. Se não forem necessárias opções adicionais, remova o ++OPTIONS++ usando o comando a seguir:

```plaintext
     "c ++OPTIONS++ '' all" 
```

em que ' ' representa duas aspas simples.

Salve a macro de edição e execute esta macro em todos os membros, exceto na própria macro de edição.

Deve-se estar ciente de que outro processo pode estar usando o ENVFILE atual, portanto, deve-se considerar se atualizar o ENVFILE atual no sistema de arquivos poderia ter outros efeitos.

**Conceitos relacionados**:

[O ambiente do IBM Integration Bus](https://www.ibm.com/docs/pt-br/SSMKHH_10.0.0/com.ibm.etools.mft.doc/be43400_.htm)

**Tarefas relacionadas**:

[Criando um nó de integração no z/OS](https://www.ibm.com/docs/pt-br/SSMKHH_10.0.0/com.ibm.etools.mft.doc/ae22400_.htm)

**Referências relacionadas**:

[Comando mqsicreatebr](https://www.ibm.com/docs/pt-br/SSMKHH_10.0.0/com.ibm.etools.mft.doc/an07080_.htm)