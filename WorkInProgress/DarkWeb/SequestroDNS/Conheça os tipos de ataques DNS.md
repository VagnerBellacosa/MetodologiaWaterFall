#### [ Dicas](https://fasthelp.com.br/categoria/dicas/) | [Notícias](https://fasthelp.com.br/categoria/noticias/)

# Conheça os tipos de ataques DNS



#### [0 Comment(s)](https://fasthelp.com.br/ataques-dns/#respond)



[wtr-time]

![img](https://secure.gravatar.com/avatar/9e56d9c0ca8706e2d4c5a8b273407e8f?s=96&d=blank&r=g)

#### Escrito por [admin](https://fasthelp.com.br/author/admin/)

Em 16/05/2018

![ataques-dns](https://i0.wp.com/fasthelp.com.br/wp-content/uploads/2018/05/ataques-dns.png)

Em outubro de 2016, um **[enorme ciberataque](https://www.forbes.com/sites/akamai/2017/09/14/companies-under-threat-of-dns-attacks-must-measure-risk-appetite/#67a1469b6078)** conseguiu derrubar algumas das empresas mais famosas e importantes da internet. Twitter, Netflix e Amazon (para citar só algumas) ficaram foram do ar. Usuários e clientes não conseguiam acessar os serviços. A ofensiva foi coordenada através de uma botnet (rede de robôs), que realizou um ataque chamado DDoS (distributed-denial-of-service). Um detalhe interessante é que para derrubar os serviços foram usados dispositivos como câmeras digitais e toca DVDs com conexão à internet, a chamada internet das coisas.

Esse é apenas um exemplo de como os ataques DNS podem ser perigosos e causar prejuízos para empresas que dependem da internet para funcionar. E, hoje em dia, qual empresa não depende?

De acordo com um **[estudo](https://www.forbes.com/sites/akamai/2017/09/14/companies-under-threat-of-dns-attacks-must-measure-risk-appetite/#67a1469b6078)** feito no ano passado, ataques DNS causaram perdas de US$ 2,2 bilhões (R$ 7,9 bilhões, aproximadamente) em 2016, um prejuízo de US$ 2,5 milhões (R$ 9 milhões) por organização. Uma empresa pode perder US$ 100 mil (R$ 362 mil) por hora durante um evento como esse. Por isso, é preciso tomar medidas de segurança para que isso não volte a acontecer, embora seja inevitável a ocorrência dos ataques DNS. Mas existem maneiras de defender seu site e seus negócios.

A seguir, entenda o que é a DNS, os principais tipos de ameaças e saiba como se defender.

## O que é DNS?

Para entender a gravidade dos ataques DNS, é preciso entender do que se trata esse termo. A sigla quer dizer Sistema de Nomes de Domínios (Domain Name System). Basicamente, esse sistema “traduz” os domínios dos sites para números de IP. O funcionamento da internet é todo baseado nesses números.

Os endereços dos sites em forma de texto servem para ajudar os usuários a lembrar dos nomes. Mas, assim que você digita na barra do navegador para onde quer ir, um sistema de servidores e base de dados entra em ação. Esse sistema se chama DNS.

## Agenda telefônica da web

Existem diversos servidores DNS pelo mundo todo, e é neles que estão armazenados os endereços IP dos sites. Eles são a agenda telefônica da rede mundial de computadores. Você procura pelo nome de alguém (um site) e lá você acha o número (de IP). Sabendo esse número, nossos navegadores têm acesso às informações armazenadas e disponibilizadas nos sites.

## O alvo preferido

Por se tratar de uma estrutura essencial para o funcionamento de basicamente todas as operações feitas pela internet, O DNS está sujeito a diversos tipos de ataque. Podem ser usados malwares para roubar senhas e dados pessoais; hackers podem redirecionar um site para enganar os usuários; uma página pode ser derrubada e ficar horas fora do ar por conta de um ataque coordenado. Cibercriminosos gostam de fazer ataques DNS e, por isso, é preciso estar atento a cada um deles.

## Ataque do tipo Zero Day

É dos ataques DNS mais complexos porque explora falhas novas nos serviços. Muitas vezes nem mesmo pesquisadores da área conhecem o problema de segurança e os hackers se aproveitam para organizar ações enquanto proteções não são desenvolvidas.

## Denial of Service

Acontece quando milhares de robôs enviam tráfego a um site ao mesmo tempo. Na maioria das vezes, o endereço não está preparado para a quantidade de pedidos de acesso. Assim, o servidor onde o site está hospedado torna o site indisponível porque não é capaz de processar o alto número de acessos que acontecem repentinamente. É dos ataques DNS mais comuns. Existe ainda uma outra variação desse tipo de ação chamada Distributed Denial of Service.

## Fast Flux DNS

Aqui, os hackers usam um nome de domínio (o endereço do site) legítimo para esconder endereços de IP que distribuem conteúdos maliciosos, como malware e páginas usadas para fazer phishing. Isso é possível mudando os registros DNS com uma frequência altíssima. O grande problema desse tipo de estratégia é que fica difícil se defender. Caso algum endereço de IP malicioso seja identificado, ele rapidamente será trocado por outro, o que dificulta (e muito) o combate a esse tipo de estratégia.

## DNS Spoofing

Nesse tipo de ataque DNS, dados maliciosos são inseridos no cache do servidor DNS. O resultado é que toda vez que ele for consultado a respeito de certos dados, fornecerá um endereço IP comprometido, que levará o tráfego de um determinado site a um computador preparado para infectar os usuários ou roubar seus dados. Há **[outra maneira](https://www.welivesecurity.com/br/2018/01/29/como-funciona-um-ataque-dns-spoofing/)** dessa categoria de ataques DNS ser estruturada: um hacker pode invadir o roteador de um usuário e mudar os endereços DNS usados pelo aparelho. Isso quer dizer que os endereços digitados podem ser redirecionados para páginas maliciosas.

## DNS Cache Poisoning

É similar ao DNS Spoofing, mas a infecção acontece nos arquivos cache que ficam no servidor DNS. O hacker troca o arquivo cache que está armazenado no servidor por um malicioso, que leva o usuário a uma página preparada para cometer crimes. Os provedores de serviço usam esses arquivos de cache para economizar tempo, já que o internauta não precisa requisitar e receber os dados do IP; recebe uma versão recente daquele site através do cache.

## DNS Amplification

Mais uma variação dos ataques DNS do tipo Negação de Serviço Distribuída. Nesse caso, o ataque é feito da seguinte maneira: em vez de ordenar que milhares de bots pesquisem os serviços de DNS público ao mesmo tempo, o hacker faz intervenções menores, mas que resultam em pedidos de informação enormes. Ao invés de os próprios bots receberem a resposta dessa pesquisa, ela é direcionada ao endereço IP de alguma vítima. O volume das respostas é tão grande que acabam inviabilizando a resposta dos servidores do site alvejado e tiram sua infraestrutura de serviços do ar. 

## O que fazer para evitar ataques DNS?

Se ter um site que funcione sem parar é um pilar para que os negócios da sua empresa prosperem, você precisa se prevenir. Em vez de ter apenas um provedor de serviços DNS, tenha dois ou até mais. Assim, você evita depender de apenas uma infraestrutura para manter seus serviços disponíveis para os clientes.

Outra medida essencial é monitorar as comunicações DNS em tempo real, para que seja possível identificar rapidamente quando há algum tipo de atividade incomum ou maliciosa acontecendo e tomar medidas imediatas para resolver o problema. Também é preciso fazer verificações regulares contra vírus e malwares e manter todos os sistemas atualizados.



[Fale com um consultor](https://fasthelp.com.br/ataques-dns/#contato)

[← Qual é a importância dos Scanners de Porta?](https://fasthelp.com.br/scanners-de-porta/)[Windows 10, um sistema operacional repleto de problemas →](https://fasthelp.com.br/windows-10/)