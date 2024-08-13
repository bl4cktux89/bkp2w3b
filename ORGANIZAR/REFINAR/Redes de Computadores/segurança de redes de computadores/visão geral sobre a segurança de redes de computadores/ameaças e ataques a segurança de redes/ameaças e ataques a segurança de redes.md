> [!important]  
> O presente tópico tem por objetivo apresentar em linha gerais os conceitos fundamentais relacionados a segurança da informação, os mecanismos lógicos e físicos de proteção as redes de computadores.  

### **Introdução**

A facilidade com que, hoje, nos conectamos a Internet e a infinidade de aplicativos e ferramentas que facilitam a nossa vida tem mudado drasticamente a forma como nós nos relacionamos, trabalhamos e divertimos. Do ponto de vista das organizações, esta nova realidade traz muitas oportunidades, mas também muitos desafios, principalmente, quando se trata de oferecer a segurança dos dados que são armazenados e trafegam pelas redes de computadores (McNab, Chris, 2017).

A complexidade proporcionada por este cenário é fonte de grande preocupação por parte das instituições, demandando atenção para os seguintes pontos:

- **Privacidade dos dados** - Com a adoção, por parte das organizações, da LGPD (Lei Geral de Proteção de Dados) a partir do ano de 2020, as organizações passaram a ser responsáveis por todos tipo de dado de dado pessoal, não só os de seus clientes, mas também dos colaboradores e parceiros.
- **Gestão dos dispositivos pessoais** -Com políticas de BYOD (Bring Your Own Device - traga o seu próprio dispositivo), as organizações se deparam no desafio de gerenciar múltiplos dispositivos e, principalmente, tendo que lidar, muitas vezes, com a negligência de seus funcionários, clientes e colaboradores no uso dos recursos institucionais disponíveis.
- **Treinamento** - Proporcionar segurança não é apenas da equipe de segurança, mas depende de todos os entes da organização. E por isso, treinamentos baseados nas políticas institucionais devem ser periódicos para reafirmar o papel de todos como agentes de garantidores das melhores práticas a minimizar vulnerabilidades.
- **Tecnologias emergentes** - Com a popularização do IoT (Internet das Coisas) e do uso cada vez mais disseminado da IA (Inteligência Artificial) devemos estar preparados para novas formas de ataques que exploram tais tecnologias. Para tanto, é necessário investimento em ferramentas mais inteligentes para identificação de ameaças e detecção de anomalias de rede e invasões.

### **Segurança da Informação**

O conceito de Segurança da Informação, atualmente, está padronizado pela norma ISSO/IEC 17799:2005, e corresponde a proteção de um conjunto de dados que possuem valor para um individuo ou organização. Este conceito se aplica a todos os aspectos de proteção do dado e da informação a ele associado, tais como a segurança no armazenamento, dos sistemas computacionais e informações eletrônicas

A segurança da informação busca garantir os atributos de confidencialidade, integridade e disponibilidade, orientando a análise, o planejamento e a implantação da segurança. Isto é feito, por exemplo, por meio da criação de um Comitê de Segurança da Informação,  conforme ilustrado abaixo.

- Ilustrações
    
    ![[Untitled 84.png|Untitled 84.png]]
    
    ![[Untitled 1 48.png|Untitled 1 48.png]]
    
    ![[Untitled 2 38.png|Untitled 2 38.png]]
    
    ![[Untitled 3 24.png|Untitled 3 24.png]]
    
    ![[Untitled 4 21.png|Untitled 4 21.png]]
    
    ![[Untitled 5 18.png|Untitled 5 18.png]]
    
    ![[Untitled 6 13.png|Untitled 6 13.png]]
    
    ![[Untitled 7 12.png|Untitled 7 12.png]]
    
    ![[Untitled 8 10.png|Untitled 8 10.png]]
    
    ![[Untitled 9 9.png|Untitled 9 9.png]]
    
    ![[Untitled 10 6.png|Untitled 10 6.png]]
    

### **Ameaças e Ataques a Segurança**

### Ameaça

O conceito de **Ameaça** está associado com os principais e prováveis riscos que uma organização está sujeita. Essas ameaças podem ser do seguinte tipo (Moraes, A. F. 2010):

- **Ameaças intencionais:** São aquelas provocadas de forma intencional por agentes com criminoso profissional, hacker, funcionário mal-intencionado e espionagem industrial.
- **Ameaças relacionadas aos equipamentos:** Equipamentos podem apresentar falhas e hardware e software ou até mesmo problemas por falta de atualização.
- **Ameaças naturais:** Todos os equipamentos e as instalações físicas de uma organização estão sujeitos a eventos naturais, tais como raios, inundações, queda de energia e fogo. Estes eventos normalmente são difíceis de se evitar, mas podem ser facilmente detectados.
- **Ameaças não intencionais:** Surge a partir do não conhecimento ou negligência dos administradores e usuários de um sistema, seja por falta de treinamento e cumprimento de regras de segurança.

### Vulnerabilidade

A vulnerabilidade constitui como o ponto no qual o sistema é sensível ao ataque. No processo de identificação da vulnerabilidade e das ameaças  a um sistema devemos considerar estes dois conceitos de forma dependentes entre si, já que dadas as ameaças, onde estão as possíveis vulnerabilidades. Ao mesmo tempo que, conhecida a vulnerabilidade do sistema, quais ameaças podem surgir.

As vulnerabilidades podem ser do tipo:

- Humana
- Naturais
- Físicas
- Hardware e software
- Mídias de armazenamento

### Ataque

**As etapas utilizadas para efetivação de um ataque podem ser enumeradas conforme abaixo (Moreno, Daniel. 2017):**

**1. Reconhecimento:** Nesta etapa o invasor busca informações sobre a vítima, utilizando, por exemplo, bases de dados do tipo WHOIS. A partir desse banco de dados é possível ter informações sobre o domínio, contatos e endereços IPs do alvo. Tais informações são públicas e podem facilmente encontradas na web.

> [!important]  
> No Brasil, o registro.Br é o responsável por manter a base de dados de WHOIS de qualquer empresa. Para ter mais informações, acesse https://registro.br/tecnologia/ferramentas/whois e realize uma consulta digitando o endereço de um site.  

Por meio do aplicativo NSLOOKUP é possível descobrir, por exemplo, o DNS, o servidor de e-mail, ou servidor FTP, conforme figura abaixo.

![[Untitled 11 5.png|Untitled 11 5.png]]

**2. Varredura:** Consiste em utilizar ferramentas de scanning ou varredura nos endereços da vítima com o objetivo de encontrar o sistema operacional, versão e os serviços ativos na máquina alvo. Existe uma infinidade de ferramentas com esse objetivo, abaixo segue algumas delas:

- Aircrack-ng
- Nikto
- Nessus Vulnerability Scanner
- Scanner de Vulnerabilidade OpenVAS

**3. Enumeração:** Na etapa de enumeração é realizado teste dos serviços identificados na etapa anterior e determinar possíveis vulnerabilidades. Por exemplo, verificar qual é o servidor web e posteriormente verificar qual o melhor exploit a ser utilizado; ou verificar se FTP permite acesso como anônimo.

> [!important]  
> Um exploit é um conjunto de comando, dados ou parte de um software que busca explorar vulnerabilidades ou defeitos em um dispositivo alvo com o objetivo de causar má execução do software ou até mesmo dar controle total sobre o dispositivo.  

**4. Ataque:** A partir do memento em que se tem um conjunto de informações sobre o dispositivo alvo, o invasor pode definir qual a melhor ferramenta para obter sucesso na sua invasão. Os principais tipos de ataques são definidos abaixo (Basta, A; Basta, N. Brown, M. 2015):

- **Ataques de Senha:** O atacante utiliza ferramentas para tentar descobrir a senha por força bruta, tentando todas possíveis combinações ou capturando arquivos de hash de senhas.
- **Buffer Overflow:** Essa técnica permite invadir outras áreas de memória por meio da injeção de strings maiores do que as permitidas estourando áreas do buffer.
- **Ataques de Privilégios:** A partir de contas de usuários com baixo privilégio o atacante busca ascender por meio de exploits e conseguir ter privilégio de ROOT, com poderes totais sobre aquele dispositivo ou sistema.
- **Ataques a aplicações Web:** Exploram vulnerabilidades em determinadas aplicações voltadas a serviços web, como o IIS da Microsoft e Apache no Linux. Ataques do tipo buffer overflow a esses alvos são muito comuns.
- **Instalação de Backdoors e Softwares de Controle Remoto:** Com auxílio de programas que abrem portas nas máquinas, conhecidos como backdoors, permitem ao atacante ter acesso a elas. Isso é feito, por exemplo, a partir do envio de um e-mail com um arquivo anexado que executa o backdoor na máquina alvo, permitindo dessa forma, que uma conexão a partir da rede local em direção a máquina do atacante seja estabelecida.
- **Ataques a dispositivos de rede:**  Esses ataques são direcionados a dispositivos de rede, tais como roteadores e switches, buscando vulnerabilidades dos sistemas operacionais neles instalados e também dos protocolos por eles utilizados. Exemplos desses ataques:
    - Envenenamento do cache ARP.
    - Ataques aos protocolos de roteamento RIP, OSPF e BGP.
    - Ataques ao protocolo STP.
    - Salto de VLAN.
    - Exploits de CDP. Sniffing de pacotes com TCP Dump/Dsniff
- **Ataques de negação de serviços (DoS):** Buscam causar a indisponibilidade dos serviços e das redes do alvo. Normalmente este tipo de ataque ocorre de forma distribuída a partir de um conjunto de máquinas comprometidas pelo atacante, onde ele assumi o controle dessas máquinas e centraliza de forma direciona o ataque para a máquina ou sistema alvo. Esse ataque é conhecidas como DDOS (Negação de serviço distribuído).

### **Mecanismos de Segurança**

Os mecanismos de segurança podem ser classificados em dois grandes grupos: mecanismos físicos e os mecanismos lógicos (Stallings, William. 2015).

**Mecanismos físicos:** são limitadores de acesso a infraestrutura e, consequentemente, a informação propriamente dita de usuários que não possuem autorização. Exemplos destes controles são: portas, trancas, paredes etc.

**Mecanismos lógicos:** consiste em ferramentas, geralmente eletrônicas que apoiam o controle lógico. São eles:

- **Criptografia** garante a confidencialidade por meio da transformação da informação de modo a torná-la ilegível para terceiros, e que, da mesma forma, garanta a reversibilidade da informação para quem é autorizado, conforme ilustrado na figura que segue.

![[Untitled 12 4.png|Untitled 12 4.png]]

- **Assinatura digital** - Consiste em um conjunto de mecanismos que garante a integridade e a autenticidade de documentos eletrônicos.
- **Mecanismos que garantem a integridade** consiste em mecanismos que garantem que a informação não foi alterada por usuários não autorizados. Exemplos desses mecanismos: funções de "Hashing".
- **Mecanismos de certificação** - utilizados para atestar a validade de um documento, conforme ilustrado no processo de certificação de documentação da figura que segue.

![[Untitled 13 4.png|Untitled 13 4.png]]

- **Firewalls** ou "parede de fogo" controla a passagem do tráfego de uma rede para outra, permitindo o negando este tráfego com base em regras pré-estabelecidas. Por exemplo, o firewall da figura que segue permite a passagem do tráfego da Internet para a DMZ (Zona Desmilitarizada), mas impede que o tráfego com origem na Internet acesse a rede local.

![[Untitled 14 4.png|Untitled 14 4.png]]

**Sistema de Detecção de Intrusão (IDS)** - Como o próprio nome diz, os IDS trabalham analisando os pacotes da rede, analisam logs de eventos dos sistemas operacionais, ou realizam a análise da integridade de um arquivo, como os realizados pelos antivírus. Na figura que segue é mostrado um IDS baseado em rede, tendo a função de analisar de forma passiva o tráfego da rede e gerando alertas para o administrador da rede.

**Sistemas de Prevenção de Intrusão (IPS)** - Além de gerar alertas, os IPS tomam medidas ativas de bloqueio caso seja detectada uma tentativa de intrusão. Os IPS normalmente estão nos segmentos de redes mais críticos em linha com o tráfego, ou seja, todo tráfego que passa por ele é inspecionado, conforme ilustrado na figura que segue.

![[Untitled 15 4.png|Untitled 15 4.png]]