**Introdução**

Todo ambiente de rede precisa armazenar informações para possibilitar o seu gerenciamento (autenticação, grupos de usuários, permissões, cotas de armazenamento e impressão, compartilhamentos etc.). Hoje em dia, a maioria das grandes organizações possui ambientes de rede heterogêneos, com várias plataformas presentes (Linux, Windows, Solaris…) e com redes virtuais fisicamente conectadas, muitas vezes distribuídas geograficamente. Essas redes podem interligar campi , porém, esse mesmo ambiente, apesar de estar conectado fisicamente na mesma rede, por questões administrativas podem não se comunicar devido a diversos fatores como segurança, permissões, níveis departamentais, entre outros.

Em seguida, abordaremos alguns conceitos básicos sobre transmissão analógica e transmissão digital.

**Sinais Analógicos**

O sinal analógico é aquele que varia de forma contínua ao longo do tempo. Originalmente, os sinais de áudio, vídeo e provenientes de sensores são analógicos, pois variam ao longo do tempo com formas e amplitudes características.

Uma forma de onda analógica é uma função do tempo que tem uma escala contínua de valores. Um exemplo de sinal analógico ou contínuo é o obtido a partir de um microfone cuja fonte é a voz humana.

**Sinais Digitais**

Um sinal digital é definido como uma função do tempo que tem um conjunto discreto de valores. Se o sinal digital é do tipo binário, apenas dois valores são permitidos (bit – binary digit).

Os sinais digitais são produzidos por equipamentos de processamento de dados ou por conversores que digitalizam informações analógicas. Se os dados consistem de texto alfanumérico serão caracteres codificados com um dos vários formatos-padrão existentes. Exemplos deles são o ASCII (American Standard Code for Information Interchange), o EBCDIC (Extended Binary Coded Decimal Interchange Code), o Baudot e o Hollerith. O material textual é transformado, então, em um formato digital, para ser processado por um sistema digital.

Tanto no sinal analógico como no digital, o sistema de comunicação deve manter a forma de onda original ou garantir que esta possa ser recuperada pelo receptor. Assim, as técnicas de transmissão e codificação, aliadas à escolha do canal apropriado, são fatores de sucesso da transmissão.

### Sinalização analógica

Um exemplo de informação digital é um trem de pulsos quadrados de amplitudes 0 e A (volts), conforme ilustra a figura abaixo

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/5/6/5670/i01_536.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/0/0/5/6/5670/i01_536.jpg)

Modulação de sinal

**Codificação analógica x codificação digital**

Na transmissão analógica, as informações são enviadas sob a forma de quantidades continuamente variadas. Em consequência, em transmissão de dados, esse processo exige a presença de um modulador e de um demodulador. E o sinal é adaptado a uma onda portadora. Os sinais analógicos possuem a forma de onda senoidais, variando com o tempo nas mais diversas formas, a exemplo dos sinais de voz humana que variam de maneira inconstante.

A transmissão digital é, em resumo, a transmissão direta do sinal digital na linha de transmissão e pode utilizar eventualmente apenas recursos de codificação digital. No entanto, como a distorção do sinal torna-se sensível com o aumento da distância, recomenda-se que se considere a distância máxima em função da velocidade de transmissão. As ondas são quadradas trabalhando com os picos máximo e mínimo de tensão, a fim de representar o bit 0 e 1. Como a onda quadrada possui variações súbitas e formato bem definido, ela se altera facilmente ao longo da transmissão devido a perdas e ruídos, deixando de ter o formato original e ocasionando a perda do sinal. Daí a limitação de distância de transmissão de sinais de dados sem modulação.

Para que a transmissão de sinais analógicos de áudio e vídeo aconteça, é necessário que ocorra o processo de digitalização desses sinais analógicos, que é o processo de transformar suas alterações de voltagem em bits 0 e 1, ou seja, convertê-las em sinais digitais.

### Podemos dividir o esquema de codificação em três grandes grupos: unipolar, polar e bipolar:

Unipolar: nesse método, um nível de tensão representa um binário. Pode apresentar problemas de sincronismo em cadeias binárias longas.

Polar: usam-se dois níveis de tensão para representar os dados. São exemplos de codificação polar os esquemas NRZ, RZ, Manchester e Manchester Diferencial.

Bipolar: usa três níveis, como o RZ, mas diferente do RZ, o nível 0 representa o bit 0, e os valores negativos e positivos representam o bit 1.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223944/7643.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/3/9/223944/7643.jpg)

codificação, linha, NRZ-L, NRZ-I, transição

### Funcionamento das principais codificações

Codificação NRZ (NonReturn to Zero)

Código diferencial. O dado é codificado pela presença (1) ou ausência (0) de transição no início do período do bit, sinal decodificado pela comparação com pulsos adjacentes, na presença de ruído, é mais fácil detectar uma transição do que comparar um valor absoluto com um limiar (definirá se é 0 ou 1).

Vantagens dos códigos NRZ:

- São simples
- Utilizam eficientemente a largura de banda.

Manchester e differencial manchester

Há uma transição no meio de cada período de bit, a transição constitui um mecanismo de sincronização, transição positiva representa um 1, e transição negativa, um 0. A transição no meio do período é usada apenas para sincronização. O bit zero é representado pela presença de transição no início do período e o bit um, pela ausência dela.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/0/224019/7647.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/2/4/0/224019/7647.jpg)

linha, NRZ e Mancheste

A importância da interoperabilidade

Interoperabilidade é a capacidade de um sistema de se comunicar de forma transparente com outro sistema (semelhante ou não). Para que se possa dizer que há interoperabilidade entre os sistemas, é importante que ele trabalhe com padrões abertos. Seja um sistema de portal, seja um sistema educacional, ou ainda, um sistema de e-commerce, hoje em dia se caminha cada vez mais para a criação de padrões para sistemas.

O crescimento das ofertas de serviços, das plataformas, da internet vem contribuindo bastante para que proprietários de diversas plataformas possam manter essa compatibilidade de troca de informações, trazendo muita agilidade e redução de custos de mão de obra para a organização, sem contar na aproximação cada vez maior de todas as plataformas existentes.

Bem, chegamos ao fim desta nossa aula, tentamos aqui apresentar, de uma maneira macro, o significado e a importância de se ter uma rede heterogênea e a importância de distinguirmos os sinais analógicos e sinais digitais, para entendermos melhor esse processo de troca de informações entre redes. Que tal agora realizarmos um breve teste de conhecimento. Tudo pronto? Então, vamos começar.

**Considerações Finais**

As informações transmitidas por um canal  são basicamente: áudio, vídeo (imagem) ou dados, e podem ser em forma de sinal analógico ou digital, dependendo do sistema envolvido.

O transmissor é responsável pela adequação do sinal original às características do canal escolhido, que tem como função a recuperação do mesmo no destino. Já o receptor deve detectar o sinal recebido e adequá-lo a um formato reconhecido pelo destino.

O canal representa o meio físico utilizado para transportar a informação e pode ser: cabo de par trançado (blindado ou não), cabo coaxial, cabos ópticos, guias de onda (utilizadas em transmissão por micro-ondas), no espeço livre. Cada um deles possui características de transmissão e suscetibilidade, sendo as interferências que necessitam ser adequadas para que a informação possa ser transportada. Como resultado dos efeitos do canal, a informação recebida sempre será diferente da informação transmitida.

Uma das interferências que afeta o canal é o ruído, por limitar o desempenho de um sistema de comunicação, alterando as características do sinal transmitido, a ponto dele não ser reconhecido no receptor de destino. Para reduzir esta interferência, pode-se utilizar sistemas de cabeamento blindado, em que uma cobertura metálica (folha ou malha) é sobreposta ao cabo e aterrada, drenando o ruído que atingiria os cabos. Em situações mais críticas, as fibras ópticas são opção por serem imunes às radiações.

Além dos ruídos e de outras perturbações no canal, também devemos ter cuidado com a atenuação, que é a diminuição progressiva do sinal ao longo do canal.