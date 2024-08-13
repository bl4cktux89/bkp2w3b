### Introdução

Os dispositivos de Entrada e Saída (E/S) ou Input/Output – I/O são também chamados de “Periféricos”, pois permitem a interação do processador com o usuário, possibilitando a entrada e/ou a saída de dados.Os dispositivos de Entrada são os responsáveis pela por fazer a “ponte” entre o desejo do usuário com a correspondente ação no computador. Eles codificam a informação que entra em dados a fim de que possam ser processados pelo SO.

Os dispositivos de Saída fazem a “ponte” contrária, eles decodificam os dados em informações que podem ser compreendidas pelo usuário.Há dispositivos que foram desenvolvidos tanto para Entrada como para Saída de dados, por exemplo: o HD (Hard Disk), Pendrive, Modem, etc.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/0/8/320822/21167.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/2/0/8/320822/21167.png)

Dispositivos de Entrada/Saída (E/S) ou Input/Output (I/O).

Os dispositivos de E/S são os responsáveis pelo fornecimento de informações, e esse fornecimento ocorre:

- Do usuário para o computador: entrada de dados ou informações via teclado, mouse, scanners, etc;
- Do computador para o usuário: saída de dados ou informações via monitor, tablet, cellular, pendrives, papel, etc.
- Do computador para o computador: entrada e saída de dados ou informações via arquivos, por exemplo: um arquivo gerado (chamado “Arquivo de Saída”) ao final de um processamento será a entrada de informações (chamado de “Arquivo de Entrada”) para um outro processamento. A figura abaixo ilustra essa situação: o processamento do “Programa Cálculo da Folha de Pagamento” gerou o arquivo de saída “Arquivo de Hollerites”, esse arquivo será o arquivo de entrada do processamento do “Programa que emite Hollerites”.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/4/5/304551/21168.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/4/5/304551/21168.jpg)

Fluxo de processamento: Arquivos de Entrada e Arquivos de Saída.

Fonte:

A figura (a) a seguir ilustra a sequência que o SO executa quando uma informação armazenada num HD é necessária num processamento:

- A CPU (Central Processing Unit: Unidade de Processamento Central) aciona o Controlador de Disco, fazendo uma solicitação ao HD;
- O Controlador de Disco aciona o HD e passa a solicitação feita pela CPU. O HD atende a solicitação e responde ao Controlador de Disco;
- A Controlador de Disco se comunica com o Controlador de Interrupção (dispositivo que controla o fluxo de informações);
- O Controlador de Interrupção retorna as informações do HD à CPU.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/4/5/304561/21172.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/0/4/5/304561/21172.jpg)

Fluxo de comunicação desde a CPU até um dispositivo de disco (HD).

Fonte: DEITEL, H. M.; DEITEL, P. J.; CHOFFNES, D. R. Sistemas operacionais. 3. ed. São Paulo: Pearson Prentice Hall, 2005.

Todos os dispositivos de E/S possuem um Controlador (ou Controladora). Esse componente tem a função de intermediar as solicitações do SO com o dispositivos de E/Se também:

- Converte fluxo serial de bits em bloco de bytes;
- Traduz operações genéricas: leitura / gravação;
- Gerar seqüência de acionamentos para manipulação do dispositivo;
- Realizar correções de erro se necessário.

**E quando ocorre uma interrupção?**

- A finalização de uma tarefa por um dispositivo gera interrupção;
- Sinal de interrupção concentrado em um controlador de interrupção: os dispositivos enviam sinal via barramento. Cada dispositivo possui uma identificação de interrupção;
- Controlador de interrupção: processa a interrupção conforme disponibilidade/prioridade e repassa o sinal para interromper a CPU. Coloca um número nas linhas de endereço do barramento;
- Na CPU: o número das linhas de endereço definem índice do vetor de interrupções. O Vetor de interrupções contem o endereço base da rotina de tratamento.

**Gerenciamento dos dispositivos de Entrada e Saída**

É a maneira pela qual o SO irá lidar com o hardware (HW). Há diferentes formas de tratar as diversas situações apresentadas pelas implementações de HW.

Objetivos do gerenciamento de E/S:

- Garantir a independência do dispositivo de E/S;
- Permitir que programas possam acessar qualquer dispositivo de E/S;
- Garantir a nomeação uniforme de arquivos: nome/caminho (path) de arquivo ou dispositivo;
- Garantir o tratamento de erros;
- Utilização de buffer para armazenamento temporário: recepção de pacotes da rede a serem tratados num Segundo momento;
- Controlar os dispositivos compartilhados e os dedicados.