**Introdução**

O objetivo da normativa 606-A é a perfeita identificação de todos os subsistemas de um projeto de cabeamento estruturado, tornando-o gerenciável no decorrer do tempo nas questões de manutenção, fornecendo rápida e precisa localização de todos os componentes que remontam a estrutura.

A norma brasileira segue a mesma filosofia da americana: ambas identificam todas as partes da rede interna estruturada (por exemplo, cabos, canaletas, espaços) e utilizam um código de cores para os dispositivos de conexão e etiquetas com nomes específicos para melhor visualização.

Dentre vários aspectos que a normativa rege, destacam-se os seguintes:

1. O identificador deverá ser único para evitar confusões.
2. Os cabos do cabeamento horizontal deverão ser identificados nas duas extremidades.
3. As tomadas nas áreas de trabalhos deverão estar identificadas em seus espelhos e _face plate_.
4. Os painéis ou blocos de conexão deverão estar identificados, bem como suas portas ou posições, de tal forma que, ao alimentarmos uma determinada porta, saberemos qual a tomada correspondente.
5. Na identificação das portas dos _hardwares_ de conectividade deverão ser utilizadas as cores padronizadas.
6. As informações relativas aos elementos da rede estruturada deverão ser guardadas em registro, que são tabelas cuja chave, a identificação e os campos representam as informações do elemento;
7. Ao final do projeto, deverá ser produzido um documento chamado _As Built_, que é a consolidação das informações e alterações ocorridas desde o seu início, contendo de forma atualizada os pontos nas plantas dos andares, a planta de situação e cortes verticais, assim como os testes de certificação do cabeamento;
8. As alterações de pontos de rede deverão ser realizadas por meio de ordens de serviço e toda essa documentação deverá ser mantida com suas respectivas atualizações para futuras consultas.

**Classes de gerenciamento**

A normativa ANSI/TIA/EIA-606-A especifica quatro classes de gerenciamento, dependendo da complexidade e o tamanho da infraestrutura de telecomunicações existentes, devendo oferecer um sistema de gerenciamento com metodologia para a localização do registro associado a qualquer identificador que foi submetido a um determinado _**hardware**_ do cabeamento.

**Classe de gerenciamento 1**

A classe 1 de gerenciamento aplica-se aos projetos com atendimento por uma única sala de equipamento, que por sua pequena estrutura não comporte salas de telecomunicações e cabeamento de _**backbone**_.

Para exemplificar melhor o tamanho de uma obra de cabeamento que se enquadra na classe 1 de gerenciamento, pode-se imaginar uma pequena rede montada em um único piso e tendo como sala de equipamento – ER uma pequena sala ou mesmo um _**rack**_ fechado do tipo armário com porta de acrílico e unidade de ventilação.

Nesta pequena rede é exigida a identificação dos seguintes itens:

1. Identificadores de espaços de telecomunicações ou da sala de equipamentos.
2. Identificadores dos cabos horizontais nas duas extremidades.
3. Identificadores das tomadas de telecomunicações em seus espelhos.
4. Identificadores no barramento principal de telecomunicações TMGB e
5. Identificadores do barramento de aterramento de telecomunicações TGB.

**Classe de gerenciamento 2**

A classe 2 de gerenciamento aplica-se em obras de cabeamento estruturado que são instalados em um único edifício, onde nos demais andares haja várias salas de telecomunicações (TRs) e _**backbone**_ ou cabeamento vertical. Nesse caso, os encaminhamentos de cabos não precisam fazer parte do sistema de gerenciamento de infraestrutura predial de telecomunicações e sua identificação se restringirá aos seguintes itens:

1. Todos os identificadores usados na classe 1 de gerenciamento;
2. Identificação dos cabos de _backbone_ do edifício;
3. Identificação dos pares dos cabos de fibra óptica do _backbone_;
4. Identificação das salas de telecomunicações distribuídas pelo edifício;
5. Identificação dos sistemas de proteção contra incêndio.

**Classe de Gerenciamento 3**

A classe 3 de gerenciamento aplica-se nos sistemas de cabeamento estruturado instalados num "campus" com grande concentração de edifícios, onde todas as redes são interligadas a uma sala de equipamentos principal ou Data Center.

Nesta classe de gerenciamento é necessária a identificação de todos os cabos externos, bem como os encaminhamentos em planta externa do terreno. Fazem parte desta classe as seguintes identificações:

1. Todas as identificações usadas na classe 2 de gerenciamento.
2. Identificação dos edifícios do campus.
3. Identificação dos cabos de _backbone_ horizontal do campus.
4. Identificação dos pares dos cabos de fibra óptica do _backbone_ horizontal do campus.

**Classe de gerenciamento 4**

A classe 4 de gerenciamento aplica-se a uma infra-estrutura que integra várias redes de campus em um único sistema de gerenciamento, o que não é muito comum e pouco utilizado na prática. Entre suas identificações destacam-se:

1. Todas as identificações utilizadas na classe 3;
2. Identificação do campus ou das localizações dos prédios.

**Identificadores**

Os identificadores devem ser únicos em todo o sistema de cabeamento estruturado para evitar confusão com informações duplicadas ou sistemas identificados, portanto cada etiqueta deve ter um número ou identificação única no sistema todo conforme exemplificado na imagem 01.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/8/104856/a14i01_cabestru80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/0/4/8/104856/a14i01_cabestru80_100.jpg)

Fazem parte dos componentes utilizados para a identificação:

1. Etiquetas laminadas.
2. Anilhas plásticas
3. Etiquetas de papel autoadesivas.
4. Plaquetas de alumínio.
5. Identificadores de plástico.

Para a perfeita identificação dos componentes do cabeamento estruturado e sua compreensão são utilizadas nomenclaturas simbólicas conforme apresentado a seguir:

**Tabela de identificação utilizada para cabos, blocos e pontos****de terminação**

![[Untitled 60.png|Untitled 60.png]]

Para a identificação dos encaminhamentos e espaços de telecomunicações, segundo a normativa ANSI/TIA/EIA 606-A, utiliza-se uma segunda tabela (a seguir), demonstrando todos os símbolos e sua descrição de identificação, necessários ao gerenciamento de uma obra em tecnologia de cabeamento estruturado.

**Tabela de identificação e simbologia para caminhos e espaços**

![[Untitled 1 39.png|Untitled 1 39.png]]

**Exemplos de identificação**

Placa ou etiqueta instalada na porta de uma sala de telecomunicações (TR) situada no 2º andar do prédio 3 de um campus:

[![](https://ead.uninove.br/ead/disciplinas/web/_g/cabestru80_100/imagens/a14i04_cabestru80_100.jpg)](https://ead.uninove.br/ead/disciplinas/web/_g/cabestru80_100/imagens/a14i04_cabestru80_100.jpg)

Nota: quando houver apenas um único prédio, não há necessidade da identificação do mesmo.

Para a identificação das etiquetas do cabo secundário (cabo usado no lançamento horizontal) de 4 pares UTP, ligado no ponto de telecomunicações nº 004, localizado no 6º andar de um edifício único, proveniente da porta 002 do primeiro painel de conexão cruzada da sala de telecomunicações nº 1, são necessárias duas identificações, sendo uma na extremidade da área de trabalho a que ela chega e outra no painel de conexão que está ligada no interior da sala de telecomunicações:

[![](https://ead.uninove.br/ead/disciplinas/web/_g/cabestru80_100/imagens/a14i05_cabestru80_100.jpg)](https://ead.uninove.br/ead/disciplinas/web/_g/cabestru80_100/imagens/a14i05_cabestru80_100.jpg)

Etiqueta utilizada no painel de conexões e;

[![](https://ead.uninove.br/ead/disciplinas/web/_g/cabestru80_100/imagens/a14i06_cabestru80_100.jpg)](https://ead.uninove.br/ead/disciplinas/web/_g/cabestru80_100/imagens/a14i06_cabestru80_100.jpg)

Etiqueta utilizada na área de trabalho no espelho.

Como resultado do trabalho de identificação, será gerado um mapa completo da rede, com todas as suas conexões, o que facilitará muito a administração e rápida recuperação no caso de manutenção em algum dos cabos, tomadas ou painéis de manobra de cabos.

Observe que um único cabo UTP deverá ter no mínimo quatro identificações a serem instaladas: duas nas pontas do cabo depois de lançado e mais duas etiquetas fixadas no espelho na área de trabalho e no painel ou bloco de manobra cruzada, instalado no interior da sala de telecomunicações.

Para auxiliar a identificação, é utilizada também uma tabela de cores que possibilita a rápida visualização de cada elemento em um sistema de gerenciamento de cabeamento estruturado.

![[Untitled 2 32.png|Untitled 2 32.png]]

**Resumo**

A normativa responsável pelo gerenciamento e administração dos sistemas de cabeamento estruturado é a ANSI/TIA/EIA 606-A. A ANSI/TIA/EIA 606-A é dividida em quatro classes de gerenciamento, conforme o tamanho da rede em tecnologia de cabeamento estruturado. A mais utilizada é a de classe 2, que trata de uma rede instalada em um edifício com várias salas de telecomunicações e diversos pontos.

A ANSI/TIA/EIA 606-A utiliza etiquetas e anilhas plásticas para realizar as identificações fixadas nos cabos, nos painéis e blocos de conexão. Todas as identificações seguem um modelo pré-formatado e as informações deverão ser únicas para registro preciso, com a finalidade de uma rápida visualização e localização dos elementos.