O termo VDC (Virtual Data Center) vem de uma forma de comercialização da tecnologia disponível em um Data Center.

_**Cloud Computing**_

O _**cloud computing**_ é um sistema que permite criar uma estrutura onde possa haver ampliação e redução de recursos sem que uma aplicação possa perceber. Trata-se, portanto, de um software (_**hypervisor**_) que produz uma máquina abstrata e, pelo fato de ser abstrata, permite usar os recursos físicos de um hardware que podem ser um, dois ou N computadores, servidores, storage, etc., e, tudo isto, sem que o usuário daquela máquina abstrata perceba.

**Virtual Data Center**

Agora que já revisamos o que é o _**cloud computing**_, fica mais fácil entender o que é um VDC. Bem, antes que ocorra uma confusão, logo acima está colocado que o termo vem de uma forma de comercialização, portanto, é preciso definir mais algumas expressões. O Data Center (sem o termo “Virtual” na frente) é uma estrutura física que contém computadores, servidores, storage e internet. Todos estes elementos conectados entre si ou não. Entre estes elementos existem os que são de propriedade do Data Center e aqueles que são de propriedade dos clientes. Estas diferenças são os diferentes serviços oferecidos pelo Data Center. Por exemplo, quando o servidor que está localizado dentro do Data Center é de propriedade do cliente, o serviço é chamado **“Colocation”** e este termo vem de Co-location, ou seja, o cliente e o Data Center teriam co-participação no serviço. Mas o que o cliente ganha? O cliente que contrata um co-location é uma empresa que tem seus servidores, sistemas operacionais, bancos de dados, discos, mas está interessada em instalá-los no Data Center para ganhar em:

1. Uma internet garantida para acesso aos seus servidores;
    - O Data Center contrata vários provedores de internet (quando não é ele mesmo um provedor) e usa _balance line_ automático, isto é, cai um link, entra outro sem se perceber.
2. Banda larga;
    - A banda contratada pelo Data Center é infinita sob o ponto de vista do cliente. São contratos maiores e garantidos de banda larga. Alguns Data Centers têm seus próprios cabos submarinos e links direto com Miami.
3. Energia garantida;
    - Dada a própria obediência as normas, um Data Center tem disponibilidade muito maior que uma empresa poderia ter se mantivesse o próprio servidor.
4. Segurança contra-ataques, vírus, espionagem em geral;
    - O Data Center protege os links de internet com técnicas muito além de softwares de segurança. São hardwares especializados. Alguns chegam a “desmontar” o TCP/IP, limpá-lo de inconsistências protocolares e remontá-lo novamente.
5. Proteção contra incêndio.
    - O Data Center tem esta proteção por norma, como sistemas que apagam incêndios sem prejudicar o equipamento.

Estes 5 itens significam uma só expressão: _**Business Continuity**_

Outro modelo de comercialização seria o servidor dedicado. Neste modelo, tudo é do Data Center e o cliente instala seus softwares, mas o limite é o servidor.

Mas, se o Data Center mantiver este mesmo modelo de negócios, ou oferecer colocation ou Servidores próprios, mas dedicados, o investimento, ou melhor, o retorno do investimento (ROI – _**Return of Investment**_) será baixo, pois todo aquele espaço estará ocioso. E, acredite, não adianta tentar passar a conta para o cliente, simplesmente porque os clientes “gordos” são disputados entre os concorrentes e sobram os “magros” cuja ociosidade não consegue se recompensada.

Se o Data Center tem tudo fisicamente e pode oferecer aqueles serviços expressados acima, o que seria o VDC? O Data Center colocaria suas estruturas físicas controladas por programas _**hypervisors**_ e prepara um outro programa, chamado de “Portal do Cliente”, cuja função é “falar” para o _**hypervisor**_ o que o cliente quer, podendo mudar esta configuração a qualquer momento, **pronto!** Agora o Data Center é um “Virtual Data Center”.

E o que o Virtual Data Center ganha? Ganha muito.

1. O mais importante: ganha a superutilização de seus recursos.
    - Como tudo é virtual, estruturas pequenas, que antes utilizariam um servidor e o restante desse hardware ficaria ocioso, agora compartilha outros clientes pequenos de forma satisfatória.
2. A condição para ser Green.
    - Com o ganho do item 1, a energia gasta para os dois clientes será a mesma, mostrando um ganho energético do Data Center melhorando o PUE (_Power Usage Effectiveness_) conseguindo o selo “Green Data Center”
3. Flexibilidade Comercial.
    - O cliente pode formatar exatamente o que precisa, então não há nada que o Data Center não possa oferecer.
4. Menos tráfego de pessoas no Data Center.
    - Sendo virtual, não há qualquer razão para o cliente visitá-lo periodicamente, para dar manutenção. O ganho é bem claro em segurança de acesso (menos processos e pessoal de segurança). Além de menos pessoas dentro do Data Center, sabendo que o custo em calor de uma pessoa representa 100 Watts (economia em climatização), etc.
5. Competição em faixas de preços baixos.
    - Uma vez que o cliente pode utilizar apenas uma porção de um hardware físico, não há motivos para oferecer serviços para qualquer tamanho de empresa ou pessoa física.

Estes 5 itens significam uma só expressão: _**Return of Investment**_

**Como se prepara um Data Center para tornar-se um Virtual Data Center?**

Em um Virtual Data Center, como o nome diz, o cliente pode entrar na sua máquina e virtualmente está acessando um Data Center completo. Existem alguns mecanismos essenciais que garantem esta possibilidade.

É preciso fornecer toda a condição preconizada pelos conceitos explicitados acima. Então existem, computadores, servidores, storage e internet, conectados logicamente. Esta lógica precisa ser configurada, ou seja, pode-se querer que o servidor X converse com o storage A, mas não com o storage B. Pode-se desejar que o servidor X acesse a internet, mas o servidor Y (do mesmo cliente) não acesse a internet. É esta elasticidade que, antes precisava ser feita pelo cliente com seus administradores de redes, mas agora tem que ser automático.

A figura 1 demonstra simbolicamente como é o Virtual Data Center (não o Data Center que está dando suporte ao VDC).

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/3/273361/15113.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/3/273361/15113.png)

Figura 1. Estrutura simbólica de um Virtual Data Center (VDC)

Fonte: EMC - (CIS Modulo 8)

Na prática, como é possível que o Data Center garanta o famoso: _**Business Continuity**_?

Não se pode dizer que é fácil, mas o que se procura, não querendo entrar muito profundamente nisto, é eliminar o “_**SINGLE POINT OF FAILURE**_ **(SPOF)**”.  A tradução direta da expressão não tem um significado muito válido, mas o quer se quer dizer com isto é “a parte do sistema (rede, servidor, aplicação, sistema operacional, disco, internet) que, se parar, para tudo! O que se faz no Data Center é criar estruturas que eliminam o **SPOF**.

A figura 2 representa bem isto. Observando a figura 2, pode-se ver que foram tomados cuidados especiais com cada ponto que pode causar falhas irrecuperáveis. Duplicidade, ou redundância, é a chave para isto.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/2/273293/15114.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/2/273293/15114.png)

Figura 2. Medidas físicas para eliminação do SPOF

Fonte: EMC - CIS Modulo 7

O que se consegue com todos estes cuidados e redundâncias é algo chamado de _**Fault Tolerance.**_ Um sistema tolerante a falhas não é um grupo de sistemas, equipamentos, rede, etc., que não falham. Muito pelo contrário. São sistemas que podem falhar, mas o serviço continua disponível.

Para que exista a essência deste tipo de serviço, são imprescindíveis as seguintes características, mostradas na figura 3.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/3/273348/15115.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/3/3/273348/15115.png)

Figura 3. Características fundamentais para a disponibilização do VDC.

Fonte: EMC - CIS Módulo 8.

Apresentando cada elemento da figura 3, pode-se descrever o que representa este grupo de características fundamentais para criar um negócio VDC.

- **On-Demand Self Service.**

Esta é a porção do serviço que está à frente da comercialização dos produtos de um VDC. Significa que o usuário entra em um portal (uma aplicação web, na maioria dos casos, e escolhe o que quer. Um servidor, com windows server 2012, mais um storage com 1 TB em configuração RAID5, um outro servidor com ORACLE 8i e uma largura de banda de acesso de 50 Mbs. Assim, simples – Self Service.

- **Rapid Elasticity.**

Isto representa escalabilidade, ou seja, o cliente pode começar pequeno e crescer em termos de recursos. E o mais importante, estas mudanças, tanto para mais como para menos, ocorrem sem interrupção dos serviços. Interessantemente, este modelo de negócios é um fomentador de negócios, pelo fato de se poder começar um negócio com pouquíssimo investimento e, se por acaso, houver um dimensionamento errado no planejamento, o negócio não é prejudicado.

- **Broad Network Access.**

Esta expressão significa um accesso de largo espectro em termos de tecnologia e plataformas, ou seja, o cliente (e o cliente do cliente) fará o acesso aos recursos de qualquer plataforma. Pode ser um computador pessoal, outro servidor, um tablet ou um smartphone, pode ser windows, IOS, linux, Unix, VMS, etc. Este material didático está sendo digitado em uma máquina linux conectada à internet, mas está usando um recurso no Data Center da Microsoft, em uma área de 1 TB reservada para este autor e, um sistema aplicativo, lá no VDC, está “pensando” que está sendo tudo digitado em WORD naquele servidor da Microsoft.

- **Resource Pooling.**

Existe um pool de recursos. Quer dizer que os recursos estão lá e podem ser usados por vários usuários ao mesmo tempo. Este é uma tecnologia baseada no modelo multi-tenant, isto é, múltiplas instâncias. Aqui que os custos são otimizados para o VDC.

- **Measured Service.**

Os serviços são medidos. Quer dizer que existe uma contagem de serviços utilizados e em quanta quantidade. Isto vai para uma conta (bill) onde há um detalhamento. Semelhante à sua casa. Existem os serviços de energia elétrica, água e esgoto, gás e limpeza. Cada serviço aparece na sua conta, quantificado e precificado. Desta forma existe total transparência, na melhor filosofia do pay-per-use (paga pelo uso).

Estes fundamentos são a alma do negócio chamado VDC. Agora, talvez, o leitor possa entender bem a definição no começo desse tópico - **O termo VDC (Virtual Data Center) vem de uma forma de comercialização da tecnologia disponível em um Data Center.**

**Exemplos de VDCs Brasileiros**

Aqui se apresentam alguns casos brasileiros de VDCs, mostrando a tela principal de seus sites comerciais e os apelos comercias mais importantes.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/8/268865/15116.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/8/268865/15116.png)

Figura 5. Embratel

Fonte: portal.embratel.com.br/cloud/datacenter-virtual/

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/8/268863/15117.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/8/268863/15117.png)

Figura 6. Viasite.

Fonte: www.viasite.com.br/quemsomos/

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/1/270191/15118.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/7/0/1/270191/15118.png)

Figura 7. Ascenty

Fonte: www.ascenty.com