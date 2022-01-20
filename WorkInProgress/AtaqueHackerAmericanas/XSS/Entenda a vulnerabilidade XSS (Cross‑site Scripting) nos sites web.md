# Entenda a vulnerabilidade XSS (Cross‑site Scripting) nos sites web

Neste post explicamos de forma simples o que é a vulnerabilidade XSS, e como é possível estar prevenido para poder navegar de forma segura.

[![Editor](https://www.welivesecurity.com/wp-content/uploads/2014/02/android5_A-222x179.png)](https://www.welivesecurity.com/br/author/editorla/)

[Editor](https://www.welivesecurity.com/br/author/editorla/)

**7 Jul 2017 - 01:38PM**

Compartilhar

Sabemos que muitos cibercriminosos aproveitam vulnerabilidades em diferentes servidores, em qualquer lugar do planeta, com a finalidade de hospedar campanhas de phishing ou malware. No entanto, muitas vezes exploram vulnerabilidades já conhecidas, que se encontram presentes há anos no top 10 do OWASP. A vulnerabilidade conhecida como **Cross Site Scripting** (XSS) ou execução de comandos em sites cruzados é uma das mais habituais. Saiba como essa vulnerabilidade funciona, a forma que utiliza para afetar as vítimas, e como é possível estar prevenido.

## Como funciona uma vulnerabilidade XSS?

Em primeiro lugar, é importante ter em conta que com essa vulnerabilidade, os atacantes aproveitam a confiança que existe entre um usuário e um site em particular, o que já nos dá uma dimensão do impacto que pode ter.

Esse tipo de vulnerabilidade pode ser explorada de duas maneiras: de forma refletida e de forma persistente. A seguir, farei uma breve explicação sobre cada uma delas.

- **Refletida**

Consiste em modificar valores que o aplicativo web usa para enviar variáveis entre duas páginas. Um clássico exemplo disso é fazer com que através de um buscador seja executada uma mensagem de alerta em JavaScript. Com o XSS refletido, o atacante pode roubar as cookies para, em seguida, também roubar a identidade, mas para isso, deve fazer com que a vítima execute um determinado comando dentro do endereço web.

Para realizar essa ação, os cibercriminosos podem enviar emails maliciosos fazendo com que as vítimas cliquem em um link disfarçado e, dessa forma, ocorra o roubo.

- **Persistente**

Consiste em inserir um perigoso código HTML (programação web) em sites e, desse modo, se tornar visível para os usuários que acessem ao site modificado.

## O que significa dizer que um site web é vulnerável a XSS?

Se um site contém essa vulnerabilidade, um cibercriminoso pode realizar diversos tipos de ataques com base na relação de confiança entre o usuário e a plataforma, como redirecionar para outro site, com o intuito de roubar informações por meio de um phishing, ou até mesmo baixar alguma ameaça para que seja executada no sistema.

Em última instância, um Cross-site Scripting também pode tornar um site legítimo extremamente perigoso para o usuário.

## Por que ou como essa vulnerabilidade é produzida?

Normalmente isso ocorre devido à falta ou pouca frequência dos controles necessários no site, que impedem a execução de comandos desde a mesma página web. Se isso acontece, um cibercriminosos pode conseguir executar scripts (pequenos programas) em linguagem como Java Script ou HTML, entre outros.

Os scripts são uma série de instruções para executar, que podem estar programadas em Java, HTML ou qualquer outra linguagem sempre e quando o ambiente, onde será executado, seja confiável. Apesar do uso de scripts ajudarem a automatizar muitas atividades dos administradores, também são utilizados pelos atacantes para automatizar ataques, fazendo com que esses pequenos programas trabalhem (por si só) roubando informações quando a vítima acesse ao site vulnerado.

## XSS na prática

Para entender como funciona, usaremos como exemplo uma situação que pode ser cotidiana. Vamos imaginar as seguintes situações:

- Por um lado, o servidor “A” que pertence ao “mibanco.com”, o qual é vulnerável a XSS.
- Por outro lado, um atacante que consegue injetar um código malicioso no “meubanco.com” por meio da exploração da XSS. O código que injeta faz com que, depois que o usuário acesse a página, seja redirecionado para outro site exatamente igual ao “meubanco.com”.
- O usuário vítima acessa por meio do navegador ao “meubanco.com”; no entanto, ao executar o código malicioso injetado pelo atacante (sem saber), estará registrando os seus dados no site clonado. Obviamente, isso compromete completamente as suas informações financeiras.

Isso apenas é um exemplo de uma das consequências da falta de controles, embora também possa ocorrer que o site baixe o malware ou algum tipo de exploit que se aproveita de alguma vulnerabilidade no sistema da vítima, conseguindo obter acesso ao equipamento pessoal.

## Como evitar ser vítima da vulnerabilidade XSS?

En primer lugar es fundamental**,** como siempre mencionamos, que cuentes con una solución de seguridad instalada y actualizada. Esto es importante ya que ante la ejecución de alguna aplicación maliciosa sin tu consentimiento, tal como *malware* o *exploits*, **automáticamente será bloqueada**.

Em primeiro lugar, é fundamental contar com uma solução de segurança instalada e atualizada. Isso é importante para que antes de executar qualquer aplicativo malicioso sem o seu consentimento, como um malware ou exploits, o mesmo seja automaticamente bloqueado.

Além disso, caso seja um redirecionamento para algum site de phishing, você já contará com uma proteção antivírus e o bloqueio proativo pelos navegadores.

Em segundo lugar, é muito importante estar sempre atento ao acessar uma página: é fundamental observar o endereço URL ao qual está acessando. Já temos visto exemplos disso, como os endereços de Facebook, que podem ser aproveitados por cibercriminosos, caso você não tenha em conta alguns detalhes, como já vimos anteriormente.

Por outro lado, existem complementos para os navegadores que bloqueiam esses scripts nos sites. Um deles é o [NoScript](https://noscript.net/), que permite realizar configurações personalizadas (e é gratuito).

Nunca é demais utilizar navegadores alternativos, talvez nem tão populares, como o Opera, o Comodo ou o Chomium, entre outros. Dessa forma, se um atacante lança um ataque que tenta explorar alguma vulnerabilidade em um dos navegadores mais conhecidos através de um exploit, ao não serem cumpridas todas as condições para a total exploração da vulnerabilidade, o acesso ao sistema será negado.

Às vezes, algumas dessas vulnerabilidades excedem aos usuários, já que pode se tratar de um problema que não é resolvido apenas com a instalação de atualizações no equipamento. No entanto, por outro lado, para resolver esse tipo de problema, é necessário que o administrador do site adicione os controles necessários para que nada possa ser modificado por um terceiro.

*Créditos da imagem:* [*©Toshiyuki IMAI/Flickr*](https://www.flickr.com/photos/matsuyuki/3900235390/in/photostream/lightbox/)