[![](https://ampli-images.s3.amazonaws.com/production/2d442055-b7d8-4d50-9b4c-8c1f7b9f930b/original)](https://ampli-images.s3.amazonaws.com/production/2d442055-b7d8-4d50-9b4c-8c1f7b9f930b/original)

Os sistemas distribuídos, normalmente, possuem alguns objetivos para atender determinados requisitos. Alguns são considerados desafios importantes que os profissionais da área devem considerar. Segundo Tanenbaum e Steen (2008), esses objetivos são:

- Abertura.
- Concorrência.
- Escalabilidade.
- Heterogeneidade.
- Segurança.
- Tolerância a falhas.
- Transparência.

Entretanto, eles devem ser analisados mais como desafios a serem atingidos, uma vez que nem sempre o sistema distribuído conseguirá atingir todos de maneira integral.

A seguir, descreveremos a que se refere cada uma dessas metas na visão de Tanenbaum e Steen (2008), embora os itens Segurança, Escalabilidade, Tolerância a Falhas e Heterogeneidade mereçam uma atenção especial.

**Abertura**

No contexto de sistemas distribuídos, refere-se a quanto o sistema é modularizado ou, em outras palavras, quanto é fácil integrar e alterar tecnologias e _frameworks_ sem que o sistema seja comprometido. Você já deve ter ouvido falar em micro serviço, não é verdade? Esse nome é a maneira atual (_hype_) de dizer que o sistema possui uma grande abertura. Importante observar que, independentemente do que o termo "abertura" possa passar, é uma coisa positiva em sistemas distribuídos.

É importante ter em mente esse conceito, pois, à primeira vista, um sistema mais "aberto" parece ser uma coisa negativa, no sentido de estar mais vulnerável a falhas e, na verdade, em sistemas distribuídos, isso não é verdade. Segurança não tem relação nenhuma com essa abertura, mas isso é um assunto a ser detalhado em uma próxima oportunidade. Por exemplo, se o sistema utiliza tecnologias não-proprietárias, dizemos que a abertura desse tal sistema é maior.

**Concorrência**

Refere-se à capacidade de o sistema poder ser acessado e utilizado de maneira simultânea, concorrente (ao mesmo tempo), por vários usuários. Aqui, cabe novamente a ressalva de que, no contexto de sistemas distribuídos, o termo concorrência não tem uma conotação negativa (como ocorre, por exemplo, no comércio), apenas refere-se a um sistema que dá suporte a acessos simultâneos. Por exemplo, várias pessoas podem acessar um website de comércio eletrônico, certo? Pois bem, isso é um acesso concorrente.