[![](https://ampli-images.s3.amazonaws.com/production/e7025e6f-1cc5-41dc-90e3-510a9935429a/original)](https://ampli-images.s3.amazonaws.com/production/e7025e6f-1cc5-41dc-90e3-510a9935429a/original)

É um protocolo de nível de transporte orientado à conexão utilizado em aplicações que exigem que a totalidade e a integridade dos dados sejam realizadas com garantia de entrega, como na transmissão de um documento, uma mensagem ou uma figura, por exemplo, em formato de arquivo. O serviço de transporte oferece meios para se estabelecer, manter e liberar conexões de transporte entre pares de _hosts_ por meio dos _Services Access Points_ (SAP). De forma geral, o protocolo TCP divide as mensagens vindas da camada de aplicação em segmentos e as encaminha para o host de destino, que a reconstruirá com informações adicionadas no cabeçalho do protocolo. Esse protocolo cuida da confirmação do recebimento da mensagem, estabelece uma conexão fim a fim e escolhe o caminho confiável de transporte da mensagem.

As principais características de um protocolo TCP são:

- Fornece um circuito virtual entre aplicações finais.
- Orientado para conexão.
- Realiza controle de fluxo para garantir a confiabilidade na transmissão.
- Divide as mensagens enviadas em segmentos;
- Utiliza o conceito de janelas deslizantes para segmentação e controle;
- Reagrupa as mensagens no _host_ destino.
- Realiza controle de congestionamento. As aplicações para esse protocolo são para transmissão de dados.

Um segmento TCP é formado por campos de cabeçalho e campo de dados. Os campos de cabeçalho contêm as portas de origem (porta de origem #) e destino da transmissão (porta de destino #), um número de sequência (número de sequência), um número de reconhecimento para verificação de integridade de dados (número de reconhecimento), campos da janela de recepção para o controle de fluxo (URG, ACK, PSH, RST, SYN, FIN), campo de comprimento de cabeçalho, campo de opções para controle em redes de alta velocidade (opções), sinalizadores de reconhecimento (soma de verificação da Internet) e o campo de dados. A figura abaixo mostra a estrutura do segmento TCP.

[![](https://ampli-images.s3.amazonaws.com/production/70f0ea43-244d-4b6b-ba5e-8265181d929d/original)](https://ampli-images.s3.amazonaws.com/production/70f0ea43-244d-4b6b-ba5e-8265181d929d/original)

Estrutura do segmento do TCP. Fonte: Kurose; Ross (2013, p. 172).

O TCP é um protocolo orientado à conexão com garantia de entrega, também chamado de protocolo elástico, utilizado para acesso a sites em formato de hipertexto nos sistemas Web, Internet Banking, correio eletrônico e transferência de dados, por exemplo. Os principais protocolos de aplicação que utilizam esse tipo de transmissão são: HTTP, FTP, SMTP e DNS.