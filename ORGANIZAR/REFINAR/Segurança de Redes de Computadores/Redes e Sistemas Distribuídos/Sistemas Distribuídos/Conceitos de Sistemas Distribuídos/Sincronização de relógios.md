[![](https://ampli-images.s3.amazonaws.com/production/1162f163-9cd5-455e-8bcf-1060a5ce976d/original)](https://ampli-images.s3.amazonaws.com/production/1162f163-9cd5-455e-8bcf-1060a5ce976d/original)

Sistemas formados por múltiplos computadores necessitam sincronizar suas ações entre si, e uma das maneiras mais utilizadas, dada sua simplicidade e popularidade, é A sincronização horária, por meio do protocolo conhecido como _Network Time Protocol_ (NTP) (NTP, 2018). Esse protocolo, por sua vez, utiliza o protocolo de transporte de dados _User Datagram Protocol_ (UDP), operando na porta 123. Essencialmente, esse protocolo é utilizado para sincronização do relógio das máquinas locais (desktops, notebooks, servidores) e demais dispositivos de rede.

A referência horária é dada por sistemas de altíssima precisão, como os relógios atômicos (NTP, 2018). Dada a precisão desses sistemas, computadores conectados a eles pertencem a uma camada de servidores chamada de estrato 1 (os sistemas de alta precisão em si pertencem a uma camada topológica chamada de estrato 0).

Segundo NTP (2018), como não existem muitos servidores no mundo conectados diretamente a relógios atômicos, outros servidores são conectados aos de estrato 1, os quais, por sua vez, formam uma segunda camada de servidores de horário, chamada de estrato 2, e essa hierarquia se estende até os servidores de estrato 15, conforme podemos ver na figura abaixo. Os computadores dos usuários são configurados para atualizarem a informação horária por meio da rede, consultando servidores de estratos com valores mais altos.

[![](https://ampli-images.s3.amazonaws.com/production/ac461472-21bb-41dd-abf2-4a1a55b0435e/original)](https://ampli-images.s3.amazonaws.com/production/ac461472-21bb-41dd-abf2-4a1a55b0435e/original)

Sistema de servidores NTP. Fonte: elaborada pelo autor.

Aqui no Brasil, por exemplo, temos o Observatório Nacional (ON), que é o órgão oficial responsável pela geração, conservação e disseminação da Hora Legal Brasileira.

Um aspecto muito interessante do protocolo NTP é que ele é projetado para verificar a latência (atraso, delay) entre a máquina cliente e a máquina servidora, e a implementação disso é muito simples: essencialmente, de tempos em tempos, a máquina cliente faz uma consulta a um servidor NTP para verificar em quanto seu relógio está atrasado (ou adiantado) em relação ao servidor horário de referência, processando a seguinte operação:

_**(t4 - t1) - (t3 - t2)**_ em que _**t1**_ é a hora, minuto, segundo e milésimos de segundo (também chamada de timestamp) da máquina cliente ao enviar uma requisição (através de um pacote, no contexto de redes de computadores) para o servidor NTP; _**t2**_ é o timestamp do servidor ao receber essa requisição; _**t3**_ refere-se ao _timestamp_ em que um pacote de resposta a essa requisição é enviado ao cliente; e _**t4**_ é o _timestamp_ em que o cliente recebe a resposta do servidor NTP. Esse cálculo, portanto, resulta em quanto o sistema operacional deverá atrasar (ou adiantar) o relógio da máquina local para que ela esteja sincronizada com a referência horária em questão, por exemplo, a Hora Legal Brasileira, em nosso caso. Um exemplo desse processo é ilustrado na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/2220348d-d81c-4c14-a3b2-5a147d50babf/original)](https://ampli-images.s3.amazonaws.com/production/2220348d-d81c-4c14-a3b2-5a147d50babf/original)

Exemplo de sincronização através do protocolo NTP. Fonte: elaborada pelo autor.

Alguns serviços, como os de acesso remoto e de autenticação de usuários, podem não funcionar adequadamente, caso haja uma diferença muito grande no horário da máquina cliente (solicitante) em relação à máquina servidora (que roda e disponibiliza o serviço). Por esse motivo, é muito importante saber como habilitar a sincronização horária das máquinas utilizando o NTP. A configuração, bem como suas etapas, varia entre os sistemas operacionais e entre suas versões.

______

**📝****Exemplificando**

Um exemplo utilizando um sistema operacional Windows 10 a partir do procedimento a seguir:

1. Abra o **Prompt de Comando (CMD)**, que pode ser acessado pelo menu iniciar, ou pelo campo de busca, digitando _**prompt**_ ou _**cmd**_.

2. Na janela do CMD, insira o código a seguir e pressione a tecla “Enter”:

`**w32tm /config /syncfromflags:manual /manualpeerlist:0.pool.ntp.org**`

[![](https://ampli-images.s3.amazonaws.com/production/bd2ab30c-eee7-4469-9163-0e89930ae619/original)](https://ampli-images.s3.amazonaws.com/production/bd2ab30c-eee7-4469-9163-0e89930ae619/original)

Apontando para o servidor NTP. Fonte: captura de tela do Prompt de Comando do Windows 10.

Na figura abaixo, podemos observar que, ao final do comando, aparece a mensagem “O comando foi concluído com êxito”. Lembre-se: para executar os comandos, você deve estar como um usuário Administrador ou executar o CMD como Administrador. Agora que fizemos o apontamento para o servidor NTP que utilizaremos, devemos reiniciar o serviço de data e hora para aplicar as alterações.

3. Utilize os comandos `**net stop w32time e net start w32time**` para parar o serviço e iniciar, reiniciando-o, conforme podemos observar na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/dbe69696-8e70-4683-937e-fa37a3aa8e9b/original)](https://ampli-images.s3.amazonaws.com/production/dbe69696-8e70-4683-937e-fa37a3aa8e9b/original)

Reiniciando o serviço de data e hora. Fonte: captura de tela do Prompt de Comando do Windows 10.

Após isso, forçaremos uma sincronização de data e hora para verificarmos se está tudo funcionando corretamente.

Force uma sincronização por meio do comando `**w32tm /resync /rediscover**`, conforme observamos na figura a seguir:

[![](https://ampli-images.s3.amazonaws.com/production/0446e4ca-bd91-4c3b-9d35-c5ca60d95a3d/original)](https://ampli-images.s3.amazonaws.com/production/0446e4ca-bd91-4c3b-9d35-c5ca60d95a3d/original)

Sincronizando data e hora. Fonte: captura de tela do Prompt de Comando do Windows 10.

Por meio da saída da figura acima, podemos observar a mensagem que será dada, informando que nossa configuração foi feita com sucesso.