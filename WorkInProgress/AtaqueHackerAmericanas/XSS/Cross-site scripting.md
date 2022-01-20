# *Cross-site scripting*

Origem: Wikipédia, a enciclopédia livre.

***Cross-site scripting*** (**XSS**) é um tipo de vulnerabilidade do sistema de segurança de um computador, encontrado normalmente em [aplicações *web*](https://pt.wikipedia.org/wiki/Aplicações_web) que ativam ataques maliciosos ao injetarem *[client-side script](https://pt.wikipedia.org/wiki/Client-side_script)* dentro das [páginas *web*](https://pt.wikipedia.org/wiki/Página_web) vistas por outros usuários. Um *[script](https://pt.wikipedia.org/wiki/Linguagem_de_script)* de exploração de vulnerabilidade *cross-site* pode ser usado pelos atacantes para escapar aos controles de acesso que usam a política de mesma origem.

## Índice



- [1Ataque](https://pt.wikipedia.org/wiki/Cross-site_scripting#Ataque)
- 2Tipos
  - [2.1Não persistente](https://pt.wikipedia.org/wiki/Cross-site_scripting#Não_persistente)
  - [2.2Persistente](https://pt.wikipedia.org/wiki/Cross-site_scripting#Persistente)
  - [2.3Vulnerabilidades do lado do servidor em relação à base de DOM](https://pt.wikipedia.org/wiki/Cross-site_scripting#Vulnerabilidades_do_lado_do_servidor_em_relação_à_base_de_DOM)
- 3Proteção
  - [3.1Validação da entrada](https://pt.wikipedia.org/wiki/Cross-site_scripting#Validação_da_entrada)
  - [3.2Validação da Saída](https://pt.wikipedia.org/wiki/Cross-site_scripting#Validação_da_Saída)
- [4*Background*](https://pt.wikipedia.org/wiki/Cross-site_scripting#Background)
- [5Ligações externas](https://pt.wikipedia.org/wiki/Cross-site_scripting#Ligações_externas)

## Ataque

Através de um XSS, o *hacker* injeta códigos [JavaScript](https://pt.wikipedia.org/wiki/JavaScript) em um campo texto de uma página já existente e este JavaScript é apresentado para outros usuários, porque persiste na página.

Exemplo de ataque: Imaginem que o *hacker* insira, em um fórum de um *website* alvo de ataque, um texto que contenha um trecho de JavaScript. Este JavaScript poderia, por exemplo, simular a página de *[login](https://pt.wikipedia.org/wiki/Login)* do *site*, capturar os valores digitados e enviá-los a um *site* que os armazene.

Quando o texto do fórum for apresentado a outros usuários, um *site* atacado pelo XSS exibirá o trecho de JavaScript digitado anteriormente nos *[browsers](https://pt.wikipedia.org/wiki/Browser)* de todos os outros usuários,

Por fim, o atacante recebe a resposta em seu *browser* = ACK

**Nota:** Se você estiver usando *plugins*/extensões em seu navegador como: NoScript ou o Google chrome com o "XSS Auditor" habilitado, os ataques de *Cross Site Scripting* em *sites* que estejam vulneráveis não irão funcionar.



## Tipos

Não existe uma classificação única, padronizada de falhas de *cross-site scripting*, mas a maioria dos especialistas distinguem pelo menos dois tipos principais de XSS: não persistentes e persistentes. Algumas fontes dividem ainda mais estes dois grupos em tradicional (causada por falhas de código do lado do servidor) e baseadas em DOM (no código do lado do cliente).

### Não persistente

A vulnerabilidade *cross-site scripting* não persistente (ou refletida) é, de longe, o tipo mais comum. Estas falhas aparecem quando os dados fornecidos por um cliente *web*, mais comumente em parâmetros de consulta HTTP ou envios de formulários HTML, é imediatamente utilizado pelos *scripts* do lado do servidor para analisar e exibir uma página de resultados de e para o usuário, sem a limpeza adequada do pedido. Como os documentos HTML têm uma estrutura plana e serial que mistura instruções de controle, formatação e conteúdo real, todos os dados fornecidos pelo usuário, não validados incluídos na página resultante sem codificação HTML adequada, pode levar a injeção de marcação.

Um exemplo clássico de um potencial vetor é um *site* com mecanismo de busca: se alguém procura por uma frase, a frase de busca normalmente será reexibida na íntegra na página de resultado para indicar que foi procurado. Se essa resposta não for devidamente tratada ou rejeitar os caracteres de controle de HTML, uma falha de *script* *cross-site* irá se aproveitar dessa resposta. Um ataque refletido é normalmente entregue via *e-mail* ou um *site* neutro. A isca é uma URL de aparência inocente, apontando para um site confiável, mas contendo o vetor de XSS. Se o *site* confiável é vulnerável ao vetor, clicar no *link* pode fazer com que o navegador da vítima execute o *script* injetado.

### Persistente

A vulnerabilidade XSS persistente (ou armazenados) é uma variante mais devastadora de uma falha de *script cross-site*: ocorre quando os dados fornecidos pelo atacante são salvos pelo servidor e, em seguida, exibidos em páginas "normais" retornadas para outros usuários no curso de uma navegação normal, sem HTML adequada.

Um exemplo clássico disso é com fóruns *[online](https://pt.wikipedia.org/wiki/Online)* onde é permitido enviar mensagens formatadas em HTML para que outros usuários possam ler. Por exemplo: suponha que exista um *site* de namoro onde os membros verificam os perfis de outros membros para ver se eles parecem interessantes. Por razões de privacidade, este *site* esconde o verdadeiro nome e *e-mail* de todos. Estes são mantidos em segredo no servidor. A única vez que o verdadeiro nome e *e-mail* de um membro é exibido no navegador é quando o membro está logado, e eles não podem ver os dados de mais ninguém. Suponha que Mallory, um atacante, se cadastra no *site* e quer descobrir os verdadeiros nomes das pessoas que ela vê. Para isso, ela escreve um *script* projetado para rodar nos navegadores das outras pessoas quando visitam seu perfil. O *script*, então, envia uma mensagem rápida para o seu próprio servidor, que recolhe esta informação. Para fazer isso, para a pergunta "Descreva o seu primeiro encontro ideal", Mallory dá uma resposta curta (parece normal), mas o texto no final da sua resposta é seu script para roubar nomes e *e-mails*. Se o *script* é colocado dentro de um elemento <script>, não será mostrada na tela. Então, suponha que Bob, um membro do *site* de namoro, chega no perfil de Mallory, que tem a resposta para a pergunta de primeiro encontro. Seu *script* é executado automaticamente pelo navegador e rouba uma cópia do verdadeiro nome e *e-mail* do Bob diretamente de sua própria máquina.

XSS persistente pode ser mais significativo do que outros tipos porque o *script* malicioso de um atacante é processado automaticamente, sem a necessidade de orientar as vítimas individualmente ou atraí-los para um site de terceiros. Particularmente no caso de *sites* de redes sociais, o código seria mais projetado para se autopropagar através de contas, criando um tipo de verme do lado do cliente. Os métodos de injeção podem variar muito, em alguns casos, o atacante não precisa nem mesmo interagir diretamente com a funcionalidade *web* para explorar esta vulnerabilidade. Todos os dados recebidos pela aplicação *web* (via *e-mail*, *[logs](https://pt.wikipedia.org/wiki/Log_de_dados)* de sistema, [IM](https://pt.wikipedia.org/wiki/Mensageiro_instantâneo) etc.) que podem ser controlados por um invasor podem se tornar um vetor de injeção.

Exemplo de XSS persistente: Uma vulnerabilidade persistente multiplataforma *cross-scripting* juntamente com um *[worm](https://pt.wikipedia.org/wiki/Worm)* de computador permitiu a execução de um código arbitrário e a listagem do conteúdo do sistema de arquivos através de um filme QuickTime no MySpace.

### Vulnerabilidades do lado do servidor em relação à base de DOM

Historicamente, o XSS foi encontrado pela primeira vez em aplicações que realizavam todo o processamento de dados no lado do servidor. A entrada do usuário (incluindo XSS vetor) seria enviada para o servidor e, em seguida, enviado de volta para o usuário como página *web*. A necessidade de melhoria da experiência do usuário resultou na popularidade de aplicações com maior parte da lógica de apresentação de trabalho em JavaScript do lado do cliente e puxando dados em tempo real do servidor usando AJAX. Como o código JavaScript também estava processando a entrada do usuário e desenhando conteúdo da página *web*, uma nova subclasse de ataques XSS refletidos começaram a ser encontradas e foram chamados scripts baseados em DOM *cross-site*.

Nos XSS baseados em DOM, os dados maliciosos não tocam no servidor web e está sendo refletida pelo código JavaScript, totalmente no lado do cliente. Um exemplo de XSS baseado em DOM é um bug encontrado em 2011 em um número de plugins jQuery. A prevenção de XSS baseado em DOM inclui medidas muito semelhantes às XSS tradicionais, apenas implementadas em código JavaScript enviados em páginas da web -. Validação de entrada e Saída. Alguns *frameworks* JavaScript tem medidas embutidas contra esses e outros tipos de ataque.

Exemplo de XSS baseados em DOM: Antes que o *[bug](https://pt.wikipedia.org/wiki/Bug)* fosse resolvido, páginas de erro Bugzilla estavam abertas a ataques XSS baseados em DOM em que HTML arbitrários e scripts poderiam ser injetados através de mensagens de erro forçados.

## Proteção

Apesar de várias ocorrências de XSS e das diferentes formas de exploração, impedir a própria vulnerabilidade é conceitualmente simples. O que a torna problemática na prática é a dificuldade de identificar todos os campos da aplicação onde há dados manipulados pelo usuário e que serão posteriormente exibidos em tela. A causa do XSS refletido e persistente é que estes dados são inseridos em respostas da aplicação sem validação. Para eliminar tais vulnerabilidades, o primeiro passo é identificar todas as instâncias dentro da aplicação em que os dados são colocados nas respostas das requisições. Uma vez identificados os locais destes dados, é necessário realizar os seguintes procedimentos:

- Validação de Entrada
- Validação de Saída

### Validação da entrada

Este é o momento em que a aplicação recebe os dados fornecidos pelo usuário, que podem ser apresentados em respostas futuras. É necessário que a aplicação realize uma validação dentro do contexto daquele conteúdo, tornando-o mais restrito possível, por exemplo:

- Limitando o tamanho do campo a ser inserido
- Definindo o conjunto de caracteres aceito pela aplicação
- Estabelecendo uma expressão regular para os dados

Estas regras de validações variam de acordo com o campo e com o contexto da aplicação, por exemplo, nomes, endereços de *e-mails*, números de contas e cartões, ou seja, de acordo com o tipo de informação, espera-se um formato pré-determinado de conteúdo.        

### Validação da Saída

Agora é a vez da aplicação copiar em suas respostas os dados que originados por algum usuário ou até mesmo por terceiros. Estes dados devem ser codificados em HTML para tratar potenciais caracteres maliciosos. Codificação em HTML é a técnica de substituir os caracteres literais pela sua entidade HTML correspondente. Isto garante que o navegador, *[browser](https://pt.wikipedia.org/wiki/Browser)*, irá exibir, como saída, tais caracteres de forma segura, tratando-o como parte do documento HTML e não da sua estrutura. Alguns deste caracteres são:

- " → &quot;
- ' → &apos;
- & → &amp;
- < → &lt;
- \> → &gt;        

Os caracteres também podem ser representados por seu código correspondente na tabela ASCII:

- % → &#37;
- \* → &#42;

Há algumas funções que fazem a codificação automaticamente para o desenvolvedor:

- PHP [htmlspecialchars()](http://php.net/manual/pt_BR/function.htmlspecialchars.php), [htmlentities()](http://php.net/manual/pt_BR/function.htmlentities.php)
- ASP.NET [Server.HTMLEncode()](http://msdn.microsoft.com/en-us/library/ms525347(v=vs.90).aspx)

Segue um exemplo de código Java que faz o tratamento de caracteres especiais, podendo sua lógica ser aplicada a outra linguagem de programação:

```
public static String HTMLEncode(String s) {

  StringBuffer out = new StringBuffer();

  for (int i = 0; i < s.length(); i++) {
    char c = s.charAt(i);

    if(c > 0x7f || c==’”’ || c==’&’ || c==’<’ || c==’>’)
      out.append(“&#” + (int) c + “;”);
    else out.append(c);

  }
  return out.toString();

 }
```

O ideal é que a aplicação combine ambas as técnicas, oferecendo assim, duas camadas de proteção, diminuindo as chances do invasor conseguir burlar os filtros utilizados.

## *Background*

A segurança na Internet baseia-se numa variedade de mecanismos, incluindo um conceito subjacente de confiança conhecida como a mesma origem política. Isto, essencialmente, afirma que, se o conteúdo de um site (como [https://mybank.example.com](https://mybank.example.com/)[*[ligação inativa\]*](https://pt.wikipedia.org/wiki/Wikipédia:Ligação_inativa)) é concedida a permissão para acessar os recursos do sistema, então qualquer conteúdo desse *site* vai compartilhar essas permissões, enquanto o conteúdo de outro *site* (https:/ / othersite.example.com) essas permissões terão que ser concedidas separadamente.

*Cross-site scripting* usa vulnerabilidades conhecidas em aplicações baseadas na *web*, seus servidores ou sistemas de *plug-ins* nos quais eles dependem. Explorando um destes, eles inserem conteúdo malicioso para o conteúdo a ser entregue a partir do site comprometido. Quando o conteúdo combinado resultante chega ao navegador do lado do cliente, tudo tem sido entregue a partir da fonte confiável e, portanto, atua de acordo com as permissões concedidas a esse sistema. Ao encontrar maneiras de injetar *scripts* maliciosos em páginas web, um atacante pode obter acesso com privilégios elevados para o conteúdo crítico da página, cookies de sessão, e uma variedade de outras informações mantidas pelo navegador em nome do usuário. Ataques de *cross-site scripting*, portanto, são um caso especial de injeção de código.

A expressão "cross-site scripting" originalmente se referia ao ato de carregar a aplicação web de terceiros atacada a partir de um *site* de ataque independente, de forma que executa um fragmento do JavaScript preparado pelo atacante no contexto de segurança do domínio de destino (uma vulnerabilidade de XSS refletido ou não persistente). A definição gradualmente expandiu para incluir outros modos de injeção de código, incluindo persistentes e não JavaScript vetores (incluindo ActiveX, Java, VBScript, Flash, ou mesmo scripts HTML), causando alguma confusão aos recém-chegados ao campo da segurança da informação.

Vulnerabilidades XSS têm sido relatadas e exploradas desde a década de 1990. Sites proeminentes afetados no passado incluindo sites de redes sociais Twitter, Facebook, MySpace, YouTube e Orkut. Nos últimos anos, falhas de *cross-site scripting* superaram os [transbordamentos de dados](https://pt.wikipedia.org/wiki/Transbordamento_de_dados) para se tornar a vulnerabilidade de segurança mais comum relatada. Alguns pesquisadores afirmaram em 2007 que mais de 68% dos sites são considerados abertos a ataques XSS.

## Ligações externas

- [WhiteHat Security － *Vulnerabilties White Paper*](https://web.archive.org/web/20090126233751/http://whitehatsec.com/home/assets/WPStatsreport_100107.pdf)
- [OWASP](https://pt.wikipedia.org/wiki/OWASP): [XSS](http://www.owasp.org/index.php/XSS), [*Testing_for_Cross_site_scripting Testing for XSS*](http://www.owasp.org/index.php/), [*Reviewing_Code_for_Cross-site_scripting Reviewing Code for XSS*](http://www.owasp.org/index.php/)
- [*Simple XSS explanation*](http://www.houbysoft.com/papers/xss.php)[*[ligação inativa\]*](https://pt.wikipedia.org/wiki/Wikipédia:Ligação_inativa)
- [*The Web Application Security Consortium's Cross-site Scripting Threat Classification Entry*](http://projects.webappsec.org/Cross-Site-Scripting)
- [*The Web Application Hacker´s Handbook - 2nd Edition*](https://www.amazon.com/The-Web-Application-Hackers-Handbook/dp/1118026470)

[![Procurar imagens disponíveis](https://upload.wikimedia.org/wikipedia/commons/thumb/f/fe/Crystal_Clear_app_demo.png/22px-Crystal_Clear_app_demo.png)](https://fist.toolforge.org/fist.php?doit=1&language=pt&project=wikipedia&data=Cross-site_scripting&datatype=articles&params[catdepth]=3&params[random]=50&params[ll_max]=5&params[free_only]=1&params[commons_max]=5&params[flickr_max]=5&params[include_flickr_id]=1&params[flickr_new_name_from_article]=1&params[wts_max]=5&params[gimp_max]=5&params[esp_max]=5&params[esp_skip_flickr]=1&params[geograph_max]=5&params[forarticles]=noimage&params[lessthan_images]=3&params[default_thumbnail_size]=250&params[jpeg]=1&params[png]=1&params[gif]=1&params[svg]=1&params[min_width]=80&params[min_height]=80&sources[languagelinks]=1&sources[commons]=1&sources[flickr]=1)

- [![img](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d7/Crystal_Clear_app_ktalkd.png/25px-Crystal_Clear_app_ktalkd.png)](https://pt.wikipedia.org/wiki/Ficheiro:Crystal_Clear_app_ktalkd.png) **[Portal das tecnologias de informação](https://pt.wikipedia.org/wiki/Portal:Tecnologias_de_informação)**

[Categorias](https://pt.wikipedia.org/wiki/Especial:Categorias): 

- [Segurança da informação](https://pt.wikipedia.org/wiki/Categoria:Segurança_da_informação)
- [Falhas em segurança de computadores](https://pt.wikipedia.org/wiki/Categoria:Falhas_em_segurança_de_computadores)

- Esta página foi editada pela última vez às 21h20min de 19 de m