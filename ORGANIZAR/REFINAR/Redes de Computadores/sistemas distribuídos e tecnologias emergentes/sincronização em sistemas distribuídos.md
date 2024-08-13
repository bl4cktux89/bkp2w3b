Em Sistemas Distribuídos a comunicação entre processos é muito importante. Entretanto, o modo como os processos cooperam e sincronizam é também um fator importante, uma vez que os processos não podem acessar um mesmo recurso simultaneamente.

Se comparado com os Sistemas Monoprogramáveis ou Multiprocessados, a sincronização em Sistemas Distribuídos costuma ser muito mais difícil, uma vez que conseguir acordo em Sistemas Distribuídos não é de todo comum.

Vamos ver um exemplo do que pode acontecer em um Sistema Distribuído se não houver um acordo global sobre horários:

- Suponha que o horário de _**output.o**_ seja 2144 e logo depois o _**output.c**_ venha a ser modificado, mas recebe o horário 2143, pois o relógio da sua máquina estava atrasado. Se isso acontecer, o programa compilador não será chamado e o programa resultante terá uma mistura de objetos fonte com dados novos e antigos. Se isso acontecer, o programa falhará.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/4/296428/18611.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/9/6/4/296428/18611.png)

Exemplo que demonstra uma situação quando uma máquina que tenha seu próprio relógio, recebe um evento que ocorreu após o outro.

Fonte: Figura 6.1 - pag. 141 do Livro Sistemas Distribuídos - Princípios e Paradigmas.

Se pensarmos em domínios de aplicação que tratam de sistemas financeiros, auditoria de segurança ou informações operativas fica claro que a marcação do tempo de maneira exata é muito importante.

Para as pessoas marcar o tempo é um mecanismo básico, mas se todos os relógios não estiverem sincronizados pode ser bastante problemático, onde os compromissos não serão devidamente atendidos, ou as esperas serão entediantes.

**RELÓGIOS FÍSICOS**

Para sincronizar os relógios em Sistemas Distribuídos, onde as CPU’s, normalmente, estão distantes e irão compartilhar recursos, a situação se torna complicada.

Atualmente, todos os computadores têm um circuito para controlar a passagem do tempo, chamados de _**relógios**_, que podem ser chamados de _**temporizador**_, que é um cristal de quartzo lapidado e usinado para cuidar desse tempo com precisão.

Se mantidos sob pressão esses temporizadores podem oscilar, e quando isso ocorre um contador reduz uma unidade de tempo e quando chega à zero gera uma interrupção, e o contador é recarregado por um registrador de retenção. Desse modo, é possível programar um temporizador para gerar uma interrupção a qualquer frequência desejada. Sendo que, essa interrupção é chamada de **ciclo de relógio.**

Os computadores tem uma RAM CMOS especial suportada por bateria, sendo que a cada ciclo de relógio é ativado o serviço de interrupção que soma uma unidade à hora armazenada, o que mantém o relógio atualizado.

Quando temos um único computador e um único relógio, não há problemas, uma vez que os processos que serão rodados nesse computador usarão o mesmo relógio, mas quando introduzimos múltiplas CPU’s, cada qual com o seu relógio, a situação sofre uma mudança radical sendo impossível garantir que em diferentes computadores os relógios funcionem exatamente à mesma frequência.

Em consequência dessa possível defasagem entre os relógios, os programas que esperam horários associados com os objetos, os processos ou uma mensagem, podem falhar.

Ao longo dos tempos vários mecanismos de medição do tempo foram criados, tais como: trânsito solar, segundo solar médio, hora atômica internacional, entre outros.

Atualmente, a hora mundial é controlada pelo _**Bureau Internacional de l’Heure**_ – BIH, que utiliza um mecanismo para resolver os diversos problemas de defasagem da hora causados pela mudança do tempo (como dias mais longos), chamado de **UTC –** Universal Coordinated Time **(Hora Coordenada Universal)**, que é a base de toda a medição moderna civil do tempo.

Esse mecanismo substituiu o Mean Time (tempo médio de Greenwich), que é a hora astronômica.

**PROTOCOLO DE TEMPO DE REDE**

Para auxiliar nos problemas de sincronização dos relógios físicos, alguns sistemas auxiliares são determinantes, como o GPS (Sistema de Posicionamento Global), o WWV (que transmite um pulso curto no início de cada segundo UTC) e o **NTP** (Network Time Protocol – **Protocolo de Tempo de Rede**).

No caso do **NTP**, a sincronização do tempo ocorre entre pares de servidores, onde cada servidor consultará o seu par, buscando em uma estrutura confiável de outros servidores NTP para obter a hora certa.

O NTP tem muitos aspectos importantes sendo alguns relacionados a identificar e mascarar erros, bem como, a ataques contra a segurança. No NTP, as máquinas lhe perguntam a hora periodicamente e ele responde a essas consultas.

O uso da hora certa é importante para servidores, para manter em operação serviços como E-mail, Logs do Sistema, Segurança, Criptografia, Pacotes de Rede, Transações Web, Banco de dados e outros serviços críticos como transações financeiras e etc, que por sua vez teriam seus serviços comprometidos e ou alterados  com um simples erro ou atraso da hora.

O algoritmo NTP é baseado na [**RFC 1305**](http://www.faqs.org/rfcs/rfc1305.html), referência no qual especifica várias regras e algoritmos para poder sincronizar os serviços de hora certa em uma rede. Tal algoritmo especifica questões técnicas para descrever o protocolo NTP.

**EXEMPLO DE INSTALAÇÃO DO SERVIDOR NTP**

A instalação do servidor NTP pode ser feita de duas maneiras, uma buscando o pacote de referência em um dos repositórios de sua distribuição Linux ou compilando diretamente os arquivos fontes  para uma instalação manual.

Em distribuições baseadas no **Debian**, como é o caso do Ubuntu, é possível efetuar a instalação através de seus repositórios com um simples comando:

sudo apt-get install ntp

Se quiser efetuar a instalação através do código fonte, primeiramente efetue o download do site da ultima versão como segue:

[](https://www.notion.soundefined)

Descompacte o arquivo do download em um diretório de sua preferência e prepare para a compilação:

tar -zxvf ntp-4.2.6p4.tar.gz       

cd ntp-4.2.6p4.      

/configure       

make       

make install

Crie os arquivos **ntp.conf** e **npt.drift**, no diretório etc “/etc/ntp.conf”:

touch /etc/ntp.conf

touch /etc/ntp.drift

No próximo passo, insira as linhas abaixo no arquivo ntp.conf (as linhas com o símbolo # trás o comentário sobre a linha de comando):

# "memória" para o escorregamento de frequência do micro.

driftfile /etc/ntp.drift

# estatísticas do ntp que permitem verificar o histórico de funcionamento e # gerar gráficos.

statsdir /var/log/ntpstats/statistics loopstats peerstats clockstatsfilegen loopstats file loopstats type day enablefilegen peerstats file peerstats type day enablefilegen clockstats file clockstats type day enable

# servidores públicos do projeto ntp.br

server a.st1.ntp.br iburstserver b.st1.ntp.br iburstserver c.st1.ntp.br iburstserver d.st1.ntp.br iburst

# A lista abaixo apresenta uma referência de endereços que devem

# ser usados. O ideal é que tenha de quatro e sete referências:

#  a.st1.ntp.br

#  b.st1.ntp.br

#  c.st1.ntp.br

#  d.st1.ntp.br

#  a.ntp.br

#  b.ntp.br

#  c.ntp.br

#  gps.ntp.br

# configurações de restrição de acesso.

restrict default kod notrap nomodify nopeer

restrict -6 default kod notrap nomodify nopeer

Agora vamos acertar a hora do sistema com o comando abaixo, e voltar para o prompt:

ntpd -q –g

Agora para inicializar em modo daemon basta executar o comando:

Ntpd

Caso você utilize algum tipo de firewall, o ntpd utiliza a porta 123, logo é preciso liberar tal porta para que serviço funcione corretamente.

Mais informações sobre o NTP consulte o seguinte site:

[**http://www.nacaolivre.com.br/servidor/configurando-servidor-ntp/**](http://www.nacaolivre.com.br/servidor/configurando-servidor-ntp/)