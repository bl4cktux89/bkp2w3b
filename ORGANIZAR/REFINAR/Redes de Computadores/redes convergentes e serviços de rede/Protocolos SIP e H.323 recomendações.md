Protocolo SIP (Session Initiation Protocol)

De modo a  compreender um pouco melhor o funcionamento do sistema VOIP, faz-se necessário abordarmos alguns conceitos básicos sobre os protocolos que regem o funcionamento desse serviço. Por isso, iremos falar sobre o protocolo SIP. Trata de um protocolo simples e modular, estabelecido pelo IETF e descrito na RFC 3261. Esse protocolo descreve como instalar chamadas telefônicas da internet, videoconferências e outras conexões de multimídia.

O SIP é um protocolo simples e foi definido pelo IETF e descrito na RFC 3261, utilizado para chamadas telefônicas da internet, videoconferência e conexões multimídia. O protocolo SIP estabelece sessões de duas maneiras, ligações comuns de telefone e de multidifusão através de um transmissor e vários receptores. Em uma de suas sessões contem áudio, vídeo e dados.

O SIP trabalha na camada de aplicação e funciona sobre o UDP e TCP, tem uma grande variedade de serviços, exemplos dele é a espera de chamadas,  a triagem de chamadas, criptografia e a autenticação.

O SIP é um único módulo, projetado para interoperar bem com aplicações da internet existentes. Por exemplo, ele define números de telefones como URLs, de forma que as páginas da web possam conter esses números, permitindo que um clique em um link inicie uma ligação telefônica (da mesma forma que o esquema mailto permite que um clique sobre um link abra um programa para enviar uma mensagem de correio eletrônico).

O SIP pode estabelecer sessões de duas partes (ligações telefônicas comuns), sessões de várias partes (em que todos podem ouvir e falar) e sessões de multidifusão (com um transmissor e muitos receptores). As sessões podem conter áudio, vídeo ou dados, e os dados são úteis para, por exemplo, a realização de jogos em tempo real com vários participantes. O SIP cuida apenas da configuração, do gerenciamento e do encerramento de sessões. Outros protocolos, como RTP/RTCP, são usados para transporte de dados. O SIP é um protocolo da camada de aplicação e pode funcionar sobre o UDP ou o TCP.

O SIP admite uma grande variedade de serviços, inclusive localização do chamado (que pode não estar em sua máquina local) e determinação dos recursos do chamado, bem como tratamento do mecanismo de configuração e encerramento de chamadas.

O SIP apresenta alguns outros recursos como espera de chamadas, triagem de chamadas, criptografia e autenticação.Na figura abaixo é representada um ligação VOIP com o protocolo SIP.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258949/14804.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/5/8/9/258949/14804.jpg)

Ligação VOIP usando SIP

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/1/3/11347/i28_546.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/1/1/3/11347/i28_546.jpg)

Mensagens de sinalização do protocolo SIP trocadas entre dois usuários..

[**MATERIAL COMPLEMENTAR**](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/3/4/323494/index.html)

Em 1996 o órgão ITU se reuniu com diferentes fabricantes para criar um padrão de equipamentos de telefonia para redes locais que oferecem uma qualidade de serviço não garantido, posteriormente em 1998 o H.323 foi revisado e se tornou a base para o sistema de telefonia e da internet.

Nas recomendações do H.323 ele faz uma referencia em uma grande parte dos protocolos específicos para codificação de voz, configuração de chamadas, sinalização e transporte de dados. Através de um Gateway que se conecta a internet e a rede de telefonia o protocolo H.323 faz a comunicação da internet com a rede de telefonia (PSTN).

H323

Com o propósito de evitar que vários fabricantes criassem sistemas diferenciados, não permitindo assim a interoperabilidade de redes, várias partes interessadas se reuniram sob o patrocínio da ITU para desenvolver padrões. Em 1996, a ITU emitiu a recomendação H.323, intitulada "Visual Telephone Systems and Equipment for Local Area Networks Which Provide a Non-Guaranteed Quality of Service" (ou seja, sistemas e equipamentos de telefonia visual para redes locais que oferecem uma qualidade de serviço não garantida). A recomendação foi revisada em 1998, e essa recomendação H.323 revisada foi a base para os primeiros sistemas amplamente difundidos de telefonia da internet.

A recomendação H.323 é mais uma avaliação da arquitetura de telefonia da internet que um protocolo específico. Ela faz referência a um grande número de protocolos específicos para codificação de voz, configuração de chamadas, sinalização, transporte de dados e outras áreas, em vez de especificar propriamente cada um desses elementos.

O modelo geral é representado na figura logo a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/1/9/241913/8516.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/1/9/241913/8516.jpg)

Terminais H.323 conectados a internet e comunicando-se com telefones ligados a uma rede telefônica de comutação. Kurose, 2010..

No centro há um gateway que conecta a internet à rede de telefonia. Ele se comunica por meio dos protocolos H.323 no lado da Internet e dos protocolos PSTN no lado da rede telefônica. Os dispositivos de comunicação são chamados terminais. Uma LAN pode ter um gatekeeper (guardião) que controla os pontos extremos sob sua jurisdição, denominada zona.