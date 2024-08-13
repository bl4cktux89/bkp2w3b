# Etapas da Configuração Básica de um Roteador

As tarefas a seguir devem ser concluídas ao configurar as configurações iniciais em um roteador.

1. Configurar o nome do dispositivo.

```Plain
Router(config)\#hostnamehostname
```

2. Proteger o modo EXEC privilegiado.

```Plain
Router(config)\#enable secretpassword
```

3. Proteger o modo EXEC usuário.

```Plain
Router(config)\#line console 0
Router(config-line)\#passwordpassword
Router(config-line)\#login
```

4. Proteger o acesso remoto Telnet/SSH

```Plain
Router(config-line)\#line vty 0 4
Router(config-line)\#passwordpassword
Router(config-line)\#login
Router(config-line)\#transport input {ssh |telnet}
```

5. Proteger todas as senhas do arquivo de configuração.

```Plain
Router(config-line)\#exit
Router(config)\#service password-encryption
```

6. Apresentar a notificação legal.

```Plain
Router(config)\#banner motddelimiter message delimiter
```

7. Salvar a configuração.

```Plain
Router(config)\#end
Router\#copy running-config startup-config
```

# Exemplo de configuração básica do roteador

Neste exemplo, o roteador R1 no diagrama de topologia será configurado com as configurações iniciais.

Para configurar o nome do dispositivo para R1, use os seguintes comandos.

```Plain
Router> enable 
Router# configure terminal 
Enter configuration commands, one per line.
End with CNTL/Z.
Router(config)# hostname R1 
R1(config)#
```

**Observação:** Observe como o prompt do roteador agora exibe o nome do host do roteador.

Todo o acesso ao roteador deve ser protegido. O modo EXEC privilegiado fornece ao usuário acesso completo ao dispositivo e sua configuração. Portanto, é o modo mais importante para proteger.

Os comandos a seguir protegem o modo EXEC privilegiado e o modo EXEC do usuário, habilitam o acesso remoto Telnet e SSH e criptografam todas as senhas de texto simples (ou seja, EXEC do usuário e linha VTY).

```Plain
R1(config)# enable secret class 
R1(config)#
R1(config)# line console 0 
R1(config-line)# password cisco 
R1(config-line)# Login 
R1(config-line)# exit 
R1(config)#
R1(config)# line vty 0 4 
R1(config-line)# password cisco 
R1(config-line)# Login 
R1(config-line)# transport input ssh telnet 
R1(config-line)# exit 
R1(config)#
R1(config)# service password-encryption 
R1(config)#
```

A notificação legal avisa os usuários de que o dispositivo só deve ser acessado por usuários permitidos. A notificação legal é configurada da seguinte forma.

```Plain
R1(config)# banner motd #
Digite a mensagem de texto. Termine com uma nova linha e o #
*********************************************** AVISO: O acesso não autorizado é proibido!***********************************************#
R1(config)#
```

Se os comandos anteriores foram configurados e o roteador perdeu energia acidentalmente, todos os comandos configurados seriam perdidos. Por esse motivo, é importante salvar a configuração quando as alterações são implementadas. O comando a seguir salva a configuração na NVRAM.

```Plain
R1# copy running-config startup-config
Destination filename [startup-config]? 
Building configuration...
[OK]
R1#
```

# Exemplo de configuração de interfaces de roteador

Neste exemplo, as interfaces diretamente conectadas de R1 no diagrama de topologia serão ativadas.

Para configurar as interfaces em R1, use os seguintes comandos.

```Plain
R1> enable
R1# configure terminal
Enter configuration commands, one per line.
End with CNTL/Z.
R1(config)# interface gigabitEthernet 0/0/0
R1(config-if)# description Link to LAN
R1(config-if)# ip address 192.168.10.1 255.255.255.0
R1(config-if)# ipv6 address 2001:db8:acad:10::1/64
R1(config-if)# no shutdown
R1(config-if)# exit
R1(config)#
*Aug  1 01:43:53.435: %LINK-3-UPDOWN: Interface GigabitEthernet0/0/0, changed state to down
*Aug  1 01:43:56.447: %LINK-3-UPDOWN: Interface GigabitEthernet0/0/0, changed state to up
*Aug  1 01:43:57.447: %LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0/0, changed state to up
R1(config)#
R1(config)#
R1(config)# interface gigabitEthernet 0/0/1
R1(config-if)# description Link to R2
R1(config-if)# ip address 209.165.200.225 255.255.255.252
R1(config-if)# ipv6 address 2001:db8:feed:224::1/64
R1(config-if)# no shutdown
R1(config-if)# exit
R1(config)#
*Aug  1 01:46:29.170: %LINK-3-UPDOWN: Interface GigabitEthernet0/0/1, changed state to down
*Aug  1 01:46:32.171: %LINK-3-UPDOWN: Interface GigabitEthernet0/0/1, changed state to up
*Aug  1 01:46:33.171: %LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0/1, changed state to up
R1(config)#
```

# Verificação da Configuração de uma Interface

Há vários comandos que podem ser usados para verificar a configuração de uma interface. O mais útil deles é o comandos **show ip interface brief** e **show ipv6 interface brief** , como mostrado no exemplo.

```Plain
R1#  show ip interface brief
Interface IP-Address OK? Method Status Protocol 
GigabitEthernet0/0/0 192.168.10.1 YES manual up up 
Gigabitethernet0/0/1 209.165.200.225 SIM manual up 
Vlan1 unassigned YES unset administratively down down 
R1#  show ipv6 interface brief
GigabitEthernet0/0/0 [up/up]
    FE80::201:C9FF:FE89:4501
    2001:DB8:ACAD:10::1
GigabitEthernet0/0/1 [up/up]
    FE80::201:C9FF:FE89:4502
    2001:DB8:FEED:224::1
Vlan1 [administratively down/down]
    unassigned 
R1#
```

10.2.4

# Comandos de Verificação de Configuração

A tabela resume os comandos **show** mais populares usados para verificar a configuração da interface.

|   |   |
|---|---|
|Comandos|Descrição|
|`**show ip interface brief show ipv6 interface brief**`|A saída exibe todas as interfaces, seus endereços IP e seus status atual. As interfaces configuradas e conectadas devem exibir uma Status de “up” e Protocolo de “up”. Qualquer outra coisa indicaria um problema com a configuração ou O cabeamento.|
|`**show ip route**``**show ipv6 route**`|Exibe o conteúdo das tabelas de roteamento IP armazenadas na RAM.|
|`**show interfaces**`|Exibe estatísticas para todas as interfaces no dispositivo. No entanto, este exibirá apenas as informações de endereçamento IPv4.|
|`**show ip interfaces**`|Exibe as estatísticas do IPv4 para todas as interfaces em um roteador.|
|`**show ipv6 interface**`|Exibe as estatísticas do IPv6 para todas as interfaces em um roteador.|

```Plain
R1(config)\#service password-encryption
R1(config)\#security passwords min-length 8
R1(config)\#login block-for 120 attempts 3 within 60
R1(config)\#line vty 0 4
R1(config-line)\#password cisco123
R1(config-line)\#exec-timeout 5 30
R1(config-line)\#transport input ssh
R1(config-line)\#end
R1#
R1\#show running-config | section line vty
line vty 0 4
 password 7 094F471A1A0A
 exec-timeout 5 30
 login
 transport input ssh
R1#
```

```Plain
Router\#configure terminal
Router(config)\#hostname R1
R1(config)\#ip domain name span.com
R1(config)\#crypto key generate rsa general-keys modulus 1024
The name for the keys will be: Rl.span.com % The key modulus size is 1024 bits
% Generating 1024 bit RSA keys, keys will be non-exportable...[OK]
Dec 13 16:19:12.079: %SSH-5-ENABLED: SSH 1.99 has been enabled
R1(config)#
R1(config)\#username Bob secret cisco
R1(config)\#line vty 0 4
R1(config-line)\#login local
R1(config-line)\#transport input ssh
R1(config-line)\#exit
R1(config)#
```

Os roteadores e switches Cisco começam com uma lista de serviços ativos que podem ou não ser necessários em sua rede. Desative todos os serviços não utilizados para preservar os recursos do sistema, como ciclos de CPU e RAM, e impedir que os atores ameaçadores explorem esses serviços. O tipo de serviços que estão ativados por padrão varia dependendo da versão do IOS. Por exemplo, o IOS-XE normalmente terá apenas portas HTTPS e DHCP abertas. Você pode verificar isso com o comando **show ip ports all**, como mostrado no exemplo.

`Router#` `**show ip ports all**` `Proto Local Address Foreign Address State PID/Program Name TCB Local Address Foreign Address (state) tcp :::443 :::* LISTEN 309/[IOS]HTTP CORE tcp *:443 *:* LISTEN 309/[IOS]HTTP CORE udp *:67 0.0.0.0:0 387/[IOS]DHCPD Receive Router#`

As versões do IOS anteriores ao IOS-XE usam o **show control-plane host open-ports** comando. Mencionamos esse comando porque você pode vê-lo em dispositivos mais antigos. A saída é semelhante. No entanto, observe que este roteador mais antigo tem um servidor HTTP inseguro e Telnet em execução. Ambos os serviços devem ser desativados. Como mostrado no exemplo, desative HTTP com o comando de configuração **no ip http server** global. Desative o Telnet especificando apenas SSH no comando de configuração de linha, **transport input ssh**.

`Router#` `**show control-plane host open-ports**` `Active internet connections (servers and established) Prot Local Address Foreign Address Service State tcp *:23 *:0 Telnet LISTEN tcp *:80 *:0 HTTP CORE LISTEN udp *:67 *:0 DHCPD Receive LISTEN Router# configure terminal Router(config)#` `**no ip http server**` `Router(config)#` `**line vty 0 15**` `Router(config-line)#` `**transport input ssh**`

# IOS Ping Indicators

|   |   |
|---|---|
|Elemento|Descrição|
|**!**|• O ponto de exclamação indica o recebimento bem-sucedido de uma resposta de eco.  <br>•  <br>Ele valida uma conexão de Camada 3 entre origem e destino.|
|**.**|• Um período significa que o tempo expirou esperando por uma mensagem de resposta de eco.  <br>•  <br>Isso indica que ocorreu um problema de conectividade em algum lugar ao longo do caminho.|
|**U**|• **U maiúscula** indica um roteador ao longo do caminho respondeu com um destino ICMP Tipo 3 “ inacessível” mensagem de erro.  <br>•  <br>Possíveis razões incluem o roteador não sabe a direção para a rede de destino ou não foi possível localizar o host no Rede de destino.|

**Observação:** Outras possíveis respostas de ping incluem Q, M,? , ou &. No entanto, o significado destes estão fora do escopo para este módulo.

# Abordagens de solução de problemas básica

Nos dois tópicos anteriores, você aprendeu sobre alguns utilitários e comandos que podem ser usados para ajudar a identificar áreas problemáticas em sua rede. Esta é uma parte importante da solução de problemas. Existem várias maneiras de solucionar um problema de rede. Este tópico detalha um processo estruturado de solução de problemas que pode ajudá-lo a se tornar um administrador de rede melhor. Ele também fornece mais alguns comandos para ajudá-lo a resolver problemas. Os problemas de rede podem ser simples ou complexos e podem resultar de uma combinação de problemas de hardware, software e conectividade. Os técnicos precisam conseguir analisar o problema e identificar a causa do erro para poderem resolver a falha na rede. Esse processo é chamado de solução de problemas.

Uma metodologia comum e eficiente de solução de problemas é baseada no método científico.

A tabela mostra as seis principais etapas do processo de solução de problemas.

**Etapa 1. Identificar o Problema**

- Este é o primeiro passo no processo de solução de problemas.
- Embora as ferramentas possam ser usadas nesta etapa, uma conversa com o usuário é normalmente muito útil

**Etapa 2. Estabelecer uma teoria de causas prováveis**

- Depois que o problema é identificado, tente estabelecer uma teoria de causas prováveis.
- Essa etapa geralmente gera mais do que algumas causas prováveis para o problema.

**Etapa 3. Testar a Teoria para Determinar a Causa**

- De acordo com as causas prováveis, teste suas teorias para determinar qual delas uma é a causa do problema.
- Um técnico geralmente aplica um procedimento rápido para testar e verificar se resolve o problema.
- Se um procedimento rápido não corrigir o problema, pode ser necessário pesquise mais o problema para estabelecer a causa exata.

**Etapa 4. Estabelecer um plano de ação e implementar a solução**

- Depois de determinar a causa exata do problema, estabeleça um Plano de Ação para Resolver o Problema e Implementar a Solução.

**Etapa 5. Verifique a solução e implemente medidas preventivas**

- Depois de corrigir o problema, verifique a funcionalidade completa.
- Se aplicável, implemente medidas preventivas.

**Etapa 6. Documentar Descobertas, Ações e Resultados**

- Na última etapa do processo de solução de problemas, documente descobertas, ações e resultados.
- Essa documentação será muito importante para referência futura.

# O comando de debug

Os processos, protocolos, mecanismos e eventos do SO geram mensagens para comunicar seu status. Essas mensagens podem apresentar informações valiosas ao solucionar problemas ou verificar as operações do sistema. O comando IOS **debug**permite que o administrador exiba essas mensagens em tempo real para análise. É uma ferramenta muito importante para monitorar eventos em um dispositivo Cisco IOS.

Todos **debug** os comandos são inseridos no modo EXEC privilegiado. O Cisco IOS permite restringir a saída para incluir **debug**apenas o recurso ou subfuncionalidade relevante. Isso é importante porque a depuração da saída recebe alta prioridade no processo da CPU e pode travar o sistema. Por esse motivo, use **debug** comandos apenas para solucionar problemas específicos.

Por exemplo, para monitorar o status das mensagens ICMP em um roteador Cisco, use **debug ip icmp**, conforme mostrado no exemplo.

`R1#` `**debug ip icmp**` `ICMP packet debugging is on R1# R1#` `**ping 10.1.1.1**` `Type escape sequence to abort. Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds: !!!!! Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/2 ms R1# *Aug 20 14:18:59.605: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0 *Aug 20 14:18:59.606: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0 *Aug 20 14:18:59.608: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0 *Aug 20 14:18:59.609: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0 *Aug 20 14:18:59.611: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0 R1#`

Para listar uma breve descrição de todas as opções de comando de depuração, use o comando **debug ?** no modo EXEC privilegiado na linha de comando.

Para desativar um recurso de depuração específico, adicione **no** a palavra-chave na frente do **debug** comando:

`Router#` `**no debug ip icmp**`

Como alternativa, você pode inserir o **undebug** formato do comando no modo EXEC privilegiado:

`Router#` `**undebug ip icmp**`

Para desativar todos os comandos de depuração ativos de uma só vez, use o comando: **undebug all**

`Router#` `**undebug all**`

Seja cauteloso usando algum comando **debug**. Comandos como **debug all** e **debug ip packet** geram uma quantidade substancial de saída e podem usar uma grande parte dos recursos do sistema. O roteador pode ficar tão ocupado exibindo **debug** mensagens que não teria capacidade de processamento suficiente para executar suas funções de rede ou até ouvir comandos para desativar a depuração. Por esse motivo, o uso dessas opções de comando não é recomendável e deve ser evitado.

# O Comando terminal monitor

As conexões para conceder acesso à interface da linha de comandos do IOS podem ser estabelecidas das seguintes maneiras:

- **Localmente** - As conexões locais (ou seja, a conexão do console) requerem acesso físico à porta do console do roteador ou do switch usando um cabo de sobreposição.
- **Remotamente** - As conexões remotas exigem o uso de Telnet ou SSH para estabelecer uma conexão com um dispositivo configurado por IP.

Determinadas mensagens IOS são exibidas automaticamente em uma conexão de console, mas não em uma conexão remota. Por exemplo, a **debug** saída é exibida por padrão em conexões de console. No entanto, a **debug** saída não é exibida automaticamente em conexões remotas. Isso ocorre porque as **debug** mensagens são mensagens de log que são impedidos de serem exibidas em linhas vty.

Na saída a seguir, por exemplo, o usuário estabeleceu uma conexão remota usando Telnet de R2 para R1. O usuário então emitiu ocomando. **debug ip icmp** . No entanto, o comando falhou ao exibir a **debug** saída.

`R2#` `**telnet 209.165.200.225**` `Trying 209.165.200.225 ... Open Authorized access only! User Access Verification Password: R1>` `**enable**` `Password: R1#` `**debug ip icmp**` `ICMP packet debugging is on R1#` `**ping 10.1.1.1**` `Type escape sequence to abort. Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds: !!!!! Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/2 ms R1# ! No debug output displayed>`

Para exibir mensagens de log em um terminal (console virtual), use o comando **terminal monitor** no modo EXEC privilegiado. Para parar de registrar mensagens em um terminal, use o comando **terminal no monitor** no modo EXEC privilegiado.

Por exemplo, observe como o **terminal monitor** comando foi inserido e o **ping** comando exibe a **debug** saída.

`R1#` `**terminal monitor**` `R1#` `**ping 10.1.1.1**` `Type escape sequence to abort. Sending 5, 100-byte ICMP Echos to 10.1.1.1, timeout is 2 seconds: !!!!! Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/2 ms R1# *Aug 20 16:03:49.735: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0 **Aug 20 16:03:49.737: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0 **Aug 20 16:03:49.738: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0 **Aug 20 16:03:49.740: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0 **Aug 20 16:03:49.741: ICMP: echo reply rcvd, src 10.1.1.1, dst 209.165.200.225,topology BASE, dscp 0 topoid 0 R1#` `**no debug ip icmp**` `ICMP packet debugging is off R1#`

**Observação**: A intenção do comando **debug** é capturar a saída imediata de um retorno de um processo (comando na memória), por um curto período de tempo (ou seja, alguns segundos a um minuto ou mais). Desative sempre **debug** quando não for necessário.