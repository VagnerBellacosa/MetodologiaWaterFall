# O que é DNS Hijacking e como evitar que esse ataque ocorra no seu site

O DNS Hijacking é uma forma de intrusão que direciona o tráfego da web para sistemas de domínio não autorizados. Dessa forma, ocorre a interceptação das solicitações de um usuário e o redirecionamento para o servidor DNS comprometido do invasor.

[Ivan de Souza](https://rockcontent.com/br/blog/author/ivan/)



16 jul, 20 | Leitura: 6min

![dns hijacking](https://rockcontent.com/br/wp-content/uploads/sites/2/2020/07/dns-hijacking.jpg)

Os cibercriminosos sabem a importância do [**DNS (Domain Name System)**](https://rockcontent.com/br/blog/dns/) **ou Sistema de Nomes de Domínio para a usabilidade da Internet**. Ele é responsável por transformar endereços numéricos de IPs em nomes de domínio, que podem ser facilmente guardados e compartilhados pelas pessoas.

[Hackers](https://rockcontent.com/br/blog/hacker/) também entendem que esse é um protocolo confiável e que muitas organizações não monitoram seu tráfego DNS adequadamente para inibir ataques maliciosos. O DNS Hijacking é um tipo de sequestro do DNS, por meio da substituição da configuração TCP/IP que redireciona o tráfego para um servidor não autorizado e sob o controle do invasor.

Neste artigo, discutimos o que é o DNS Hijacking e como você, usuário da Internet, pode proteger seu sistema desse tipo de ataque. Veja, a seguir:

- **O que é DNS Hijacking?**
- **Qual o objetivo dos cibercriminosos?**
- **Como evitar esse tipo de ataque em seu site?**



## O que é DNS Hijacking?

O DNS Hijacking é uma forma de intrusão do DNS que **ocorre, principalmente, por meio de ataques de phishing**. Mas o sistema da vítima também pode ser invadido em plataformas de autoatendimento (provedores de serviços de Internet) e em provedores de DNS baseados em roteadores públicos.

Em infraestruturas domésticas, o DNS Hijacking se **aproveita da vulnerabilidade do firmware de roteadores**, que permite o acesso sem a solicitação de senha. Também, do desleixo dos usuários, que **mantêm as credenciais de fábrica dos aparelhos**, informações que podem ser facilmente encontradas pelos hackers para posterior acesso ao servidor.

Esses métodos de intrusão **direcionam o tráfego da web para DNSs não autorizados**. Dessa forma, ocorre a interceptação das solicitações de um usuário e o redirecionamento desse sistema para o servidor DNS comprometido do invasor.

O navegador exibe a URL original, o que faz o usuário acreditar que o [site](https://rockcontent.com/br/blog/site/) é confiável para acesso. Enquanto isso, as informações compartilhadas em sites e armazenadas no banco de dados são roubadas e todas as atividades executadas na máquina são monitoradas.

![dns hijacking](https://www.paloaltonetworks.com/content/dam/pan/en_US/images/cyberpedia/fig1-dns-hijack.png)

(Fonte: https://www.paloaltonetworks.com/content/dam/pan/en_US/images/cyberpedia/fig1-dns-hijack.png)

## Qual o objetivo dos cibercriminosos?

O objetivo desse tipo de ataque, além de **coletar informações pessoais e financeiras**, é fazer anúncios não autorizados na página do usuário, transformá-lo em audiência de sites com anúncios ou solicitar resgates de dados sequestrados, geralmente, pagos em criptomoedas. Isso [dificulta o rastreamento](https://rockcontent.com/br/blog/blockchain-e-marketing-digital/) do valor pelas autoridades.

O phishing, por exemplo, direciona o acesso para um site “disfarçado” e faz com que o usuário tenha a impressão de que a página é confiável. Nesse processo, são roubadas informações confidenciais, que podem ser **usadas em troca de resgates** ou para que o **cibercriminoso assuma a identidade do usuário** em transações online.

As instituições financeiras são o principal alvo de ataques de phishing porque o usuário enganado digita dados como número de conta, nome de usuário e senha na página falsa, sem perceber. Posteriormente, o hacker assume a conta na página verdadeira e realiza transações financeiras.

O sequestro de DNS não é imprescindível em ataques de phishing, porque eles acontecem a partir do acesso de links manipulados. No entanto, **quando o DNS está corrompido, um ataque de phishing pode ser ainda mais crítico**.

Isso porque, independentemente de o usuário ter inserido a URL correta ou clicar em um site a partir de um widget, ela ainda será redirecionada para esse site falso. Dificilmente o acesso despertará a desconfiança dos usuários e é isso que torna o DNS Hijacking ainda mais malicioso.

Em contrapartida, os **ataques de pharming não prejudicam o usuário**. Eles acontecem porque o invasor aproveita a “identidade digital” da vítima para transformá-la em **audiência em sites com anunciantes**, que pagam caro aos proprietários pelos cliques obtidos nesses ambientes.

O golpe direciona os usuários para um site falso, repleto de anúncios. Essas páginas da web não cumprem nenhuma função real, mas o operador gera receita cada vez que é visitado — mesmo que a pessoa feche a página imediatamente após a abertura. Com o lucro dessas operações, o cibercriminoso financia outras atividades criminosas.

## Somente cibercriminosos usam o DNS Hijacking?

Diferentemente dos que muitas pessoas pensam, o DNS Hijacking não serve apenas para práticas de [fraudes na Internet](https://rockcontent.com/br/blog/fraudes-na-internet/). O **sistema de intrusão também pode ser usado por outros agentes**.

Alguns governos, por exemplo, aplicam a prática para censurar a Internet: reprimem a oposição política ou proíbem acesso a conteúdos específicos, como sites com conteúdo ilícito ou pornográfico. Assim, usuários que tentam acessar esse tipo de conteúdo são redirecionados para outras páginas e recebem o aviso de que o site anterior está inacessível.

Alguns provedores de serviços da Internet também usam esse protocolo para exibir mensagens de erro quando usuários tentam acessar domínios que não existem. Por exemplo, se um usuário digita uma URL errada ou sem registro no DNS, é exibida a [mensagem de erro](https://rockcontent.com/br/blog/problema-dns-como-resolver/) NXDOMAIN.

Mas antes de o usuário receber essa resposta, a solicitação passa por todos os níveis de DNS para a verificação da existência dessa entrada. Nesse momento, o provedor de serviços da Internet intercepta a mensagem de erro e redireciona o acesso para outros ambientes, uma página popular, o site institucional do provedor ou páginas com anúncios, que aumentam a receita do negócio.

## Como evitar esse tipo de ataque no meu site?

O sequestro de DNS é uma prática muito usada por cibercriminosos e **deve ser combatida com um controle mais efetivo,** criado por meio de uma estratégia de segurança em camadas**.** Por exemplo, uma **solução de segurança baseada no DNS** poderia ter sido usada para impor uma política mais rígida aos dispositivos críticos da infraestrutura e bloquear os malwares, assim que fosse identificada a intrusão no “paciente zero”.

Essa identificação precoce permitiria que a equipe de resposta a incidentes solucionasse primeiro os dispositivos afetados, antes que outros sistemas fossem infectados. **Usar plataformas confiáveis, como a** [**Stage**](https://stage.rockcontent.com/br/?utm_source=SDL&utm_medium=sdl&utm_campaign=sdl&utm_term=sdl&utm_content=sdl)**,** também inibe a atuação de invasores e cibercriminosos e evita que seu [site WordPress seja hackeado](https://rockcontent.com/br/blog/site-wordpress-hackeado/).

No entanto, os usuários podem aumentar a segurança da sua infraestrutura com algumas medidas:

- **mude a senha** padrão do seu roteador e desative a opção de administração remota;
- faça atualizações constantes para inibir vulnerabilidades e falhas que não dizem respeito ao seu modo de uso;
- **atualize** o firmware do roteador;
- use ferramentas que bloqueiam pop-ups;
- clique em várias seções do site que você pretende visitar antes de escrever alguma credencial (dificilmente todo o layout da página de phishing é recriado);
- **verifique se as conexões são seguras**, por meio da existência do https:// antes da URL, e se o site tem algum certificado ou protocolos de segurança, como [o TLS](https://rockcontent.com/br/blog/tls/).

O DNS Hijacking pode ser usado de várias formas, mas todas elas são ilegítimas. Afinal, o usuário não tem consciência do uso de sua identidade digital: o IP do seu aparelho.

Por isso, veja como reforçar a [segurança digital](https://rockcontent.com/br/blog/seguranca-digital/) no seu acesso à Internet e garanta confiabilidade para todas as suas ações na web!

Compartilhe









![Ivan de Souza](https://secure.gravatar.com/avatar/eb1e3960268016620722afe889c85c81?s=172&d=mm&r=g)![Rock author vector](https://rockcontent.com/wp-content/uploads/2021/03/author-avatar-base.png)

Author

[Ivan de Souza](https://rockcontent.com/br/blog/author/ivan/)