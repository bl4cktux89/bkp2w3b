### Objetivo:

Neste tópico iremos descrever brevemente sobre os padrões que diferem os equipamentos utilizados nas redes sem fio wireless: Estes padrões ditam a tecnologia e diferem a performance dos produtos. Cada tecnologia contida num padrão adere a classes e velocidades que veremos a seguir.

### INTRODUÇÃO

As comunicações wireless para uso em redes de computadores começaram a tomar forma mesmo no ano de 1985 quando o FCC – _**Federal Communications Commision**_, órgão regulamentador das comunicações e radiofrequências Norte Americano, autorizou o uso público da banda ISM – _**Industrial, Scientific and Medical**_, que opera entre 902MHz e 5,85GHz sem a necessidade de licenciamento para as transmissões de rádio e, com isso abriu o caminho a indústria.

Esta autorização deu aos fabricantes a faixa do espectro de frequência para o desenvolvimento de produtos tais como: telefones sem fio, fornos de micro-ondas e os rádios wireless para uso em redes de computadores sem a necessidade da utilização de cabos do tipo UTPs.

No ano de 1980, o grupo de trabalho IEEE 802 - _**Institute of Electrical and Electronics Engineers**_, responsável pelo desenvolvimento dos padrões de rede de computadores, como exemplo o Ethernet, iniciaram os trabalhos para o desenvolvimento de padrões para redes sem fio e, desta forma, deram uma direção única à indústria para a fabricação de produtos com total interoperabilidade.

O grupo IEEE 802 então, através de várias comissões de trabalho propuseram diversos padrões de comunicação wireless para diferentes tipos de aplicações e, a cada um destes grupos foram designados padrões que iremos descrever agora. São eles:

### IEEE 802.15 – _Wireless Personal Area Network_ – WPAN

Usa a tecnologia Bluetooth para a interconexão de produtos e acessórios de uso pessoal com aplicações de curta distância, por exemplo: mouses, celulares, controle remoto, teclados sem fio e etc.

A rede Bluetooth não deve ser considerada como uma wireless LAN, mas sim como uma tecnologia de rede pessoal, daí o seu nome ser WPAN ou seja, _**Personal Área Network**_.

Operando na frequência de 2,4GHz e com largura de banda de apenas 1Mbps, esta tecnologia utiliza o compartilhamento por divisão de frequência TDMA e com pequeno alcance, de 1 a 10 metros aproximadamente.

Suporta aplicações de dados com velocidade real de até 720Kbps por canal e sua maior desvantagem é concorrer e corromper redes que operam na mesma frequência de 2,4GHz, isto é, redes do padrão IEEE 802.11b, g, n e ac. A figura 1 ilustra esta aplicação.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293457/18295.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293457/18295.jpg)

Figura 1 - Aplicação das Redes WPAN

### IEEE 802.11 – _Wireless LANs_ - WLAN

É o tipo de conexão utilizada em edifícios ou casas para prover a conectividade entre computadores de forma móvel e sem a necessidade dos cabos. No interior dos prédios e casas esta conectividade pode chegar até aproximadamente 100 metros em campo aberto.

Quando se usa a tecnologia WLAN para a conexão entre prédios consegue-se distâncias médias na ordem de alguns quilômetros, chamados de enlaces de rádio digital. Estas distâncias podem ser de até 30 quilômetros, pois o impedimento em questão não são os rádios e nem as antenas, mas a altura das torres de sustentação das antenas devido à curvatura do planeta Terra e a irregularidade da superfície do solo.

A primeira publicação realizada pelo grupo IEEE foi a norma IEEE 802.11 no ano de 1997 que especificava os parâmetros mínimos para os fabricantes desenvolverem seus produtos como placas de rede e rádios, estes rádios foram batizados de _**Access Point**_ ou ponto de acesso e, por final, caracterizando taxas de transferências e demais aspectos técnicos. Nesta primeira modalidade de equipamentos wireless para uso em redes LAN foram definidas as seguintes características:

- Taxa de transferência de 1Mbps e 2Mbps
- Modulação em FHSS – _Frequency Hope Spread Spectrum_ utilizando GFSK
- Modulação em DSSS – _Direct Sequence Spread Spectrum_ utilizando o método de modulação DBPSK e DQPSK.

Nota:  O padrão IEEE 802.11 foi apenas um “rascunho” de inicialização dos trabalhos que logo seriam mudados e aperfeiçoados.

### IEEE 802.11b – _Wireless LANs_ - WLAN

Em setembro de 1999 o IEEE lançou um complemento denominado IEEE 802.11b que trouxe novas e importantes especificações, como aumento das taxas de transferências e melhor segurança nas transmissões dos equipamentos wireless. As principais modificações foram:

- Modulação em DSSS - _Direct Sequence Spread Spectrum_ na frequência de 2,4GHz com taxas de transmissão de 1Mbps, 2Mbps, 5,5Mbps e 11Mbps.
- Novas especificações de modulação em BPSK e QPSK utilizando o CCK que é uma forma de espalhamento espectral, utilizando códigos complementares binários.

### IEEE 802.11a – _Wireless LANs_ – WLAN

Na mesma ocasião da publicação do padrão IEEE 802.11b, foi criado outro grupo de trabalho responsável pelo desenvolvimento de um novo padrão que ficou denominado IEEE 802.11a.

Este grupo por sua vez, criou um novo método de transmissão para a camada física conhecido como OFDM ou _**Orthogonal Frequency Division Multiplexing,**_ utilizando agora a frequência de transmissão de 5GHz dividida em três faixas, a saber:

- Banda baixa que vai de 5,51GHz a 5,25GHz
- Banda média que vai de 5,25GHz a 5,35GHz e
- Banda alta indo de 5,725GHz até 5,825GHz

Também foram especificadas novas velocidades de transmissão de dados: 6, 9, 12, 18, 36, 48 e 54Mbps com taxas obrigatórias de 6, 12 e 24Mbps.

O sistema OFDM utiliza 52 sub portadoras que são moduladas em BPSK/QPSK, 16 _**Quadrature Amplitude Modulations**_ – QAM, ou 64 QAM. (MALBURG, 2004)

Este novo padrão apresenta algumas vantagens em relação ao seu antecessor com um aumento da velocidade de transmissão, que passou de 11Mbps para 54Mbps. Também este novo padrão aloca até 8 canais não sobrepostos contra os apenas 3 canais do padrão IEEE 802.11b, assim numa aplicação com mais de um rádio, esta nova versão poderá suportar mais usuários conectados sem qualquer conflito ou degradação do sinal.

Porém, como tudo não são apenas benefícios, o padrão 802.11a é totalmente incompatível com seu antecessor o padrão 802.11b por utilizar uma frequência diferente na transmissão, 5GHz contra o 2,4GHz.

### IEEE 802.11g – _Wireless LANs_ – WLAN

No ano de 2003 foi publicado o suplemento complementar para um novo padrão, o IEEE 802.11g que especificou novos limites de transmissão de até 54Mbps com portadora operando em 2,4GHz e utilizando a modulação OFDM igualmente como o padrão IEEE 802.11a.

A principal vantagem deste novo padrão foi sem dúvida o aumento da velocidade, que antes era de 11Mbps para o padrão 802.11b para 54Mbps e sua total compatibilidade com o antecessor. O equipamento deste novo padrão tem no seu interior dois moduladores que podem ser alternados, dependendo da velocidade de conexão dos usuários, por exemplo: Quando os equipamentos de usuário que operam em 802.11b se conectam a um rádio 802.11g, sua operação de modulação é realizada em DSSS em taxas de transmissão de 11Mbps. Quando os usuários se conectam com equipamentos 802.11g a modulação passa a ser OFDM, aumentando a taxa de transmissão para 54Mbps, mas isso não pode ser realizado ao mesmo tempo quando temos os dois tipos de usuários conectados.

Neste caso, a modulação que vai permanecer funcionando é o DSSS com velocidade de 11Mbps, e assim, mesmo clientes que tenham placas de rede em 802.11g só conseguirão se comunicar a 11Mbps, pois o Access Point sempre respeitará os clientes de menor velocidade. A tabela 1 resume os três padrões com todas as informações de compatibilidade e velocidade de cada um.

![[Untitled 74.png|Untitled 74.png]]

### IEEE 802.11n – _Wireless LANs_ – WLAN

Tem uma largura de banda até aos 300 Mbps e um alcance médio de 100 metros, operando nas frequências 2,4GHz e 5GHz. Os principais objetivos na criação deste padrão foram:

- O aumento de velocidade e banda para suportar serviços de multimídia como televisão em alta definição HD.
- Ser compatível e ter total interoperabilidade com os padrões e tecnologias anteriores.

É um padrão recente com uma nova tecnologia denominada MIMO _**(multiple input, multiple output)**_ que pode utilizar várias antenas para sua comunicação, sendo que modelos com 4 antenas podem chegar até 600Mbits por segundos.

Os padrões 802.11a e g operam com canais de 22Mhz trabalhando em OFDM, o padrão n pode trabalhar com canais de 40Mhz de banda, permitindo praticamente duplicar as taxas de transferência por canal, onde dois canais sem sobre posição de 22 MHz sejam combinados para formar um único canal de 40 MHz. Desta forma, os canais do padrão 802.11n podem ser configurados como 20MHz ou 40MHz, ou ser configurados para conversão automática. Os canais com conversão automática operando em 40 MHz podem automaticamente retornar para 20MHz quando o ambiente estiver com altos níveis de interferências. Quando _**Acess Point**_ operando em 2,4GHz o uso de canais são poucos, pois, em realidade, só existe 3 canais livres de sobreposição (canais 1, 6 e 11), porém, com AP operando em 5GHz os resultados são bastante satisfatórios.

### IEEE 802.11ac – _Wireless LANs_ – WLAN

O mais recente padrão da família IEEE 802.11 é o de sigla ac que foi desenvolvido trabalhando nos três pilares fundamentais para se conseguir maior velocidade de conexão, são eles o aumento da largura de banda utilizada, a melhoria entre a relação Sinal/Ruído e o aumento da eficiência espectral.

Enquanto os padrões IEEE 802.11 a e g tem uma largura de banda de 22MHz, o seu sucessor, o padrão n já utiliza uma largura de 40MHz e em consequência, o aumento da velocidade de transmissão. O novo padrão ac na sua fase 1 já foi concebido com uma largura de canal de 80MHz e na sua fase 2 que deverá entrar em serviço nos próximos anos a largura será de 160MHz.

Referente a melhoria da largura espectral, o seus antecessores padrão a e g utiliza modulação OFDM com 52 sub portadoras em modo QAM64, já o padrão n também utiliza o OFDM mas agora com 108 sub portadoras e modulação QAM64 com MIMO 4x4, utilizando em até quatro antenas. O novo padrão ac utiliza OFDM também mas com 234 ou 2 x 234 sub portadoras em modulação QAM64 e MIMO 8x8, isso significa que na sua velocidade máxima o equipamento poderá compor de até oito antenas.

O novo padrão pode operar nas duas frequências da banda ISM, 2,4GHz e 5GHz com a diminuição do canal para 40MHz e quando se utilizar da frequência de 5GHz, o canal volta para seus originais 80MHz. Portanto, os equipamentos ac vão operar no padrão n em 2,4GHz e no padrão ac quando conectados em frequência de 5GHz. Quando operando a 5GHz e com a utilização destes novos fatores melhorados, consegue-se velocidades de até 1300Mbits. A figura 2 ilustra as redes WLAN.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293452/18297.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293452/18297.jpg)

Figura 2 - aplicação das redes WLAN

### IEEE 802.16 – Wireless LANs – WiMAX

Em 2001 o IEEE divulgou um novo padrão com a tarefa de prover uma alternativa ao acesso de última milha que hoje em nosso país é suprido por cabos de cobre via xDSL ou _**Cable Modem.**_

Este novo padrão deve ter total interoperabilidade com o padrão 802.11 e seu objetivo principal é prover uma conexão wireless sem linha de visada, ou seja, utilizar antenas que não estão em linha de visibilidade uma da outra, como nos casos de enlace de rádio que necessitam de antenas com visada direta.

Suas especificações mínimas são:

- Banda de frequência 10GHz a 66GHz com _throughput_ de 32Mbps a 134Mbps.
- Limite de frequência a 2GHz até 11GHz – banda não licenciada de 5,8GHz e bandas licenciadas de 2,5GHz e 3,5GHz.
- Taxa de transferência de até 75Mbps

No ano de 2003 o IEEE publicou um adendo chamado IEEE 802.16a, utilizando a banda de frequências de 2GHz a 11GHz que suportará aplicações mais exigentes como banda passante e um alcance maior de até 40Km utilizando as ERB – Estação Rádio Base de telefonia celular.

O WiMAX 802.16a é uma tecnologia de redes MAN – _**Metropolitan Área Network**_, que prevê conectividade em dispositivos fixos ou móveis, o que poderá ser usado por diversos equipamentos móveis como celulares_**, laptops**_ e _**tabletes**_ com perfeita conectividade em taxas muito altas onde existir cobertura de celular.

Para as aplicações fixas, ou seja, fornecimento de conectividade a Internet a empresas e residências o 802.16 WiMAX também poderá ser utilizado fornecendo taxas altas de conexão do tipo DSL ou canais E1 de 2048Kbps. A figura 3 ilustra as redes WiMAX.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293453/18298.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/3/4/293453/18298.jpg)

Figura 3 - Redes WiMAX

### Outros Padrões de Redes Wireless

IEEE 802.11d - Com tecnologia e desenvolvimento para equipamentos não atendidos pelo padrão 802.11, como o mercado industrial.

IEEE 802.11e – Permitirá, quando for concluído seus estudos, a qualidade de serviço por priorização dos pacotes que trafeguem no meio wireless como áudio e vídeo.

IEEE 80211f – Desenvolve protocolos de comunicação entre rádios e _**Access Point.**_

### O Selo WIFI

O selo WIFI foi criado pela _**WI-FI Alliance**_, antiga (WECA – _**Wireless Ethernet Compatibility Alliance)**_ que é uma organização sem fins lucrativos, nascida em 1999 com o objetivo de promover a integração dos fabricantes de produtos de wireless.

Este selo atesta a interoperabilidade entre produtos 802.11 através de uma série de testes realizados por laboratórios independentes, que certifica todos os equipamentos de diversos fabricantes que eles são interoperáveis entre si, isso quer dizer que equipamentos que tenham o selo WIFI poderão se comunicar com outros equipamentos com o mesmo selo, sem nenhum problema com todas as características funcionais determinada pelo padrão em questão. Isso é mais uma garantia da qualidade dos produtos wireless, portanto na hora de adquirir tais produtos, como placas de redes e rádios, exija o selo WIFI. (SANTOS JUNIOR, 2005)

### Revisão:

Os padrões são definidos pelo IEEE que é o Instituto de Engenharia e Elétrica nos Estados Unidos da América e é este instituto que padroniza as redes como é o caso da wireless LAN.

Basicamente temos cinco padrões de redes wireless LAN, a saber:

IEEE 802.11b com frequência de operação em 2,4GHz, velocidade de sinalização de 11Mbps e com 11canais de 22Mhz cada um no Brasil.

IEEE 802.11g com frequência de operação em 2,4GHz, velocidade de sinalização de 54Mbps e com 11canais de 22Mhz cada um no Brasil.

IEEE 802.11a operando em 5GHz, velocidade de 54Mbps e com 12 canais sem interpolação.

IEEE 802.11n com frequência de operação em 2,4GHz, velocidade de sinalização de até 300Mbps e, 11canais de 22Mhz ou 3 canais de 40MHz e a utilização da tecnologia MIMO.

IEEE 802.11ac com frequência de operação em 2,4GHz ou 5GHz, velocidade de sinalização de até 1300Mbps e canalização de 40 ou 80MHz, também utilizando a tecnologia MIMO.