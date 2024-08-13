[![](https://ampli-images.s3.amazonaws.com/production/b91aa11a-1c98-4346-a5dd-c0ac673e0a75/original)](https://ampli-images.s3.amazonaws.com/production/b91aa11a-1c98-4346-a5dd-c0ac673e0a75/original)

Quando se aborda serviços oferecidos pelos protocolos de redes, uma análise de protocolos pode ser vista como essencial. Em redes de computadores, são oferecidos serviços orientados à conexão e serviços não orientados à conexão.

Serviços orientados à conexão são aqueles que necessitam de garantia de entrega dos dados. O protocolo de nível de transporte que realiza esse tipo de serviço é o TCP, e os protocolos de nível de aplicação que utilizam esse tipo de serviço são o HTTP, FTP, Telnet e SMTP. Esses protocolos são utilizados por aplicações que transmitem dados como arquivos, imagens, textos e que precisam ter garantia de entrega para completar a transmissão.

Um exemplo de serviço orientado à conexão é o _Internet Banking_, em que, para finalizar uma transação bancária, é necessário que a entrega da totalidade dos dados seja concluída.

Outro tipo de serviço em redes de computadores é o não orientado à conexão, em que a rapidez para transmissão de dados é mais relevante do que a entrega na totalidade dos dados. Esse serviço, por sua vez, transporta dados sem a confiabilidade entre os _hosts_ da rede.

O protocolo de camada de transporte que realiza esse tipo de comunicação é o User _Datagram Protocol_ (UDP), e alguns exemplos de protocolos de nível de aplicação que utilizam esse serviço são: _Dynamic Host Control Protocol_ (DHCP), D_omain Name System_ (DNS), S_imple Network Management Protocol_ (SNMP) e _Network File System_ (NFS). Esse tipo de serviço é utilizado em aplicações de _streamings_ de áudio e vídeo, em que a perda de um ou mais dados não interfere com grande impacto na comunicação. Esse tipo de serviço é comum em sistemas de transmissão de _streaming_ de áudio e vídeo ou, ainda, em uma ligação pelo WhatsApp, por exemplo, em que ocorre a degradação do serviço, mas os pacotes não são retransmitidos.

Para melhor entendimento, apresentaremos, a seguir, uma comparação entre as estruturas do modelo de referência ISO/OSI e TCP/IP. A partir dela, podemos observar que existe apenas uma reorganização conceitual dos níveis de protocolos e nomenclatura, que se referem, na prática, ao mesmo contexto.

[![](https://ampli-images.s3.amazonaws.com/production/f63029db-d7c1-411c-820e-296261da9615/original)](https://ampli-images.s3.amazonaws.com/production/f63029db-d7c1-411c-820e-296261da9615/original)

Modelos ISO/OSI e TCP/IP. Fonte: elaborado pelo autor.

______

**🔁Assimile**

O modelo de referência ISO/OSI e a arquitetura (conjunto de protocolos) TCP/IP são referenciais que buscam organizar os protocolos que executam os serviços de transmissão e interpretação de dados em um sistema distribuído em redes de computadores. O modelo ISO/OSI é considerado um modelo referencial desenvolvido no início das tecnologias de rede; já a arquitetura de protocolos TCP/IP é considerada um conjunto de protocolos que representa, na prática, a distribuição dos protocolos utilizados, na atualidade, em redes de computadores e na internet.