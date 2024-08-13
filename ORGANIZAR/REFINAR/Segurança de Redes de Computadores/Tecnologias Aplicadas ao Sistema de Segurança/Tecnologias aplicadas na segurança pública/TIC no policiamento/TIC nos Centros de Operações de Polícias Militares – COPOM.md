[![](https://ampli-images.s3.amazonaws.com/production/f22fd539-d0a2-422a-9332-32fca07893b0/original)](https://ampli-images.s3.amazonaws.com/production/f22fd539-d0a2-422a-9332-32fca07893b0/original)

**COPOM** é a sigla dos Centros de Operação da Polícia Militar, que são localizados em cada cidade com presença da Polícia Militar e podem ser desde bem modestos: uma linha telefônica recebendo chamados da população, operada por um policial ou escrivão com acesso a rádio para coordenar ações com outros policiais, delegados e delegacias de cidades vizinhas; até centros dedicados de atendimento e coordenação de ações policiais, com centenas de policiais operando equipamentos de última geração de comunicação e processamento, e coordenando ações em terra e ar (helicópteros da polícia).

O COPOM é, segundo Lima (2004), um portal de acesso ao balcão de serviços da Polícia Militar, serviços esses que são requisitados pelo estado e ao mesmo tempo são dever do Estado ao cidadão. Ele depende de informações para habilitar seus administradores a tomarem decisões durante ocorrências de segurança (crimes em andamento ou recém-ocorridos, acidentes no âmbito de ação da polícia, desastres naturais e que tais).

Esta necessidade de informações, aliada à necessidade de comunicação plena com os policiais de campo, torna fundamental a disponibilização de uma infraestrutura de TIC que atenda as demandas de uma sociedade que clama por mais segurança.

Almeida (2014) estabelece uma arquitetura otimizada para centros de monitoração, arquitetura esta adotada pelo COPOM da Polícia Militar do Estado de São Paulo. A figura a seguir estabelece esta arquitetura:

[![](https://ampli-images.s3.amazonaws.com/production/60aba350-186a-4fd2-9e77-2e86b315063e/original)](https://ampli-images.s3.amazonaws.com/production/60aba350-186a-4fd2-9e77-2e86b315063e/original)

Arquitetura de um centro de Monitoração. Fonte: Instituto CFTV.

De acordo com a arquitetura estabelecida na figura apresentada, temos:

**Central de Monitoramento**

- servidores rodando VMS (_Virtual Machine System_, ou Sistema de Maquina Virtual), criando máquinas virtuais em cada cliente (ou seja, em cada computador sendo operado para o atendimento de emergências);
- NVRs (_Network Video Recorders_, ou gravadores de vídeo em rede), sistemas de gravação do _feed_ de vídeos enviado pelos policiais, viaturas e helicópteros em campo;
- Monitores – instalados nas mesas dos operadores e em um painel de controle do tipo video _wall_.

**Campo (conectado à central de monitoramento por meio de redes locais, redes de longa distância ou pela Internet)**

- sistema analógico de comunicação;
- sistema IP de vídeo;
- sistema IP de comunicação;
- sistema IP de mensagens escritas.

Um exemplo de como esta arquitetura de TICs pode ser implantada pode ser visto no COPOM da Polícia Militar do Estado de São Paulo, como nos mostra novamente Almeida (2014), na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/ccdd22ea-2702-46b7-a8c4-10b99cab24fa/original)](https://ampli-images.s3.amazonaws.com/production/ccdd22ea-2702-46b7-a8c4-10b99cab24fa/original)

Instalação de monitoração do COPOM, PMESP. Fonte: Instituto CFTV.

______

**➕** **Pesquise mais**[Clique aqui](https://www.youtube.com/watch?v=-wUHM0RGR3k) para assistir a esse excelente vídeo de demonstração feito pelo COPOM da PMESP, mostrando como funcionam as operações ali monitoradas e deflagradas.