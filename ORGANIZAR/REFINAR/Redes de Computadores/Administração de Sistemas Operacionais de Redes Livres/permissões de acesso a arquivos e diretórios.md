### Comandos de controle de acesso.

Quando listamos o diretório com o comando “ls” opção -l, ou seja, forma longa, podemos ver na primeira coluna aparecem as permissões. Segue abaixo esta representação. Em seguida vamos entender como manipular estas informações.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/7/836758/36600.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/7/836758/36600.png)

**chmod [options] mode filename**

Este comando muda as permissões de um **arquivo/diretório.**

No Linux e outros sistemas operacionais semelhantes ao Unix, há um conjunto de regras para cada arquivo que define quem pode acessá-lo e como eles podem acessá-lo. Essas regras são chamadas de permissões de arquivos ou modos de arquivo. O nome do comando chmod significa "_**change mode**_” (mudar o modo) e é usado para definir a maneira como um usuário pode ser acessado [2].

Em geral, os comandos chmod assumem a forma:

**chmod -opções permissões nome-do-arquivo/nome_do_diretório**Se nenhuma opção for especificada, o chmod modifica as permissões do arquivo especificado pelo nome do arquivo para as permissões especificadas por permissões.**Permissões** define as permissões para o proprietário do arquivo (o _**user**_), membros do mesmo grupo do proprietário (o _**group**_) e qualquer outra pessoa (_**other**_). Existem duas formas de representar estas permissões: com símbolos (caracteres alfanuméricos) ou com número octal (os dígitos de 0 a 7). Está em octal, mas a origem é binários.Digamos que você é o proprietário de um arquivo chamado testblob.py e deseja definir suas permissões para que:    O usuário possa ler, escrever e executá-lo;    Os membros do seu grupo podem lê-los e executá-los; e    Outros só podem lê-lo.Este comando fará o que desejamos:**chmod  u = rwx, g = rx, o = r   testblob.py**Este exemplo usa a notação de permissões simbólicas. As letras u, g e o representam "usuário", "grupo" e "outro". O sinal de igual ("=") significa "definir as permissões exatamente como este", e as letras "r", "w" e "x" significam "read", "write" e "execute", respectivamente. As vírgulas separam as diferentes classes de permissões e não há espaços entre elas.Aqui está o comando equivalente usando notação de permissões octal:**chmod 754 testblob.py**Aqui os dígitos 7, 5 e 4 representam individualmente as permissões para o utilizador, grupo e outros, nessa ordem. Cada dígito é uma combinação dos números 4, 2, 1 e 0:    4 significa "ler",    2 significa "escrever",    1 significa "executar", e    0 significa "sem permissão".Então 7 é a combinação de permissões 4 + 2 + 1 (ler, escrever e executar), 5 é 4 + 0 + 1 (ler, não escrever e executar), e 4 é 4 + 0 + 0 (ler, não Escrever e não executar).

Agora podemos explicar porque o octal vem do binário. Se você lista o diretório verá na primeira coluna o modo do arquivo como mostrado abaixo. Colocando 1 para se a permissão foi dada e 0 se não foi dada a permissão fica:

rwx  r- x  r - -

111 101  100

Transformando cada grupo binário de 3 dígitos acima podemos ver o 754 (como no comando acima). Veja agora o exemplo na prática abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836837/36602.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836837/36602.png)

Observe que o arquivo até mudou de cor para verde, algo característico do comando “ls” mostrando que o mesmo virou um executável.

Talvez você esteja preocupado com o tracinho (-) na frente das permissões. Ali está um espaço reservado para informar se aquela linha está representando um arquivo (-) ou um diretório (d) ou um link (l). Não se preocupe com isto agora.

Vamos ver como seria o mesmo comando usando letras.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836841/36603.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836841/36603.png)

Na tabela abaixo pode-se ver um grupo de exemplos que fará você memorizar o uso das permissões.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/4/3/874343/36604.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/7/4/3/874343/36604.png)

Com o tempo você irá ficar muito prático na escolha dos números. A maioria dos usuários experientes usam a forma octal.

Além do chmod que muda as permissões, podemos mudar o proprietário do arquivo e o grupo do qual o arquivo pertence.

Antes disso, porém, vamos te que ter mais poder sobre nossas operações. Para isto não basta ser um usuário comum.

### Tornando-se o superusuário por um curto tempo

Conforme observado em [1], muitas vezes é útil se tornar o superusuário para executar tarefas importantes de administração do sistema, mas como você já devia estar avisado, você não deve permanecer conectado como o superusuário, isso é perigoso. Na maioria das distribuições, existe um programa que pode fornecer acesso temporário aos privilégios do superusuário. Este programa é chamado su (abreviação de usuário substituto) e pode ser usado nesses casos quando você precisa ser o superusuário para um pequeno número de tarefas. Para se tornar o superusuário, basta digitar o comando “su”. Você será solicitado a fornecer a senha do superusuário. Veja como é feito na figura abaixo. Para sair do privilégio root, aplique o programa “exit”.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836870/36605.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836870/36605.png)

Observe que o prompt mudou para “#” e antes estava “$”. O prompt de superusuário é #.

Perceba abaixo que se eu comandar “exit” volto a não ter privilégios de root.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836875/36606.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836875/36606.png)

Agora você está pronto para os próximos comandos:

**chown [options] filename/dirname**

Muda quem é o proprietário do arquivo. Veja no exemplo abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836880/36607.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836880/36607.png)

Observe que troquei o proprietário luckgav para root. Também perceba que tive que usar um usuário privilegiado com o comando “sudo”, isto eu explico mais para frente. Assim, nem precisei virar superusuário.

**chgrp [options] filename**

Muda o grupo de quem pertence o arquivo. Veja no exemplo abaixo.

[![](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836886/36608.png)](https://img.uninove.br/static/0/0/0/0/0/0/0/8/3/6/8/836886/36608.png)

Observe que tentei mudar o grupo, mas não tinha autoridade para isso. Precisei me tornar um superusuário.

### Conclusão

Você precisa manter seus arquivos e diretórios protegidos da melhor maneira possível. Sempre pense, ao criar um arquivo, que a segurança de seu sistema pode ser comprometida pelo acesso a este arquivo. Procure colocar as permissões de forma a compatibilizar acesso e segurança ao mesmo tempo. **Lembrando que todos os comandos de permissões valem para diretórios.**