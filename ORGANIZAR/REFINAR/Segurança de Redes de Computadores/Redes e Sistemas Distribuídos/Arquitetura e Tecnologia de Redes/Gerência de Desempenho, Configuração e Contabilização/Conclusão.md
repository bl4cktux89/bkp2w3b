[![](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)](https://ampli-images.s3.amazonaws.com/production/3ab1ae4e-ad0a-404f-b930-4492530cb9f6/original)

Esta unidade buscou trazer conceitos importantes sobre o gerenciamento de redes de computadores e a aplicação de comandos e ferramentas para verificação, análise e gerenciamento de redes, observando informações de configuração de dispositivos da rede e o seu tráfego. Estas ferramentas são importantes para que o profissional de tecnologia da informação possa conceber e operar sistemas de redes de computadores, porém com naturalidade, visto que não abarca todo o conhecimento necessário para uma gestão completa de redes. Neste cenário, bibliografias complementares e ferramentas foram sugeridas para que você possa se aprofundar na área de redes de computadores e se tornar um profissional de excelência.

______

**➕****Saiba mais**

A utilização de comandos e aplicativos para configuração e gestão de redes de computadores não se restringe aos exemplos dados e pode ser conhecida com maiores detalhes em literaturas específicas de cada plataforma operacional.

Para configurações de sistemas Windows, pode ser consultado o livro Configuração do Windows Server 2008: infraestrutura de rede, de T. Northrup e J. C. Mackin, disponível na biblioteca virtual.

Para configurações de sistemas Linux, pode ser consultado o livro Manual completo do Linux: guia do administrador, de Eve Nemeth, Garth Snyder e Trent R. Hein, disponível na biblioteca virtual.

Para configurações de sistemas Linux, pode ser consultado o livro Dominando o Linux: Red Hat e Fedora, de Bill Ball e Hoyt Duff, disponível na biblioteca virtual.

Para conhecimento de projeto de interconexão de redes, pode ser verificado o livro Projeto de Interconexão de redes: Cisco Internetwork Design – CID, de Matthew Birkner, disponível na biblioteca virtual.

Considerando a segurança dos sistemas nas áreas onde tem Wi-Fi, a escolha do equipamento com recursos providos e configuráveis é importante. Sugerimos a leitura do texto Porque você precisa se preocupar com o gerenciamento do Wi-Fi na sua empresa, da página Olhar Digital (2017).

______

**➕****Pesquise mais**

Para contribuir com a compreensão e o uso de ferramentas de gerenciamento de redes, é sugerida a leitura das informações do texto _Conheça as_ _Principais Ferramentas de Gerenciamento de Redes de Mercado_, de Marcelo Brenzink do Nascimento.

Para realizar análise de performance e gerenciamento de redes, é importante a utilização de ferramentas de software. Fica a sugestão para conhecer as seguintes ferramentas:

1. Wireshark.
2. Capsa.
3. Microsoft Network Monitor.
4. SLAView.
5. Zenoss.
6. Cisco Prime Network Analysis.

_____

A seguir, acompanhe o relatório apresentado como solução ao problema indicado no início da aula.

**Relatório do projeto de redes: monitoramento de rede via** _**sniffig**_

A solução para análise do tráfego de rede foi a implantação de um _sniffer_ na rede através de um programa chamado _Wireshark_. O objetivo é monitorar e capturar pacotes de rede que passam pelo _switch_, que realiza a comutação central da rede, distribuindo as conexões para outro _switch_ e roteador dos departamentos. A figura do _sniffer_ apresentado na figura abaixo representa o dispositivo de hardware/software implantado na rede para análise e captura de pacotes. Este dispositivo é caracterizado por um computador munido do software farejador (_sniffer_).

[![](https://ampli-images.s3.amazonaws.com/production/70bf15ec-64ce-4dbc-a772-48ba8038d948/original)](https://ampli-images.s3.amazonaws.com/production/70bf15ec-64ce-4dbc-a772-48ba8038d948/original)

Topologia de rede do escritório de contabilidade com implantação de sniffer. Fonte: elaborada pelo autor.

Em seguida, foram avaliadas informações coletadas através do software _Wireshark_, conforme Figura 2.53. O volume de informações é grande, considerando a intensidade das requisições na rede. A análise das requisições pode ser realizada através de filtros inseridos no programa, como HTTP (_HyperText Transfer Protocol_), que fará com que a ferramenta filtre apenas os pacotes do respectivo protocolo, ou ainda utilizar as ferramentas de estatística para análise.

Importante informar que a consultoria também pode utilizar outros programas de sniffig para fazer a avaliação dos dados capturados na rede, como o _Microsoft Network Monitor_, apresentado na figura abaixo.

[![](https://ampli-images.s3.amazonaws.com/production/33b63e03-45d1-4551-9609-251735d7e162/original)](https://ampli-images.s3.amazonaws.com/production/33b63e03-45d1-4551-9609-251735d7e162/original)

Tela do sniffer Wireshark com informações de monitoramento de pacotes da rede. Fonte: captura de tela da ferramenta Wireshark elaborada pelo autor.

[![](https://ampli-images.s3.amazonaws.com/production/dc556274-0993-4827-ab25-a84d15cbf2ca/original)](https://ampli-images.s3.amazonaws.com/production/dc556274-0993-4827-ab25-a84d15cbf2ca/original)

Tela do Microsoft Network Monitor. Fonte: captura de tela do Microsoft Network Monitor elaborada pelo autor.

Avaliando os dados coletados via software sniffer, pode-se perceber os acessos dos hosts ativos no ambiente de rede, por exemplo, as requisições e os acessos do endereço IP 192.168.0.12.

O relatório pode ser completado com análises mais detalhadas.