# mIRC

Origem: Wikipédia, a enciclopédia livre.

| [![img](https://upload.wikimedia.org/wikipedia/commons/thumb/9/97/Question_book.svg/40px-Question_book.svg.png)](https://pt.wikipedia.org/wiki/Ficheiro:Question_book.svg) | Este artigo ou secção **não cita [fontes confiáveis](https://pt.wikipedia.org/wiki/Wikipédia:Fontes_confiáveis) e [independentes](https://pt.wikipedia.org/wiki/Wikipédia:Fontes_independentes)**. Ajude a [inserir referências](https://pt.wikipedia.org/wiki/Wikipédia:REF). O conteúdo não [verificável](https://pt.wikipedia.org/wiki/Wikipédia:Verificabilidade) pode ser removido.—*Encontre fontes:* [Google](https://www.google.com/search?as_eq=wikipedia&as_epq=MIRC) ([notícias](https://www.google.com/search?hl=pt&tbm=nws&q=MIRC&oq=MIRC), [livros](http://books.google.com/books?&as_brr=0&as_epq=MIRC) e [acadêmico](https://scholar.google.com.br/scholar?hl=pt&q=MIRC)) *(Maio de 2011)* |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
|                                                              |                                                              |

|                             mIRC                             |                                                              |
| :----------------------------------------------------------: | ------------------------------------------------------------ |
|  [Desenvolvedor](https://pt.wikipedia.org/wiki/Programador)  | [Khaled Mardam-Bey](https://pt.wikipedia.org/wiki/Khaled_Mardam-Bey) |
|                          Lançamento                          | [28 de Fevereiro](https://pt.wikipedia.org/wiki/28_de_Fevereiro) de [1995](https://pt.wikipedia.org/wiki/1995) |
|    [Versão](https://pt.wikipedia.org/wiki/Versão) estável    | 7.55 (8 de Fevereiro de 2019)                                |
| [Sistema operacional](https://pt.wikipedia.org/wiki/Sistema_operativo) | [Microsoft Windows](https://pt.wikipedia.org/wiki/Microsoft_Windows) |
|                          Gênero(s)                           | cliente de IRC                                               |
| [Licença](https://pt.wikipedia.org/wiki/Licença_de_software) | [software proprietário](https://pt.wikipedia.org/wiki/Software_proprietário) |
|     [Página oficial](https://pt.wikipedia.org/wiki/Site)     | https://www.mirc.com/                                        |

**mIRC** é um cliente de IRC, [shareware](https://pt.wikipedia.org/wiki/Shareware), para o [sistema operacional](https://pt.wikipedia.org/wiki/Sistema_operacional) [Microsoft Windows](https://pt.wikipedia.org/wiki/Microsoft_Windows), criado em [1995](https://pt.wikipedia.org/wiki/1995) e desenvolvido por [Khaled Mardam-Bey](https://pt.wikipedia.org/wiki/Khaled_Mardam-Bey) com a finalidade principal de ser um programa [chat](https://pt.wikipedia.org/wiki/Chat) utilizando o protocolo [IRC](https://pt.wikipedia.org/wiki/IRC), onde é possível conversar com milhões de pessoas de diferentes partes do mundo. Ele era utilizado somente para isto, mas evoluiu para uma ferramenta totalmente configurável, que pode ser usada para muitas finalidades devido à sua linguagem de programação incorporada ([mIRC Scripting](https://pt.wikipedia.org/wiki/MIRC_Script)). Outros usos incluem:

- Gerente para canais de IRC
- Servidor de jogos multiplayer
- Leitor de MP3
- Browser
- Servidor de [DCC](https://pt.wikipedia.org/wiki/DCC), [HTTP](https://pt.wikipedia.org/wiki/HTTP) e de [IRC](https://pt.wikipedia.org/wiki/IRC)
- Plataforma de jogos (designados de mIRC *games*, jogos de mIRC)

Apesar de seu caráter limitado os recursos são muito úteis e funcionais. O programa é muito popular, tendo atingido a marca de 150 milhões de downloads [[1\]](http://www.mirc.com/news.html). Também ficou entre o top 10 das aplicações de [internet](https://pt.wikipedia.org/wiki/Internet) mais populares em [2003](https://pt.wikipedia.org/wiki/2003) pelo [Neilsen Net Ranking](http://www.internetnews.com/stats/article.php/3096631). A sua popularidade pode explicar o fato de muitos utilizadores do **mIRC** pensarem que este é também o nome do protocolo que o programa utiliza (IRC), e se referirem aos servidores e canais de IRC como "servidor de mIRC" ou "canal de mIRC".

## Índice



- [1Funcionalidades principais](https://pt.wikipedia.org/wiki/MIRC#Funcionalidades_principais)
- [2mIRC Scripts](https://pt.wikipedia.org/wiki/MIRC#mIRC_Scripts)
- [3Ver também](https://pt.wikipedia.org/wiki/MIRC#Ver_também)
- [4Ligações externas](https://pt.wikipedia.org/wiki/MIRC#Ligações_externas)

## Funcionalidades principais

- Ligação a múltiplos servidores simultaneamente
- [Língua de programação incorporada](https://pt.wikipedia.org/wiki/MIRC_Script);
- Bases de suporte para [CTCP](https://pt.wikipedia.org/w/index.php?title=CTCP&action=edit&redlink=1);
- Suporte para som via CTCP (pode ler [MP3](https://pt.wikipedia.org/wiki/MP3), [WAV](https://pt.wikipedia.org/wiki/WAV), e [MIDI](https://pt.wikipedia.org/wiki/MIDI));
- Suporte para chat e envio de arquivos por meio do protocolo [DCC](https://pt.wikipedia.org/wiki/Direct_Client-to-Client);
- Tentativas para parar downloads inadvertidos de [Trojan horses](https://pt.wikipedia.org/wiki/Trojan_horse);
- Servidor de arquivos (através de DCC chat) que permite um utilizador navegar em uma pasta específica e efetuar o [download](https://pt.wikipedia.org/wiki/Download) de arquivos;
- Suporte para decoração de texto estilo [ANSI](https://pt.wikipedia.org/w/index.php?title=ANSI_escape_code&action=edit&redlink=1) e estilo mIRC;
- Reconhecimento e síntese de voz via produtos;
- Capacidade de administração das salas de chat.

## mIRC Scripts

É comum os usuários do mIRC configurarem e modificarem o programa através do [mIRC Scripting](https://pt.wikipedia.org/wiki/MIRC_Script). Foram criados bastantes canais de IRC, sites e fóruns que ajudam as pessoas a aprender o mIRC Scripting. Existem milhares de scripts que podem se encontrados em sites relacionados com o mIRC, deve-se ter atenção para o fato de alguns scripts possuírem código malicioso.

Exemplos de Código em mIRC Scripting:

- Exemplo 1

  Somando dois números

```
alias Soma {
  var %n1 = $1
  var %n2 = $2
  return $calc(%n1 + %n2)
}
```

Observações:

- Em mIRC Scripting, [funções](https://pt.wikipedia.org/wiki/Funções) de programação são chamadas de ***Aliases***
- A *Aliase* acima recebe dois dados de entrada: **$1** e **$2**, armazenando os mesmos em duas variáveis locais **%n1** e **%n2**. Por fim, retorna a soma de ambas com o auxílio do identificador **$calc**.

- Exemplo 2

  Contando um número de 1 até 10

```
alias Contar {
  var %n1 = 1
  while (%n1 <= 10) { echo -a %n1 | inc %n1 }
}
```

Observações:

- A estrutura de programação é feita através de **blocos de chaves** como na [Linguagem C](https://pt.wikipedia.org/wiki/Linguagem_C)
- O comando **echo** é uma função interna do próprio cliente mIRC que exibe na janela atual os valores de **%n1** em cada loop.
- mIRC Scripting apenas aceita a estrutura de repetição **while**

**Exemplo 3: Exibindo uma mensagem no canal \*#Ajuda\* toda vez quem alguém entrar no mesmo**

```
on !*:JOIN:#Ajuda:{ msg $chan Olá $nick bem vindo ao canal #Ajuda }
```

Observações:

- mIRC Scripting também permite a manipulação de eventos. O Exemplo acima dispara sempre que qualquer pessoa (que não seja você) entre no canal **#Ajuda**. O evento de ao entrar em canal é o **ON !\*:JOIN**.
- A função **msg** é interna do cliente e permite enviar mensagens de texto para um canal ou uma pessoa diretamente. No exemplo acima a mesma envia para **$chan**, sendo esta, um identificador que conterá o canal de onde o evento disparou. A mesma coisa acontece com o identificador **$nick** que mostra o [nick](https://pt.wikipedia.org/wiki/Nick) ou [apelido](https://pt.wikipedia.org/wiki/Apelido) do indivíduo que entrou no canal.

Poderíamos ter utilizado desta forma:

```
on !*:JOIN:#Ajuda:{ msg $chan Olá $nick bem vindo ao canal $chan }
```

O Exemplo exibirá o seguinte texto no canal #Ajuda: **Olá fulano bem vindo ao canal #Ajuda**, onde *fulano* é qualquer pessoa.

As possibilidades são inúmeras para mIRC Scripting. É possível automatizar todo um cliente mIRC, sendo que, já existem clientes assim denominados **Bots**. Os Bots geralmente são programados em mIRC Scripting ou em [linguagem TCL](https://pt.wikipedia.org/wiki/Linguagem_TCL) com a finalidade de proteger um canal contra ataques de *[flood](https://pt.wikipedia.org/wiki/Flood)*, *[spam](https://pt.wikipedia.org/wiki/Spam)*, indivíduos com más intenções etc.

mIRC Scripting também permite realizar recursos extraordinários como, efetuar conexões TCP/UDP através de Sockets e até mesmo a manipulação de arquivos [DLL](https://pt.wikipedia.org/wiki/Dynamic_Link_Library)

## Ver também

- [Internet Relay Chat](https://pt.wikipedia.org/wiki/Internet_Relay_Chat)
- [Khaled Mardam-Bey](https://pt.wikipedia.org/wiki/Khaled_Mardam-Bey)
- [mIRC Script](https://pt.wikipedia.org/wiki/MIRC_Script)

## Ligações externas

- [«mIRC, Página oficial»](http://www.mirc.com/) (em inglês)
- [«mIRC.net - site com addons, scripts e outros conteúdos relacionados com o mIRC»](http://www.mirc.net/) (em inglês)
- [«mIRCscripts.org - site com todos os tipos de downloads relacionados com o mIRC»](http://www.mircscripts.org/) (em inglês)
- [«CanalScript.com.br - site com vários addons, dlls, rotinas e etc sobre mIRC-Scripting»](http://www.canalscript.com.br/)
- [«Ircmaster.com.br - site com vários addons, dlls, rotinas e etc sobre mIRC-Scripting»](http://www.ircmaster.com.br/)
- [«Tutorial IRC e mIRC para iniciantes em Português»](http://voltamirc.hub4ever.org/)