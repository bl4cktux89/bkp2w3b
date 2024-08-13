### **Introdução**

Atualmente, processos criptográficos são fundamentais para garantir a confidencialidade dos dados que trafegam pelas redes e aqueles que são armazenados. Nesse processo de proporcionar confidencialidade, envolve alterar um texto em um formato legível para um formato ilegível.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/5/298536/20122.jpg)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/8/5/298536/20122.jpg)

Processo criptográfico

Elementos da Criptografia

Os seguintes elementos e termos são comuns em qualquer processo criptográfico:

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363570/29202.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/3/5/363570/29202.png)

Termos utilizados em Criptografia

### **Criptografia de chave simétrica e assimétrica**

Existem basicamente dois grandes grupos de criptografia que se diferenciam na forma pela qual as suas chaves funcionam, são elas a criptografia de chave simétrica e criptografia de chave assimétrica.

Criptografia de chave simétrica: também conhecido como ?algoritmos de chave privada?, utilizam a mesma chave no processo de criptografar como também para decriptografar, conforme ilustrado na figura que segue.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/4/0/364098/29204.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/4/0/364098/29204.png)

Processo de criptografia de chave simétrica

Na criptografia de chave simétrica, tanto o emissor quanto o receptor devem ter uma cópia da mesma chave. Ela tem a vantagem de ser muito mais rápidas do que os algoritmos de chave assimétrica, mas são vulneráveis a interceptação da chave e, como consequência, decifrar a mensagem. A tabela abaixo mostra os algoritmos simétricos e as velocidades para cifrar a mensagem.

![[Untitled 94.png|Untitled 94.png]]

### **Criptografia de chave simétrica e assimétrica**

Existem basicamente dois grandes grupos de criptografia que se diferenciam na forma pela qual as suas chaves funcionam, são elas a criptografia de chave simétrica e criptografia de chave assimétrica.

Criptografia de chave simétrica: também conhecido como ?algoritmos de chave privada?, utilizam a mesma chave no processo de criptografar como também para decriptografar, conforme ilustrado na figura que segue.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/4/0/364098/29204.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/3/6/4/0/364098/29204.png)

Processo de criptografia de chave simétrica

Na criptografia de chave simétrica, tanto o emissor quanto o receptor devem ter uma cópia da mesma chave. Ela tem a vantagem de ser muito mais rápidas do que os algoritmos de chave assimétrica, mas são vulneráveis a interceptação da chave e, como consequência, decifrar a mensagem. A tabela abaixo mostra os algoritmos simétricos e as velocidades para cifrar a mensagem.

![[Untitled 1 58.png|Untitled 1 58.png]]

Abaixo são discutidas as características de cada um dos algoritmos mostrados na tabela anterior

- **3DES:** O 3DES (Triplo DES) é um padrão de geração anterior que a realiza a criptografia do texto com DES e na sequência realiza recriptografia do texto já criptografado. Esse processo é realizado com três chaves distintas a 168 bits ou duas distintas a 112 bits.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/0/1/240117/9219.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/4/0/1/240117/9219.png)

Criptografia 3DES

- **AES:** O AES (Padrão de Criptografia Avançada) é um dos algoritmos mais utilizados pelos fabricantes de tecnologia de segurança. O AES agrupa os dados em bloco de 128 bits e, na sequência, realiza atividades de permutações e substituição nesses bits para produzir o texto cifrado. Chaves de 128 são suficientes para garantir a confidencialidade de informações governamentais e no caso de informações altamente secretas, chaves de 192 ou 256 são necessárias.
- **Blowfish:** Um dos primeiros algoritmos de código aberto distribuídos ao público. Realiza cifragem em blocos de 64 bits que, por sua vez, utiliza uma chave variável de 1 a 448 bits. A criptografia utiliza permutação e substituição.
- **RC4:** Criado pela Segurança de Dados RSA é um algoritmo muito rápido e é utilizado em ambiente que necessitam de segurança moderada. Pode ser utilizado no padrão WEP e também no SSL.

### Criptografia de chave assimétrica

Também conhecido como criptografia de chave pública, utilizam duas chaves para criptografar e decriptografar os dados, sendo uma mantida secreta e outra pode ser fornecida publicamente. Enquanto uma das chaves é utilizada para criptografar a outra é utilizada para decriptografar, no entanto, a criptografia de chave assimétrica é muito mais lenta do que a simétrica. Por outro lado, ela resolve o problema de distribuição de chaves, principalmente, para aplicações com assinatura digital e o certificado digital. Na figura abaixo é mostrado um exemplo da criptografia assimétrica (Basta, A; Basta, N. Brown, M. 2015).

![[Untitled 2 46.png|Untitled 2 46.png]]

Abaixo são discutidas as características de cada um dos algoritmos mostrados na tabela anterior

- **DSS:** é utilizado para gerar assinatura digitais para documentos eletrônicos, sendo padrão para assinatura digital do governo dos EUA. Funciona a partir da combinação de chaves pública e função hash para criar uma versão condensada do texto. Esse resumo é utilizado para criar uma assinatura digital que, posteriormente, é enviado com a mensagem. De posse da chave pública do remetente e a mesma função, o destinatário é capaz de verificar a autenticidade da mensagem.
- **RSA:** O RSA é considerado muito seguro e sua segurança está associada a dificuldade de fatorar números primos grandes. As chaves públicas e privadas são número primos de 100 a 200 dígitos ou mais. Entretanto, é muito mais lento que algoritmos simétricos como o DES e, por isso, não é utilizado na encriptação de grandes blocos de dados.
- **Diffie-Hellman:** O algoritmo Diffie-Hellman foi desenvolvido para resolver o problema de distribuição de chaves simétricas. Isso permite que os dois lados estabeleçam comunicação segura por meio do uso de uma chave secreta compartilhada por meio de canais públicos e inseguros como a Internet.

**SAIBA MAIS...**

O Diffie-Hellman é um algoritmo de troca de chaves bastante utilizado na internet para estabelecimento de VPNs. Ele possui um mecanismo interessante para trocar as suas chaves. Saiba como as chaves são trocadas clicando em: [**Wikipedia**](https://www.notion.sohttp://xn--o%20diffie-hellman%20%20um%20algoritmo%20de%20troca%20de%20chaves%20bastante%20utilizado%20na%20internet%20para%20estabelecimento%20de%20vpns-vgm./)

### Funções Hash

As funções de Hash transforma dados de comprimento variável em um valor de hash de tamanho fixo com o objetivo de garantir a integridade dos ao verificar a ocorrência de alteração não previstas no envio da mensagem. Por exemplo, ao aplicar a função hash a um arquivo que deve ser enviado, um hash do arquivo é gerado. Ao enviarmos o arquivo e a função hash criptografada, quem recebê-los pode verificar a integridade decriptografando o hashing e comparando-o com o resultado do cálculo hash realizado na recepção. Os principais algoritmos de hashing são descritos abaixo (Moraes, A. F, 2010).

- **Algoritmo Resumo de Mensagem 5 (MD5):** utilizando blocos de 512 bits de entrada, o MD5 produz um hash de 128 bits. Apesar de ainda ser considerado seguro, recomenda-se o uso de funções SHA-1. Isso se deve a quantidade de pontos encontrados em função dos seus valores reduzidos de hash.
- **Algoritmo de Hash Seguro (SHA)**: padrão superior ao MD5, o SHA-1 tem 160 bits de comprimento e um conjunto de variantes mais fortes, conhecidos com SHA-2 que produzem hashes de 224, 256, 384 e até 512 bits. Apesar disso, vulnerabilidades foram reportadas no SHA-1, por isso, recomenda-se o SHA-2.
- **Códigos de Autenticação de Mensagem (MAC):** é uma função hash que incorpora uma chave e para executar a função de hash o receptor deve ter a mesma chave utilizada para criação do MAC.

### Assinatura digital

A assinatura digital é utilizada para verificar a autenticidade e a integridade das mensagens enviadas. Para tanto, executa-se a função de hashing sobre a mensagem a ser enviada. Posteriormente, sobre o hash gerado é executada uma função de criptografia assimétrica, utilizando uma chave privada. Por fim, o hash criptografado é anexado a mensagem original e enviado.

Quando a mensagem com o hash criptografado chega ao receptor, ele decriptografa o hash com a chave pública. Posteriormente, o receptor calcula o hash da mensagem. Caso seja idêntico ao hash criptografado enviado, a mensagem é tida como integra.

**Não Repúdio**

Garante a validade das mensagens não sejam questionadas pelas partes. Isso é garantido pela confidencialidade da chave privada.

### Certificados Digitais

O certificado digital tem a finalidade de verificar a chave pública de um determinado usuário é realmente dele. O certificado digital é assinado digitalmente por uma autoridade certificadora (CA) que verifica a autenticidade da chave pública. Quando uma comunicação é realizada, a chave pública não é enviada, mas sim o certificado. Se a assinatura da CA for aceita, significa que o certificado foi expedido pela CA. Entretanto, não significa que o certificado é valido, é necessário ainda a consulta para verificar a lista de revogação de certificados por parte do CA (Cert.br, 2020).

### Emissão, criação e revogação de certificados

Para emissão de um certificado, A entidade certificadora (CA) faz uma série de exigências de acordo com o tipo de segurança do certificado. Os tipos de certificado são elencados abaixo.

- **Certificado tipo A - Assinatura Digital:** atesta a identidade do titular, atestando autenticidade de operações e a integridade do documento assinado.
- **Certificado tipo S - Certificados de Sigilo:** é utilizado para garantir o sigilo de transações. É possível criptografar, por exemplo, e-mails.
- **Certificado tipo T - Certificado de sigilo:** Conhecido também como carimbo de tempo. É utilizado para garantir a temporalidade e veracidade de informações.
- **Certificado OM-BR - Certificado do tipo Objeto Metrológico:** Emitidos para equipamentos metrológicos regulados pelo Inmetro.
- **Certificado tipo A CF-e-SAT:** Emitidos somente para equipamentos do Sistema e Transmissão de Cupom Fiscal Eletrónico.

Para criação do certificado, o usuário crias as chaves pública e privada de forma randômica. Na sequência a chave pública é enviada para a CA, onde será criado o certificado a partir da chave privada da CA. Por fim, o certificado é enviado de volta para o usuário já assinado.

Os certificados podem ser revogados sempre que o usuário é removido do domínio de segurança, quando o usuário reconhece que perdeu a chave privada e quando há suspeitas de ataque. Na figura abaixo são mostrados os detalhes de um certificado digital instalado no navegor.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/2/268251/12566.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/8/2/268251/12566.png)

### Infraestrutura de chave Pública (PKI)

A PKI consiste de políticas, entidades e mecanismos utilizados para carregar as chaves criptográficas e associa-las aos respectivos proprietários, programas, protocolos etc. os protocolos que utilizam PKI são mostrados abaixo (Moraes, A. F, 2010):

- Aplicações como S/MIME
- Protocolos TCP/UDP/ SSL
- Protocolo IPSec
- Protocolos de Enlace PPP (CHAP)

A infraestrutura PKI é mostrada na figura abaixo e é composta pelos seguintes elementos.

- Autoridade de Registro (RA)
- Autoridade de Certificação (CA)
- autoridade de validação (VA)

[![](https://img.uninove.br/static/0/0/0/0/0/0/8/0/5/9/9/8059949/59488.png)](https://img.uninove.br/static/0/0/0/0/0/0/8/0/5/9/9/8059949/59488.png)