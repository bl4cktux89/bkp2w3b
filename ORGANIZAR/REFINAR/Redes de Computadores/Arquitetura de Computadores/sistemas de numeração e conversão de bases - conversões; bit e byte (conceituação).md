**Conversão do sistema binário para hexadecimal**

A conversão de um número binário para hexadecimal pode ser feita de forma indireta pelos métodos de conversão anteriores: converte-se do sistema binário para o decimal e depois do decimal para o sistema hexadecimal. Porém, uma conversão direta do sistema binário para o sistema hexadecimal pode ser efetuada substituindo-se quatro dígitos binários por um dígito hexadecimal, pois com quatro dígitos binários obtenho no máximo o número 16, que é a base do sistema hexadecimal.

**Exemplo 1**: Conversão do número 111012 em binário para o sistema hexadecimal.

1. Obtenho os quatro últimos dígitos do número binário: 1101
2. Converto diretamente para hexadecimal: 1101= 13 = D
    
    2
    
    10
    
    16
    
3. Com isso, obtenho o último dígito do número hexadecimal: D
    
    16
    
4. Repito o mesmo método para os dígitos restantes do número binário: 1 = 1= 1
    
    2
    
    10
    
    16
    
5. Unindo os dois dígitos, obtenho o número em hexadecimal: 11101= 1D
    
    2
    
    16
    

**Exemplo 2:** Conversão do número 1001010102 em binário para o sistema hexadecimal.

10102 = 1010 = A16

00102 = 210 = 216

12 = 110 = 116

1001010102 = 12A16

A conversão de hexadecimal para binário pode ser feita de forma indireta: converte-se de hexadecimal para decimal e de decimal para binário. Uma forma direta pode ser executada do modo contrário ao anterior: converte-se em quatro dígitos binários cada dígito hexadecimal. O último dígito do número hexadecimal fornece o valor dos quatro últimos dígitos do número binário.

**Exemplo 3:** Conversão do número CDF hexadecimal para o sistema binário.

F16 = 1510 = 11112

D16 = 1310 = 11012

C16 = 1210 = 11002

CDF16 = 1100110111112

**Exemplo 4:** Conversão do número 100216 hexadecimal para o sistema binário.

216 = 00102

016 = 00002

016 = 00002

116 = 00012

100216 = 10000000000102

Para conhecer um pouco mais sobre essa representação, veja o infográfico abaixo. Este infográfico faz parte da sequência desta aula e, portanto, é essencial para a aprendizagem.

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/3/5/2/2/8352224/484630-hexadecimal.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/8/3/5/2/2/8352224/484630-hexadecimal.jpg)

**Tabela comparativa entre os sistemas de numeração**

**Bit e byte (byte, kbyte, mbyte)**

|Decimal|Binário|Hexadecimal|Octal|
|---|---|---|---|
|0|0|[[0 2]]|0|
|1|1|[[1 2]]|1|
|2|10|[[2 2]]|2|
|3|11|[[3 2]]|3|
|4|100|[[4 2]]|4|
|5|101|[[5 2]]|5|
|6|110|[[6 2]]|6|
|7|111|[[7 2]]|7|
|8|1000|[[8 2]]|10|
|9|1001|[[9 2]]|11|
|10|1010|[[A 2]]|12|

  
  

|Decimal|Binário|Hexadecimal|Octal|
|---|---|---|---|
|0|0|[[0]]|0|
|1|1|[[1]]|1|
|2|10|[[2]]|2|
|3|11|[[3]]|3|
|4|100|[[4]]|4|
|5|101|[[5]]|5|
|6|110|[[6]]|6|
|7|111|[[7]]|7|
|8|1000|[[8]]|10|
|9|1001|[[9]]|11|
|10|1010|[[ORGANIZAR/REFINAR/Redes de Computadores/Arquitetura de Computadores/sistemas de numeração e conversão de bases - conversões; bit e byte (conceituação)/Untitled Database/A]]|12|

  
  

|Decimal|Binário|Hexadecimal|Octal|
|---|---|---|---|
|11|1011|[[B]]|13|
|12|1100|[[C]]|14|
|13|1101|[[D]]|15|
|14|1110|[[E]]|16|
|15|1111|[[F]]|17|

  
  

O computador trabalha com sinais elétricos em dois níveis R 0 e +V ou 0 e RV R, os quais são chamados de estados lógicos. Para definir cada estado lógico, ficou estabelecido que, quando temos 0 V (zero volt), o valor do estado lógico é 0 (zero), e, quando temos + V ou ? V, o valor do estado lógico é 1.

Assim, com a disponibilidade de apenas dois números, os cientistas criaram uma tabela de combinações desses estados. As tabelas são formadas de uma composição de 8 estados lógicos. Essa combinação é chamada de byte, e cada um dos estados lógicos são chamados de bit. Um conjunto de 8 bits, portanto, equivale a um byte.

Para representar a linguagem do usuário, o computador usa a relação da tabela de combinações dos estados lógicos para compor um caractere, o qual se constitui das letras de uma palavra ou de pontuações das frases. Um caractere equivale ao conjunto de 8 bits (1byte). Uma palavra se forma com a combinação de um conjunto de bytes. Por isso, cada letra, número, pontuação e sinais gráficos se forma no computador pela associação de 8 bits.

No entanto, para não haver diversidade de tabelas entre os fabricantes, garantindo a interoperabilidade entre eles, padronizou-se o mesmo valor para cada caractere. Instituiu-se a tabela ASCII (American Standard Code for Information Intercharge) como um conjunto de códigos-padrão para o computador representar números, letras, pontuação e outros caracteres.

**Tabela ASC II**

A tabela ASC II mostra no que um valor hexadecimal (decimal) corresponde ao código ASC II. Clique no botaão para abrir o texto complementar.

[**COMPLEMENTAR**](http://ead.uninove.br/ead/disciplinas/impressos/_g/arco80_100/a04tc01_arco80_100.pdf)

Os computadores têm suas características de processamento expressas em número de bits (8, 16, 32 ou 64). Cada instrução enviada para o microprocessador pode ser formada por 1byte, 2 bytes, 3 bytes e 4 bytes. Assim, dependendo da instrução, são necessárias de 1 a 4 linhas de memória para armazená-la.

O espaço em disco ou memórias define-se como múltiplos de 1kbyte, em que 1kbyte é igual a 1024 bytes (210). A tabela a seguir mostra os múltiplos do byte.

|Múltiplos do Byte|Abreviação|Valor|
|---|---|---|
|[[Quilobyte]]|KB|103 do byte (ou 1024 bytes)|
|[[Megabyte]]|MB|106 do byte (ou 1024 KB)|
|[[Gigabyte]]|GB|109 do byte (ou 1024 MB)|
|[[Terabyte]]|TB|1012 do byte (ou 1024 GB)|
|[[Petabyte]]|PB|1015 do byte (ou 1024 TB)|

  
  

Agora que você já estudou esta aula, resolva os exercícios e verifique seu conhecimento.Caso fique alguma dúvida, leve a questão ao Fórum e divida com seus colegas e professor.