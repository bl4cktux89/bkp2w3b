### Introdução

A camada Física trata da transmissão de bits por um canal de comunicação (A. S. Tanenbaum). Apesar do modelo TCP/IP original não fazer distinção entre as camadas de enlace de dados e física, é importante tratarmos tal camada separadamente, visto que, ela é de fundamental importância para entendermos a sua influência sobre todas as camadas superiores como, exemplo, a sua influência sobre uma aplicação de rede que requer alta largura de banda (em bits por segundo) em um ambiente que com alta interferência eletromagnética. Outro típico exemplo, é a utilização de redes wireless para transportar dados essenciais de uma organização. No primeiro caso, podemos optar por cabos blindados ou fibras ópticas; e no segundo, se desejarmos transmitir dados confidenciais de uma organização devemos evitar a utilização de redes wireless.

Os meios de comunicação podem ser classificados em guiados não guiados: Os meios guiados são as fibras ópticas e fio de cobre, enquanto que as não guiadas são as popularmente conhecidas como redes “wifi”, radio terrestre e via satélite.

Você já deve ter se perguntado por que sua internet está lenta?? Muitas vezes o motivo pode estar associado ao meio de transmissão e com as condições em que esse meio de comunicação está operando. Você tem que saber que existem limitações impostas pela natureza sobre aquilo que pode ser transmitido por um canal de comunicação.

Sinais e a Largura de banda

A quantidade de dados transmitidos por segundo é limitada pela Largura de banda do canal (em MHz). A largura de banda é uma propriedade física, e em geral, depende da espessura e do comprimento do meio. Um exemplo disso é a telefonia, que proporciona um canal de voz com largura de banda de 3100 Hz disponibilizados pelas operadoras de telecomunicações. Como a telefonia requer baixa largura de banda (MHz) em comparação a outros tipos de transmissões, acarretará em uma menor quantidade de bits por segundo transmitidos.

No passado, utilizávamos modens para conectarmos a internet. Como alguns devem se lembrar, a conexão era de baixa velocidade. Posteriormente, na mesma linha telefônicas, passamos a utilizar a tecnologia ADSL, que aumentou consideravelmente essa velocidade utilizando uma largura de banda (MHz) maior do que a do modem. Apesar dos avanços trazidos pela tecnologia ADSL, a sua abrangência é limitada (~ 5 Km) – Quanto maior a distância para central telefônica menor vai ser a velocidade de transmissão. Isso se deve a atenuação do sinal (diminuição da potência ao longo do caminho) e do ruído, conforme mostrado na Figura 1.

![[Untitled 31.png|Untitled 31.png]]

Os exemplos citados anteriormente, evidenciam a importância dos meios de transmissão e de suas condições de instalação e operação, que, consequente, pode afetar as nossas aplicações.

A camada Física, como já comentando anteriormente, estabelece as especificações mecânicas, elétricas e ópticas, conforme resumido na tabela 1 e descritos abaixo:

![[Untitled 1 21.png|Untitled 1 21.png]]

- Componentes Físicos: Os componentes físicos, como o próprio nome diz, estão relacionados aos meios de transmissão propriamente ditos, conectores, antenas.
- Técnica de codificação de quadro: Para representar o sinal digital (binário 0 ou 1) em um meio de transmissão é necessário variar de forma discreta a tensão (volts) em cabos metálicos; o comprimento de onda e o pulso luminoso em fibras ópticas; e as técnicas de codificações analógicas e digitas para transmissão em redes sem fio.
- Método de Sinalização: Especifica o formato e a duração de um pulso elétrico ou óptico. Dentre eles podemos citar a alteração da frequência, amplitude e a fase.

![[Untitled 2 19.png|Untitled 2 19.png]]

### Meios de Comunicações

Os meios de comunicações podem ser classificados em guiados e não guiados: O meios guiados confinam a transmissão no meio de comunicação como, por exemplo, as fibras ópticas e os cabos metálicos, por outro lado, os meios não guiados propagam os dados pelo espaço livre, sem utilizar uma técnica para confinamento, como ocorre nas redes wireless e bluetooth.

Outro fator importante sobre os meios de transmissão está associado com capacidade de transmissão de dados por segundo, também conhecido como Largura de Banda (em bits por segundo, bps) – Não confundir com a Largura de Banda do canal (em MHZ), discutido anteriormente. Qualquer transmissão de dados em redes de computadores utiliza múltiplos de 1000 bps e não 1024 bits.

Cuidado: Transmissão de dados utiliza múltiplos de bits (“b” minúsculo), como mostrado na tabela abaixo. Observe que abreviamos a unidade de Largura de banda com kbps, Mbps, Gbps, etc, e não MBps (Megabit por segundo), GBps (GB por segundo).

![[Untitled 3 13.png|Untitled 3 13.png]]

**Cabo Coaxial**

O cabo coaxial é um meio guiado, chamado dessa forma devido a formação de camadas de isolantes e condutores em formato concêntrico em volta de um eixo (axis). Os elementos de construtivos desse cabo são mostrados na figura abaixo e descritos abaixo:

(1) Núcleo condutor de cobre;

(2) Isolador dielétrico interno

(3) Blindagem eletromagnética;

(4) Revestimento de plástico.

![[Untitled 4 13.png|Untitled 4 13.png]]

### Fibras ópticas

As fibras ópticas são meios de transmissão guiado por um dielétrico, feito de vidro ou polímero. O seu funcionamento se baseia no fenômeno de reflexão interna total que ocorre no núcleo da fibra. As fibras ópticas são classificadas em multimodo e monomodo, conforme mostrado na figura abaixo.

![[Untitled 5 12.png|Untitled 5 12.png]]

Cabo Par-trançado

O cabo par-trançado é formado por 4 pares de fios entrelaçado aos pares e classificados em: Cabo par-trançado não blindado (UTP - Unshielded Twisted Pair, cabo) e cabo par-trançado blindado (STP - Shielded Twisted Pair). O cabo par-trançado (Twister pair) é o mais utilizado atualmente em virtude do seu baixo custo relativo e facilidade de instalação e manutenção. O Cabo par-trançado é fabricado unindo dois fios de cobre trançados entre si com o objetivo de reduzir a interferência entre pares (Diafonia) e a interferência eletromagnética externa por meio do efeito de cancelamento, conforme mostrado na figura abaixo.

![[Untitled 6 8.png|Untitled 6 8.png]]

Abaixo comparamos os cabos par-trançados com as fibras ópticas. As principais vantagens da fibra óptica em relação aos demais meios, é a sua maior Largura de Banda (em bps) transmitida e a imunidade a interferência eletromagnética.

![[Untitled 7 7.png|Untitled 7 7.png]]

### Sem fio

Atualmente, a transmissão de dados em redes wireless é bastante comum, e explora a característica de não necessitar de meios físicos para transmissão, proporcionando alta mobilidade. As redes sem fio utilizam ondas eletromagnéticas para a transmissão, tais ondas podem ser dividas no que é chamado espectro eletromagnético característico de cada tipo de transmissão, seja ela infravermelho, microondas ou ondas de rádio. A Figura abaixo ilustra algumas aplicações sem fio.

![[Untitled 8 7.png|Untitled 8 7.png]]

Padrões 802.11

Existem, atualmente, diferentes padrões para redes wireless, conforme mostrado na figura abaixo, que se diferenciam de acordo com a frequência, velocidade máxima de transmissão e compatibilidade com versões anteriores, conforme mostrado na figura abaixo.

![[Untitled 9 6.png|Untitled 9 6.png]]