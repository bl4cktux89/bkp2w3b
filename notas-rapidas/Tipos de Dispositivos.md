Nó / Node - qualquer dispositivo conectado a uma rede de comunicação de dados.

Endpoint - origem ou destino.

Redistribuição - dispositivos de rede.

Servidores - compartilhamento de recursos, fornecimento e gerenciamento de serviços

Terminal: sem capacidade de processamento por si mesmo, utiliza recursos do servidor

Cliente - utiliza os serviços

# Dispositivos de Segurança

## Firewall:

- Um firewall pode ser implementado através de hardware ou software
- Pode atuar especialmente nas camadas 2, 3, 4 e 7
- Ele bloqueia pacotes que entram ou saem da rede
    - Via Inspeção Stateless: o firewall examina todos os pacotes e compara com conjunto de regras
    - Via Inspeção Stateful: o firewall examina o estado da conexão entre as redes
- É a primeira linha de defesa para proteger a rede de ameaças externas

### Intrusion Detection System (IDS)

É um sistema passivo que tem a função de detectar quando ocorre uma violação ou um ataque contra a rede

Geralmente é utilizado em conjunto com espelhamento de tráfego e compara com um conjunto de padrões:

- Baseado em Assinatura: avalia o tráfego de rede em busca de assinaturas conhecidas de malware ou ataques
- Baseado em Anomalia: avalia o tráfego de rede em busca de alterações suspeitas
- Baseado em Política: avalia o tráfego de rede em relação a uma política de segurança específica declarada

Pode ser implantado no nível do host, como Sistema de Detecção de Intrusão Baseado em Host (HIDS)

### Intrusion Prevention System (IPS)

Um IPS é um sistema ativo projetado para impedir que uma violação ou ataque tenha sucesso em danificar a rede.

- Geralmente projetado para realizar uma ação ou conjunto de ações para interromper a atividade maliciosa
- Informará um administrador de rede por meio do uso de arquivos de log, SMS e/ou notificação por e-mail

Todo o tráfego no segmento de rede passa pelo IPS para entrar ou sair desse segmento de rede.

- Assim como o IDS, todo o tráfego é avaliado em relação a um conjunto de padrões.

O melhor posicionamento na rede é entre um roteador (com um firewall) e o segmento de rede de destino.

Ele é programado para fazer uma resposta ativa à situação:

- Bloquear o endereço IP ofensivo
- Desativar a interface vulnerável
- Encerrar a sessão de rede
- Redirecionar o ataque

# Dispositivos de otimização e desempenho

## Load Balancer

Um balanceador de carga também pode ser chamado de switch de conteúdo ou filtro de conteúdo.

Um dispositivo de rede usado para balancear a carga entre vários hosts que contêm os mesmos dados - distribuindo a carga de trabalho para obter maior eficiência.

- Comumente usado para distribuir as solicitações (carga de trabalho) para uma fazenda de servidores entre os vários servidores, ajudando a garantir que nenhum servidor fique sobrecarregado.

## Proxy Server

Um servidor proxy é um dispositivo que solicita recursos em nome das máquinas clientes.

É frequentemente usado para recuperar recursos de redes não confiáveis externas em nome do cliente solicitante.

Ele oculta e protege o cliente solicitante.

Também pode ser utilizado para filtrar o conteúdo permitido.

Pode aumentar o desempenho da rede ao armazenar em cache páginas da web frequentemente solicitadas.