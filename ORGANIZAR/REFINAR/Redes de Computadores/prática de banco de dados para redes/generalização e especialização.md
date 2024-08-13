**Conceitos básicos de generalização e especialização**

Algumas entidades podem apresentar ocorrências em que uma parte delas possui as mesmas propriedades e a outra parte possui propriedades diferentes, sendo necessário separá-las em subgrupos (especializações).

Usando o conceito de generalização e especialização, podemos subdividir uma entidade em várias outras de acordo com o significado dos seus dados.

O símbolo usado é um **triângulo** e para definir o tipo utilizamos **(t)** total e **(p)** parcial.

Podemos ver, no exemplo a seguir, que a entidade cliente de uma empresa pode ter ocorrências de pessoa jurídica e ocorrências de pessoa física; ambas podem ter nome, código e outros atributos em comum, mas possuem também atributos que as diferenciam, como CPF e RG. Esses atributos somente o cliente pessoa física possui, enquanto que CNPJ e Inscrição Estadual pertencem apenas ao cliente pessoa jurídica. Para que a entidade cliente não seja definida com todos os atributos em que uma possua determinados dados e outra não, separa-se a entidade cliente em duas para melhor organização: pessoa física e pessoa jurídica.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121728/a06i01_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121728/a06i01_md80_100.jpg)

A generalização/especialização está associada à herança porque as entidades especializadas, além dos seus próprios atributos, possuem também todos os da entidade generalizada.

No exemplo, cada ocorrência de **pessoa física** possui: **código**, **nome**, **RG** e **CPF**, enquanto as ocorrências de **pessoa jurídica** possuem: **código**, **nome**, **CNPJ** e **INSC_EST**.

A generalização/especialização pode ser classificada em dois tipos: total e parcial.

**Total (t)**

Quando cada ocorrência da entidade generalizada possui obrigatoriamente uma ocorrência correspondente a alguma das entidades especializadas. Cada cliente ou é pessoa jurídica ou é pessoa física, não existe um que não seja nenhuma das duas, conforme exemplo.

O símbolo usado é a letra **t**.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121729/a06i02_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121729/a06i02_md80_100.jpg)

**Parcial (p)**

A generalização/especialização é parcial quando existem ocorrências na entidade genérica que não possuem ocorrências correspondentes na entidade especializada.Vejamos um exemplo:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121730/a06i03_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121730/a06i03_md80_100.jpg)

Nesse caso, nem todo funcionário é engenheiro ou advogado. Algumas ocorrências existem apenas na entidade genérica.

**Generalização e especialização em vários níveis**

Pode ocorrer que uma entidade genérica tenha várias entidades especializadas que, por sua vez, também generalizem outras entidades especializadas. Não há limite no número de níveis hierárquicos.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121731/a06i04_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121731/a06i04_md80_100.jpg)

No exemplo apresentado, a pessoa física pode ser nativa do país em questão ou pode ser estrangeira. Cada uma possui documentos diferentes, mas pertence à mesma entidade genérica pessoa física. Pode-se observar que ambas possuem CPF e carteira profissional.

**Herança múltipla**

Podem existir casos em que uma entidade seja especialização de várias entidades genéricas, então, dizemos que a entidade possui herança múltipla de atributos.Observe o exemplo a seguir:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121733/a06i05_md80_100.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/1/2/1/7/121733/a06i05_md80_100.jpg)