[![](https://ampli-images.s3.amazonaws.com/production/760562c1-9a3b-4146-a338-a8f2fa54fb5a/original)](https://ampli-images.s3.amazonaws.com/production/760562c1-9a3b-4146-a338-a8f2fa54fb5a/original)

O Packet Tracer é um software muito interessante que nos permite planejar, testar e ajustar as redes de computadores conforme as necessidades e a disponibilidade de equipamentos e tecnologias. Para entender a potencialidade desse software, suas características e o funcionamento dos equipamentos de redes de computadores, observe um exemplo na figura a seguir e crie um primeiro projeto, simples, para um departamento administrativo de uma pequena empresa.

Escolha os dispositivos de rede, arraste-os para a área de trabalho do software, em seguida, clique duas vezes no dispositivo e explore as características de cada dispositivo de rede. Por fim, você verá como o sistema é interessante ao trazer as características reais de cada equipamento e as possibilidades de simulação da rede.

[![](https://ampli-images.s3.amazonaws.com/production/0f4ba278-f0e2-40df-ba9a-e3e3272c65bd/original)](https://ampli-images.s3.amazonaws.com/production/0f4ba278-f0e2-40df-ba9a-e3e3272c65bd/original)

Nesse exemplo, foram utilizados os seguintes dispositivos para compor uma rede de computadores simples de um pequeno escritório administrativo: um servidor de rede, um switch 24 portas, uma impressora, três estações de trabalho desktops, um roteador _wireless_ e três smartphones. Naturalmente, o volume de estações de trabalho e smartphones pode ser acrescido na topologia conforme as necessidades e capacidades dos _switches_ e roteadores disponíveis no Packet Tracer.

O Packet Tracer é uma ferramenta que nos permite colocar em prática os estudos de redes de computadores. Embora a aplicação seja fácil de operar e intuitiva, o conhecimento de suas principais funcionalidades o auxiliará no desenvolvimento de topologias de redes de computadores. Observe a interface do Packet Tracer na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/6d3062d6-ce11-4bc2-b366-9ac2bb58b390/original)](https://ampli-images.s3.amazonaws.com/production/6d3062d6-ce11-4bc2-b366-9ac2bb58b390/original)

Interface do Packet Tracer. Fonte: captura de tela elaborada pelo autor.

Onde,

1. **Área de funcionalidades**: idêntico à maioria dos programas em Windows. Na parte superior, é possível salvar, abrir e alterar pequenas configurações.
2. **Atalhos: na parte inferior**: algumas figuras geométricas e atalhos das configurações.
3. **Área de edição**: espaço reservado para desenvolver as topologias.
4. **Seleção de categoria**: essa área está dividida por categoria: _network devices_ (nós de redes), end devices (computadores, servidores etc), componentes (antenas), conexões (cabeamentos), _miscelanius_ (vários dispositivos misturados) e connection (simuladores de cloud).
5. **Seleção de subcategoria**: após selecionar uma categoria é possível escolher uma subcategoria. Por exemplo: ao selecionar a categoria _Network Devices_, na subcategoria será possível selecionar roteador, switch, hub, wireless device, security e wan emulation.
6. **Seleção de Equipamentos**: ao selecionar uma sub-categoria, todos os equipamentos disponíveis são apresentados nessa área da interface.

**Equipamentos**

Para colocar os equipamentos na área de edição, é necessário clicar neles, segurá-los e arrastá-los até o local desejado (Drag and drop). Após posicionar os equipamentos, é a hora de ligá-los por meio de cabeamento, conforme a figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/96e4afe0-5bb9-495f-8cdd-5419644abaee/original)](https://ampli-images.s3.amazonaws.com/production/96e4afe0-5bb9-495f-8cdd-5419644abaee/original)

Ligação de cabos. Fonte: captura de tela elaborada pelo autor

**Interface**

Inicialmente, na área de categoria, deve ser selecionado o cabeamento (representado por um raio); em seguida, o cabo adequado. Então, é só clicar no dispositivo e escolher a interface de rede em ambos os equipamentos que se deseja efetuar a comunicação. Ainda é possível fazer a configuração dos equipamentos ao dar um clique no equipamento. Observe o exemplo de um computador na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/9f7072a8-407d-4b45-8039-d32959f8743e/original)](https://ampli-images.s3.amazonaws.com/production/9f7072a8-407d-4b45-8039-d32959f8743e/original)

Exemplo de interface.Fonte: captura de tela elaborada pelo autor

**Interface de rede**

Para atribuir endereço IP para os computadores, existem duas possibilidades: manualmente e via DHCP (servidor de endereço IP). Para isso, clique em IP Configuration (primeira opção da figura anterior). Ao selecionar a opção DHCP, o servidor (nessa topologia o roteador) enviará o endereço à interface de rede. Já para atribuir o endereço manualmente, observe a figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/7ce4f249-2837-4f27-93a3-af0f6799a021/original)](https://ampli-images.s3.amazonaws.com/production/7ce4f249-2837-4f27-93a3-af0f6799a021/original)

Exemplo de interface de rede. Fonte: captura de tela elaborada pelo autor

_**Command Propmt**_

Ainda é possível utilizar a versão nova do IP, o IPv6. Após todos os computadores possuírem endereço, é possível efetuar o teste de conexão PING. Para isso, anote um endereço IP de um dos computadores, acesse a interface do computador e clique em Command Prompt, por fim, digite o comando: ping endereçoIP. Por exemplo: ping 192.168.0.103. Observe um exemplo na figura a seguir.

[![](https://ampli-images.s3.amazonaws.com/production/fb1ff05a-9526-4a0b-bc2d-5ec4f96eff28/original)](https://ampli-images.s3.amazonaws.com/production/fb1ff05a-9526-4a0b-bc2d-5ec4f96eff28/original)

Exemplo de comando PING. Fonte: captura de tela elaborada pelo autor