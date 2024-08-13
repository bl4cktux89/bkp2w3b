### **Introdução**

Um servidor de arquivos geralmente mantém os dados gerados pelos funcionários da organização. Permitir e fornecer o acesso de forma adequada a esses arquivos e pastas, disponibilizados pela rede, é parte fundamental no processo de gerenciamento de serviços de arquivo no Windows Server 2012.

Nesta aula, aprenderemos como proteger arquivos e pastas nos servidores Windows Server 2012, e realizar um gerenciamento de forma a manter os dados sempre disponíveis e protegidos.

É possível definir o compartilhamento em discos formatados com FAT, FAT32, exFAT, NTFS, ou Resilient File System (refs). E as permissões podem ser definidas especificando:

- Um conjunto de permissões aplica-se a discos formatados com exFAT, FAT ou FAT32. Essas permissões são chamadas de permissões de compartilhamento.
- Dois conjuntos de permissões aplicam-se a discos formatados com NTFS ou refs: permissões NTFS (também referida como permissões de acesso) e as permissões de compartilhamento.

Ter dois conjuntos de permissões permite determinar exatamente quem tem acesso a arquivos compartilhados e o nível de acesso atribuído.

### **Usando e Ativando o Compartilhamento de Arquivos**

As configurações de compartilhamento em um computador determinar a forma como os arquivos podem ser compartilhados. Os dois modelos de compartilhamento de arquivos que o Windows Server 2012 suportes têm as seguintes diferenças:

- Compartilhamento de arquivos padrão: permite que usuários remotos acessem arquivos, pastas e unidades na rede. Quando compartilhamos uma pasta ou uma unidade, todos os seus arquivos e subpastas se tornam disponíveis para um conjunto específico de usuários. As permissões de compartilhamento e permissões de acesso em conjunto permitem controlar quem tem acesso a arquivos compartilhados e o nível de acesso atribuído.
- Compartilhamento de pasta pública: Permite que os usuários locais e (opcionalmente) os usuários remotos acessem quaisquer arquivos armazenados em _%systemdrive% \Usuários do computador\pasta pública_. As permissões de acesso na pasta Pública determinar quais usuários e grupos têm acesso a arquivos compartilhados publicamente, bem como o nível de acesso desses usuários e grupos

### **Pastas compartilhadas**

Quando uma pasta é compartilhada, ela e todo o seu conteúdo são disponibilizados a vários usuários simultaneamente através da rede. As pastas compartilhadas mantêm um conjunto de permissões separado das permissões NTFS, que se aplica ao conteúdo da pasta.

Os usuários geralmente acessam uma pasta compartilhada através da rede usando seu endereço UNC (Convenção de Nomenclatura Universal). O endereço UNC contém o nome do servidor no qual a pasta está hospedada e o nome real da pasta compartilhada, separado por uma barra invertida (\) e precedida por duas barras invertidas (\\). Por exemplo, o caminho UNC da pasta compartilhada Marketing no servidor com nome EMPRESA-SERVIDOR é \\EMPRESA-SERVIDOR\Marketing.

### **Compartilhamento de uma pasta através da rede**

Para compartilhar uma pasta no Windows Server 2012, podemos proceder das seguintes maneiras:

- Clique na unidade apropriada e, na seção Serviços de Arquivo e Armazenamento no Gerenciador do Servidor, clique na tarefa Novo Compartilhamento.
- Use o Assistente de Compartilhamento de Arquivos no menu de atalho da pasta ou clicando no botão Compartilhar na guia Compartilhamento da caixa de diálogo Propriedades da pasta.
- Use Compartilhamento Avançado, clicando no botão Compartilhamento Avançado na guia Compartilhamento da caixa de diálogo Propriedades da pasta.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261587/14228.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261587/14228.PNG)

Figura 1: Compartilhamento de pasta

### **Permissões de pasta compartilhada**

Podemos atribuir as permissões de pasta compartilhada a usuários, grupos ou computadores, e essas permissões são aplicadas a todo o conteúdo da pasta compartilhada para os usuários que acessam a pasta através da rede.

Toda vez quem criamos uma pasta compartilhada, a permissão padrão para essa pasta compartilhada será Ler para o grupo Todos.

Observe as permissões associadas a pasta compartilhada.

![[Screenshot_from_2022-03-31_00-59-54.png]]

### **Permissões NTFS**

As permissões NTFS são atribuídas a arquivos ou pastas em uma unidade de armazenamento formatada com o NTFS. As permissões atribuídas a arquivos e pastas NTFS controlam o acesso do usuário a esses arquivos e pastas.

Os pontos a seguir, segundo a Microsoft (MICROSOFT, 2012) descrevem os principais aspectos das permissões NTFS:

- As permissões NTFS podem ser configuradas para um arquivo ou uma pasta individual ou para conjuntos de arquivos ou pastas.
- As permissões NTFS podem ser atribuídas individualmente a objetos que incluem usuários, grupos e computadores.
- As permissões NTFS são controladas negando ou concedendo tipos específicos de acesso a arquivos e pastas NTFS, como Leitura ou Gravação.
- As permissões NTFS podem ser herdadas de pastas pai. Por padrão, as permissões NTFS atribuídas a uma pasta também são atribuídas a pastas ou arquivos recém-criados dentro dessa pasta pai.

### **Permissões NTFS padrão**

As permissões padrão fornecem as configurações de permissão usadas com mais frequência para arquivos e pastas. As permissões padrão são atribuídas na janela Atribuição de Permissões NTFS.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261588/14230.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261588/14230.PNG)

Figura 2: Propriedades e permissões NTFS

Observe as permissões associadas a arquivos e pastas NTFS.

![[Screenshot_from_2022-03-31_01-01-07.png]]

### **Arquivos off-line**

Um arquivo offline é uma cópia de um arquivo de rede armazenado em um computador cliente. A utilização de arquivos offline permitirá que os usuários acessem arquivos baseados em rede quando seu computador cliente for desconectado da rede.

Os arquivos e as pastas offline serão editados ou modificados pelo cliente e as alterações serão sincronizadas com a cópia de rede dos arquivos na próxima vez que o cliente se reconectar à rede. O agendamento da sincronização e o comportamento dos arquivos offline são controlados pelo sistema operacional cliente Windows.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261589/14240.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261589/14240.PNG)

Figura 3: Configurações para arquivos offline

Visualize a janela Configurações Offline para uma pasta compartilhada, clicando no botão Cache na janela Compartilhamento Avançado.

### **Gerenciando cotas de disco**

Mesmo com as grandes unidades de disco disponíveis atualmente, muitas vezes o espaço disponível no disco rígido deve ser controlado. Nesse contexto, que as cotas de disco são muito importantes, pois esse recurso ajuda a gerenciar e definir um limite de uso espaço em disco.

### **Como funciona o gerenciamento de cotas**

Usando cotas de disco, podemos monitorar e controlar a quantidade de espaço em disco que as pessoas utilizam quando acessam suas pastas. Sem o gerenciamento de quotas, é difícil controlar a quantidade de espaço a ser utilizado por usuários e ainda é mais difícil controlar a quantidade total de espaço que eles podem usar. Para utilizar o gerenciamento de cotas, devermos fazer o seguinte:

Configurar o sistema de quotas de disco para monitorar apenas o uso de espaço em disco, permitindo que os administradores verifiquem o uso de espaço em disco manualmente.

Configure o sistema de cota de disco para monitorar o uso de espaço em disco e gerar avisos quando os usuários excederem os níveis de utilização predefinidas.

Configure o sistema de cota de disco para monitorar o uso de espaço em disco, gerar avisos quando os usuários excederem os níveis de utilização predefinidas, e fazer cumprir os limites ao negar espaço em disco aos usuários que excedem o limite de cota.

As cotas de disco são configuradas por volume (disco). Quando ativamos as quotas de disco, todos os usuários que armazenam dados em um volume serão afetados pela quota. Porém podemos definir exceções para usuários individuais e estabelecer novos limite.

Visualize as Cotas de disco através das propriedades do disco, através da guia Cota.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261590/14244.PNG)](https://img.uninove.br/static/0/0/0/0/0/0/0/2/6/1/5/261590/14244.PNG)

Figura 4: Propriedades de disco local.