**Aspectos gerais de um AutoQoS VoIP****para roteadores**

O AutoQoS é um aspecto encontrado em roteadores e switches Cisco que permite a você configurar um dispositivo para QoS somente com alguns comandos básicos de QoS. O melhor de tudo é que você **não** precisa conhecer tudo sobre aspectos QoS para poder trabalhar com AutoQoS.

O destaque para uma configuração com AutoQoS é que você precisa apenas configurar uma ou duas linhas de comando, e o AutoQoS realiza o resto.

Para se ter uma ideia do que o AutoQoS faz, considere que um roteador com AutoQoS poderá classificar pacotes em três classes de serviços:

- Voice Payload (carga de voz)
- Voice Signaling (sinalização de voz)
- Outros tipos de tráfegos

Antes de iniciar a configuração do AutoQoS VoIP, é recomendado fazer uma leitura no guia de configuração do IOS 12.3 da Cisco, versão compatível com esse recurso.

**Configurando um AutoQoS VoIP****para roteadores**

Algumas observações importantes para a configuração de um AutoQoS:

- AutoQoS requer o processo CEF(Cisco Express Forwarding) habilitado primeiro.
- AutoQoS não pode ser usado se uma interface já estiver configurada com um "service-policy".
- Pelo fato do AutoQoS VoIP reprogramar a largura de banda configurada previamente, os roteadores devem estar configurados com as larguras de bandas corretas em cada interface antes de iniciar o AutoQoS.
- Suporta apenas subinterfaces ponto a ponto com interfaces Frame-Relay.
- Dá suporte aos links de dados HDLC, PPP, Frame Relay e ATM.

Na tabela 1, a seguir, são demonstrados os principais comandos AutoQoS e suas sintaxes:

![[Screenshot_20220207_230044.png]]

Seguem as linhas gerais de configuração, como exemplo, utilizado nesse desenho:

`1.` `R3\#show running-config` `2.` `! portions omitted for brevity` `3.` `ip cef` `4.` `!` `5.` `interface serial0/1` `6.` `ip address 192.168.12.3 255.255.255.0` `7.` `encapsulation ppp` `8.` `!` `9.` `R3\#configure terminal` `10.` `Enter configuration commands, one per line. End with CNTL/Z.` `11.` `R3(config)\#int s 0/1` `12.` `R3(config-if)\#auto qos voip` `13.` `R3(config-if)\#end` `14.` `R3#` `15.` `R3#show int s 0/1` `16.` `serial0/1 is up, line protocol is up` `17.` `Hardware is PowerQUICC Serial` `18.` `Internet address is 192.168.12.3/24` `19.` `MTU 1500 bytes, BW 1544 Kbit, DLY 20000 usec,` `20.` `reliability 255/255, txload 1/255, rxload 1/255`

Nesse exemplo, a configuração já usa CEF, por meio do ip cef command. Entretanto, a interface serial 0/1 não possui um comando service-policy. Porém o comando "auto qos voip" habilitou o serviço na interface.

Na próxima sequência de comandos, é demonstrado por meio de dois comandos "show" a lista de novas configurações geradas pelo AutoQoS VoIP.

`1.` `R3\#show auto qos` `2.` `!` `3.` `! First ACL matches Voice payload, second match Voice signaling` `4.` `!` `5.` `ip access-list extended AutoQoS-VoIP-RTCP` `6.` `permit udp any any range 16384 32767` `7.` `ip access-list extended AutoQoS-VoIP-Control` `8.` `permit tcp any any eq 1720` `9.` `permit tcp any any range 11000 11999` `10.` `permit udp any any eq 2427` `11.` `permit tcp any any eq 2428` `12.` `permit tcp any any range 2000 2002` `13.` `permit udp any any eq 1719` `14.` `permit udp any any eq 5060` `15.` `!` `16.` `! Next class-map matches voice payload` `17.` `!` `18.` `class-map match-any AutoQoS-VoIP-RTP-UnTrust` `19.` `match protocol rtp audio` `20.` `match access-group name AutoQoS-VoIP-RTCP` `21.` `!` `22.` `! Next class-map matches voice control traffic` `23.` `!` `24.` `class-map match-any AutoQoS-VoIP-Control-UnTrust` `25.` `match access-group name AutoQoS-VoIP-Control` `26.` `!` `27.` `! This one matches all non-voice that was already` `28.` `marked like voice` `29.` `!` `30.` `class-map match-any AutoQoS-VoIP-Remark` `31.` `match ip dscp ef` `32.` `match ip dscp cs3` `33.` `match ip dscp af31` `34.` `!` `35.` `! Policy-map performs low latency queuing for voice` `36.` `payload, CBWFQ for` `37.` `! Voice signaling, re-marks non-voice packets that` `38.` `are marked like voice,` `39.` `! and queues all non-voice in class-default.` `40.` `!` `41.` `policy-map AutoQoS-Policy-UnTrust` `42.` `class AutoQoS-VoIP-RTP-UnTrust` `43.` `priority percent 70` `44.` `set dscp ef` `45.` `class AutoQoS-VoIP-Control-UnTrust` `46.` `bandwidth percent 5` `47.` `set dscp af31` `48.` `class AutoQoS-VoIP-Remark` `49.` `set dscp default` `50.` `class class-default` `51.` `fair-queue` `52.`   `53.` `Serial0/1 -` `54.` `!` `55.` `interface Serial0/1` `56.` `service-policy output AutoQoS-Policy-UnTrust` `57.` `!` `58.` `! Sends rmon events for packet drops for voice to` `59.` `the SNMP manager` `60.` `!` `61.` `rmon event 33333 log trap AutoQoS description` `62.` `"AutoQoS SNMP traps for Voice Dr` `63.` `ops" owner AutoQoS` `64.` `rmon alarm 33333` `65.` `cbQosCMDropBitRate.1161.1163 30 absolute` `66.` `rising-threshold 1 3` `67.` `3333 falling-threshold 0 owner AutoQoS` `68.` `R3#show auto qos int s 0/1` `69.`   `70.` `Serial0/1 -` `71.` `!` `72.` `interface Serial0/1` `73.` `service-policy output AutoQoS-Policy-UnTrust`

**Considerações finais**

Por meio dos comandos _**"show auto qos"**_, _**"show running-config"**_ e _**"show auto qos interface serial0/1"**_ é possível visualizar as configurações que foram construídas. O intuito dessa aula **não** era fazer você, caro aluno, construir o circuito, mas sim, evidenciar um exemplo de rede configurada com AutoQoS, porém, recomendamos que você tente construir esse circuito no packet tracer. Os comandos que irá utilizar, são conseguidos facilmente pelas respostas dadas acima, quando utilizados os comandos "show". Boa sorte!