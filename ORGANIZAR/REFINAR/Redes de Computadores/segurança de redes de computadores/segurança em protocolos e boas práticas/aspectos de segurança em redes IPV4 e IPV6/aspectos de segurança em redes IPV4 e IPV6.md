### **Introdução**

O desenvolvimento da arquitetura IPv6 trouxe consigo diversos avanços no quesito segurança em comparação a arquitetura IPv4. Diversas vulnerabilidades foram corrigidas, no entanto, não podemos afirmar que a arquitetura IPv6 é mais segura do que a IPv4.  O correto seria afirmar que a arquitetura IPv6 fornece mecanismos de segurança mais robustos do que o IPv4, já que, por exemplo, possui suporte nativo ao protocolo IPSec.

Apesar de ter suporte nativo, não quer dizer que todos os pacotes que trafegam pelas redes IPv6 são criptografados automaticamente. Isso é completamente errado! Por outro lado, à medida em que o IPv6 for cada vez mais utilizado, provavelmente novas vulnerabilidades serão encontradas.

### NAT IPv4

Existe também a cultura, até certo ponto enraizada, de que o NAT IPv4 é uma solução de segurança. Temos que ter em mente que o NAT, na sua origem, tinha como função proporcionar a tradução endereços privados para públicos e vice-versa, tendo em vista a escassez de endereços IPv4. Mas teve como consequência proporcionar a chamada "proteção por obscuridade", já que toda a rede local é ocultada por um roteador ou firewall de borda, conforme ilustrado na figura que segue (Brito, S. H. B, 2013.

A técnica NAT, portanto, "quebrou" a conectividade fim-a-fim, e é essa uma das principais vantagens da adoção do IPv6, fazendo com que um host de uma rede local A possa se conversar diretamente com outro host da rede local B.

### Convergência IPv4/IPv6 e a segurança

Existem diversas soluções que permitem a convivência de redes IPv4 e IPv4, dentre elas, podemos citar: a pilha dupla, túnel 6over4 e NAT64. No contexto de rede local, a existência de pilha dupla e de tuneis automáticos IPv6 podem levar a grandes riscos à segurança.

Por meio de túneis automáticos, por exemplo TEREDO, as redes IPv4 podem ser alcançadas através da Internet IPv6. Por isso, regras de firewall IPv6 devem ser escritas mesmo que a rede interna esteja rodando IPv4. Além disso, o TCP/IPv6 deve ser desabilitado em todos os hosts.

No entanto, a prática acima vai na contramão da adoção do IPv6. Devemos, hoje, considerar a existência de redes puramente IPv6 (Brito, S. H. B, 2013).

### ICMPv4/v6

No ICMPv4 as mensagens trocadas têm como principal finalidade o diagnóstico do estado da rede e dos hosts. Entretanto, no IPv6, além das mensagens de diagnósticos existentes no IPv4, as mensagens ICMPv6 é parte fundamental do funcionamento da arquitetura. Como exemplo, a descoberta de endereços MACs dos vizinhos IPv6 é feita através de mensagens ICMPv6/NDP (Protocolos de descoberta de vizinhos), enquanto no IPv4 é utilizado o protocolo ARP. As mensagens de descoberta de vizinhança não se restringem apenas a descoberta de endereços MACs, mas também são utilizadas para estabelecer outros tipos de vizinhanças, conforme mostrado na tabela que segue (Brito, S. H. B, 2013).

![[Untitled 92.png|Untitled 92.png]]

O NDP não é um protocolo à parte, ele funciona a partir do protocolo ICMPv6. Além da descoberta de vizinho, como já comentado, o ICMPv6/NDP possuem também as seguintes funcionalidades:

- Descoberta dos parâmetros do enlace;
- Autoconfiguração de endereços (SLAAC);
- Descoberta de roteadores e prefixos de rede;
- Detecção de endereços duplicados (DAD);
- Detecção de atividade do vizinho;
- Redirecionamento de roteadores.

### Ataques ICMPv6/NDP

Muitos dos ataques que exploravam as mensagens ARP, agora, no IPv6, tem como o foco as mensagens ICMPv6/NDP, que, como já comentado, têm muitas outras funcionalidades dentro da arquitetura. Dentre os principais ataques ao IPv6 podemos citar (Cisco Systems, 2020):

- **Ataque à descoberta de vizinhança:** no processo de descoberta de vizinhança são trocadas mensagens do tipo ICMPv6 Tipo 135 - NS e Tipo 136 - NA. Um host que deseja ingressar na rede IPv6 envia mensagens NS para verificar se o seu endereço não está sendo utilizado por outro host na rede com o objetivo de se evitar a duplicidade. Como resposta, o ataque pode enviar mensagens NA informando que aqueles endereços IPv6 informados já estão em uso, impedindo dessa forma, que o host ingresse na rede.
- **Envenenamento de tabela de vizinhança:** Mensagens do tipo ICMP Tipo 136 - NA falsas podem ser enviadas pelo atacante com o objetivo de inundar (flood) a tabela de vizinhança com entradas falsas. Como resultado, ocorrerá inconsistência no encaminhamento dos quadros e o estouro da tabela de vizinhança. Por outro lado, este tipo de falsificação pode levar a interceptação do tráfego por parte do atacante.

**SAIBA MAIS...**

O envenenamento de tabela de vizinhança é semelhante ao ataque de ARP-Spoofing, que consiste no envio em massa de endereços MACs falsos, comprometendo a integridade da tabela ARP. Este ataque também pode estar associado ao ataque conhecido como MAC-flood, podendo ocasionar estouro do limite da tabela de endereços MACs do switch.

- **Falsificação de roteadores e prefixos:** Uma outra funcionalidade exclusiva do IPv6 consiste no anúncio de mensagens ICMPv6 Tipo 134 - RA falsas enviadas por um host fingindo-se ser o roteador da rede. Dessa forma, o ataque passa a ser um dispositivo intermediário na comunicação, técnica conhecida como man-in-the-middle. Além disso, é possível manipular as mensagens RA dos roteadores e zerar o seu tempo de validade, isso levaria a perda dos prefixos de rede por parte dos hosts. Também há a possibilidade de envio de mensagens RA com endereços inexistentes, o que levaria a indisponibilidade.
- **Varredura de endereços e privacidade:** Da mesma forma que ocorre no IPv4 é possível fazer a varredura por meio de um escâner de rede com objetivo de levantar as possíveis vulnerabilidades de um host. No entanto, no IPv6 este processo pode ser extremamente demorando em virtude do seu esquema de endereço. A título de exemplo, se pegarmos uma rede /24 teremos 254 hosts válidos nos quais o escâner deverá varrer. No IPv6 o campo destinado aos hosts é composto por um /64, necessitando de alguns bilhões de anos para varrer completamente este prefixo.

### Mecanismos de defesa

Existem diversos ataques envolvendo a forma de funcionamento da arquitetura IPv6, ao mesmo tempo que existem diversas técnicas e recursos dos equipamentos de rede qu e podem ser utilizadas para reduzir a chance de um ataque. A medida em que o protocolo IPv6 for cada vez mais empregado, novos vulnerabilidades certamente surgirão, assim como novos mecanismos de defesa. Nesta sessão será demonstrado algumas técnicas e recursos que podem ser utilizados em roteadores em switches para mitigação de ataques que envolvem as mensagens ICMPv6/NDP, dentre elas a configuração do RA-Guard e ND-Inspection em switches (Brito, S. H. B, 2013).

- **RA-Guard:** O RA-Guard é um recurso disponível em alguns switches estabelecido pela RFC-6105 utilizado para mitigar o ataque de falsificação de roteadores e prefixos de rede IPv6. Neste recurso, o administrador pode configurar as interfaces que podem encaminhar anúncio de roteadores (RA), ou seja, as interfaces com roteadores legítimos são configuradas como confiáveis e as demais são automaticamente enquadradas como não confiáveis. Para exemplificar esta funcionalidade será adotada a topologia que segue.

![[Untitled 1 56.png|Untitled 1 56.png]]

Fonte: Brito, S. H. B. IPv6: O novo Protocolo da Internet. São Paulo: Novatec, 2013 (Adaptado).

`1.` `# Configuração RA-Guard no switch #` `2.`   `3.` `Switch(config)# ipv6 nd raguard policy RA-GUARD-ROUTER` `4.` `Switch(config-ra-guard)# device role router` `5.` `Switch(config-ra-guard)# trusted-port` `6.` `Switch(config-ra-guard)# exit` `7.` `Switch(config)# ipv6 nd raguard policy RA-GUARD-HOST` `8.` `Switch(config-ra-guard)# device role host` `9.` `Switch(config-ra-guard)# exit` `10.` `Switch(config)# interface g0/1` `11.` `Switch(config-if)# ipv6 nd raguard attach-policy RA-GUARD-ROUTER` `12.` `Switch(config-if)# int range f0/1 - 24` `13.` `Switch(config-if-range)# ipv6 nd raguard attach-policy RA-GUARD-HOST`

O princípio de funcionamento do RA-Guard é semelhante ao recurso DHCP-snooping utilizado em redes IPv4 para bloquear as mensagens DHCP-offer de interfaces não confiáveis, desativando-a em caso de violação, enquanto as interfaces confiáveis são aqueles onde estão localizados os servidores DHCP.

- **ND-Inspection:** O recurso ND-Inspection faz com que o switch aprenda dinamicamente os endereços MAC e IPv6 associados as suas respectivas interfaces e armazena em uma tabela confiável de vizinha. Com isso, o switch sabe quando descartar uma mensagem NA inválida. Se os endereços MAC e IPv6 da mensagem RA não correspondem a tabela de vizinhança o quadro, então, é descartado. Esta técnica pode ser utilizada para evitar ataques de negação de serviço que utilizam como base as mensagens utilizadas para detecção de duplicidade de endereços IPv6.A topologia anterior será utilizada para aplicar a configuração do recurso ND-Inspection. No exemplo abaixo, a configuração força switch a sempre verificar as mensagens NA nas interfaces f0/1 a f0/24.

`1.` `Switch(config)# ipv6 nd inspection policy NOME` `2.` `Switch(config-nd-inspection)# drop unsecure` `3.` `Switch(config-nd-inspection)# exit` `4.` `Switch(config)# int range f0/1 - 24` `5.` `Switch(config-if-range)# ipv6 nd inspection attach-policy policy NOME`

**SAIBA MAIS...**

Existe um recurso semelhante ao ND-Inspection IPv6 para switches que rodam em redes IPv4, ele é conhecido como DAI (Inspeção dinâmica do ARP), criando uma tabela de associação de endereços MACs e IPv4, e verificando o cabeçalho do pacote antes de encaminhá-lo. Para saber mais como configurar essa função, consulte o link que segue: [**https://www.cisco.com/c/pt_br/support/docs/switches/catalyst-3750-series-switches/72846-layer2-secftrs-catl3fixed.html**](https://www.cisco.com/c/pt_br/support/docs/switches/catalyst-3750-series-switches/72846-layer2-secftrs-catl3fixed.html)