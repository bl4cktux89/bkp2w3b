[![](https://ampli-images.s3.amazonaws.com/production/9573637f-cfb4-4411-b0b8-c622b204bb37/original)](https://ampli-images.s3.amazonaws.com/production/9573637f-cfb4-4411-b0b8-c622b204bb37/original)

Singh (2002) aponta para um fato interessante ocorrido durante a Segunda Guerra Mundial. Tanto os Aliados quanto o Eixo tinham equipes cuja missão única era encontrar cabos de comunicação do inimigo e inutilizar esses cabos. O motivo era simples: a comunicação por meio de cabos – naquela época, no início da década de 1940 – era considerada segura e confiável.

Sem os cabos, afirma o autor, as comunicações deveriam ocorrer por meio de ondas de rádio, o que as tornava menos confiáveis (mais ruídos, menos alcance, etc.) e, principalmente, acessíveis por quem quer que tivesse um aparelho de rádio, ou seja: qualquer um poderia escutar as comunicações do inimigo.

Este quadro, afirma Singh (2002), impulsionou o desenvolvimento de mecanismos que impedissem que qualquer um tivesse acesso a comunicações, tornando-as privadas mesmo que o meio de acesso (a atmosfera) fosse público, permitindo o acesso de quem quer que fosse.

______

**📝** **Exemplificando**Diante da impossibilidade de evitar que o inimigo compreendesse as comunicações no campo de batalha no Pacífico, durante a Segunda Guerra Mundial, os EUA desenvolveram uma estratégia engenhosa de “criptografia”: treinaram nativos da tribo Navajo, nativa do estado do Novo México, para se comunicarem usando sua língua nativa.

A língua Navajo era impermeável à tradução, e garantia sigilo nas comunicações. Este mecanismo nunca foi quebrado pelas forças inimigas durante todo o período em que foi utilizado na Segunda Guerra Mundial (SINGH, 2002).

______

As primeiras barreiras tecnológicas utilizadas para proteger as TICs foram a frequência de comunicação, apesar de bastante ineficientes. Quem quisesse escutar a conversa de duas partes precisaria saber em que frequência ela ocorre. A dificuldade para burlar esse tipo de barreira desapareceu quando foi inventado o dial.

Nada diferente dos botões giratórios dos rádios de hoje em dia, estes dispositivos permitem a varredura de todo o espectro de transmissão, e encontrar a frequência correta é uma questão de tempo e paciência.

Em seguida, os chamados _scramblers_ foram inventados e passaram a ser usados em telecomunicações sigilosas. Os _scramblers_ funcionam por meio da transposição e inversão de frequências e amplitudes, utilizando uma lógica restrita aos aparelhos que transmitem e são autorizados a receber as mensagens.

O mecanismo funciona como a criptografia de chave privada, uma vez que a forma e sequência de inversões e transposições funciona como uma chave secreta, de conhecimento apenas das partes autorizadas.

Este mecanismo, tal como é o caso de todos os mecanismos baseados em chaves privadas, sofre de problemas graves, como já discutido: não é possível autenticar o emissor da mensagem e, uma vez comprometida a chave, qualquer um que tenha um scrambler e o configure da maneira correta pode ouvir a conversa.

Esta questão crucial do sigilo das telecomunicações só foi resolvida com o advento dos mecanismos de chave pública, que permitiu o surgimento de uma das mais úteis e confiáveis tecnologias de comunicação segura: as VPN, (_Virtual Private Networks_), ou redes virtuais privadas.

Hoje em dia, os roteadores que permitem a comunicação entre redes são dotados da capacidade de estabelecer e manter VPN, o que tira da esfera de responsabilidade do usuário a decisão sobre como e quando criptografar suas comunicações.

A figura a seguir ilustra como se dá o tunelamento VPN:

[![](https://ampli-images.s3.amazonaws.com/production/29235a6e-b308-4c71-952b-e66f243746db/original)](https://ampli-images.s3.amazonaws.com/production/29235a6e-b308-4c71-952b-e66f243746db/original)

Duas redes se comunicando via tunelamento VPN. Fonte: elaborada pelo autor.

Uma VPN é estabelecida entre duas entidades comunicantes quando as mesmas (sejam elas rádio, telefones ou computadores) realizam os seguintes passos:

1. as entidades comunicantes iniciam o protocolo de comunicação trocando certificados digitais atestando sua autenticidade;
2. uma vez identificadas, as duas partes trocam chaves públicas de criptografia;
3. de posse das chaves públicas mútuas (que são seguras, porém lentas), ambas as partes entram em acordo sobre uma chave privada a ser usada (que permite comunicação bem mais rápida), protegidas pela criptografia de chave pública.
4. decidida a chave privada, as chaves públicas podem ser descartadas, e a comunicação efetiva tem início. A chave pública é usada apenas para a seção corrente, pois mesmo que seja decifrada (o que demora, no mínimo, vários meses ou mesmo anos), já não terá validade alguma para comunicações correntes.

______

**💭** **Reflita**Seria útil ter dois locais ultras seguros se comunicando por um meio inseguro sem garantia de sigilo entre as comunicações? Comparando essa situação hipotética com o que costumam dizer os especialistas em segurança: a corrente sempre quebra no elo mais fraco, você consegue estabelecer um paralelo? Qual o elo fraco, nesse caso? Como pode ser fortalecido?