# Home

![Logo](logo-runa-site.png){width="300"}

## Bem-vindo ao R.U.N.A.!

O **R.U.N.A.** — *Rotina Unificada Naturalmente Automatizada* — é um aplicativo inovador focado em transformar a forma como os usuários organizam suas tarefas diárias. Com uma proposta leve, interativa e totalmente gamificada, o projeto visa unir produtividade e motivação, criando um ambiente onde cada tarefa concluída representa uma conquista.

Mais do que um simples gerenciador de afazeres, o R.U.N.A. oferece uma experiência que valoriza o progresso do usuário, integrando recompensas, níveis e desafios em um sistema visual intuitivo. A ideia é clara: fazer com que a rotina se torne algo envolvente, onde o cumprimento de metas diárias contribui não apenas para organização pessoal, mas também para a evolução dentro de um universo simbólico e divertido.

Com recursos como autenticação de usuário, criação de tarefas por tipo (personalizadas, periódicas ou pontuais), possibilidade de anexar arquivos e visualização organizada por abas, o app busca facilitar o dia a dia sem deixar de lado a estética e a experiência do usuário.

Seja bem-vindo à sua nova forma de realizar tarefas. Seja bem-vindo ao universo R.U.N.A.

---

## Integrantes da E7 Studios

- Henrique de Freitas Araújo (ricosgames.henrique@gmail.com)
- Jader Oliveira Silva (jaderoliveira28@gmail.com)
- João Pedro Rodrigues Silva (jprs1308@gmail.com)
- Pedro Augusto Gontijo Moura (pedroaugustomoura70927@gmail.com)
- Rafael Adolfo Silva Ferreira (rafael.ferreira11.98@gmail.com)
- Rafael Ferreira da Rocha (rafaelrocha241003@gmail.com)
- Samuel Silva Gomes (silvagomes881@gmail.com)

## Histórico de Versões

Essa seção ficará responsável por descrever as atualizações feitas durante as semanas com o _Sprint_ relativo ao projeto R.U.N.A. Os registros específicos feitos pelos contribuidores do Projeto podem ser verificados no GitHub: [https://github.com/Ak4ai/TasksApp](Github R.U.N.A).

---

### Protótipo Inicial (28/04/25 - 05/05/25)


O protótipo inicial foi concebido com o objetivo de demonstrar a estruturação básica necessária para a criação, organização e gerenciamento de tarefas personalizadas por parte do usuário. Esta etapa visa apresentar ao orientador e demais avaliadores a proposta inicial da interface gráfica, bem como validar a separação modular dos arquivos responsáveis pelas funcionalidades do sistema.

A seguir, descreve-se a estrutura modular adotada, com os arquivos principais e suas respectivas responsabilidades no projeto:

* **`index.html`**: Arquivo principal da interface gráfica. Responsável por estruturar os elementos HTML visíveis ao usuário, como campos de entrada de dados, botões, layout das tarefas e containers para exibição de mensagens e feedbacks.

* **`style.css`**: Define o estilo visual da aplicação, organizando cores, espaçamentos, tipografia, transições e responsividade. Sua modularização permite separar completamente o design do funcionamento lógico do sistema.

* **`auth.js`**: Módulo responsável pela autenticação do usuário via Firebase Authentication. Implementa funcionalidades como login com conta Google, logout e persistência da sessão do usuário.

* **`firebase-config.js`**: Arquivo de configuração do Firebase. Centraliza as credenciais e inicializa os serviços de banco de dados (Firestore), autenticação e demais recursos necessários da plataforma.

* **`script.js`**: Controla funcionalidades de interface gerais, como manipulação de eventos de botões, interações com o DOM e chamadas de funções utilitárias para o comportamento geral do aplicativo.

* **`tarefas.js`**: É o núcleo da lógica de tarefas. Este módulo gerencia a criação, visualização, marcação como concluída, edição e exclusão de tarefas, além de implementar a lógica de recorrência (tarefas periódicas) e atualização em tempo real da interface com base nos dados armazenados no Firestore.

* **`service-worker.js`**: Responsável por implementar o comportamento offline e o cache da aplicação. Este arquivo é parte fundamental da conversão do projeto em uma Progressive Web App (PWA), garantindo que o aplicativo funcione mesmo na ausência de conexão com a internet.

A modularização proposta permite melhor organização do código, facilita manutenções futuras e oferece flexibilidade para expansão das funcionalidades do sistema. Além disso, cada módulo possui uma responsabilidade única e bem definida, respeitando o princípio de *separação de preocupações*, amplamente adotado no desenvolvimento de aplicações modernas baseadas na arquitetura Web.

Esta versão inicial já possibilitava ao usuário:
- Logar. Dessa maneira, através da API de Login da Google, tornou-se possível armazenar os dados (tarefas e preferências do usuário).
- Criar Tarefas (que erão distribuidas entre dois blocos, um para tarefas ainda não realizadas e outro para tarefas realizadas). As tarefas eram contabilizadas como realizadas quando a data selecionada para a mesma era ultrapassada.
- Modificar e Excluir Tarefas. Havia a possibilidade de modificar a data selecionada para a tarefa, junto a sua descrição, bem como excluir a mesma.
- Deslocar-se Pela Abas. Tentou-se dentro do _R.U.N.A_ implementar uma interface interativa associada a dois parâmetros: necessidade de organização das tarefas de acordo com a prefência do usuário e priorizar a utilização em dispositivos móveis através de deslocamentos horizontais em abas distintas. Além disso a interface possuia duas barra, uma no topo que demonstrava o nome do usuário, junto a data e um contador relativo a próxima tarefa em tempo.
 

---


### Segunda Release (05/05/25 - 12/05/25)

**Responsáveis pelo desenvolvimento desta versão:** Henrique de Freitas, Jader Oliveira, João Pedro Rodrigues e Samuel Silva
**Responsáveis pela documentação desta versão:** Pedro Augusto, Rafael Adolfo e Rafael Ferreira

Durante a reunião inicial que precedeu esta semana de desenvolvimento da segunda versão do R.U.N.A, muito foi-se discutido acerca da disposição do software, principalmente sobre as necessidades que deveriam ser atendidas de imediato para um melhor arranjo dos módulos do programa em si. Criou-se um diagrama de usuário como "guia" para os desenvolvedores ao longo do projeto. Assim, para essa primeira semana de desenvolvimento após o protótipo, tinha-se como objetivo: 

> Implementar a tipagem de tarefas (Importantes Periódicas, Importantes Não-Periódicas, Personalizadas) visando futuramente integrar-se com o sistema de 'tags' para tarefas.

> Ajustar a frequência selecionada pelo usuário para a recorrência de tarefas periódicas e personalizadas suprindo as necessidades impostas pelo mesmo. 

Então, ao fim do período de desenvolvimento, tinha-se implementado dentro do programa:

- **Tipagem de Tarefas:** A tipagem de tarefas foi exatamente como aquela prevista (Importante Periódica, Importante Não-Periódica e Personalizada). Porém, o tipo personalizado ainda havia uma menor capacidade de conceder liberdade ao usuário durante a manipulação desta tarefa ao seu gosto. Além disso, as tarefas eram depostas em novos blocos de acordo com a sua tipagem.

- **Sistema de Conclusão de Tarefas:** Agora as tarefas possuem um _checkbox_ do qual ao selecionar esta passa a ser concluida, concedendo _XP_ ao usuário além de movendo-a para um bloco de tarefas concluidas. Caso a data limite selecionada da tarefa fosse ultrapassada, esta então contaria como uma tarefa expirada.

- **Sistema de XP e Pequena Interface do Futuro Personagem:**  Iniciou-se a gameficação do projeto, apresentando um contador de _XP_ para o usuário associado a um nível com base em quanto dessa experiência você acumula. Essa interface fica presente em todas abas enquanto apresentava uma imagem de placeholder para a futura personagem do usuário.

- **Frequência de Tarefas:** A frequência foi implementada para repor tarefas importantes periódicas além das personalizadas (esta, por sua vez, ainda carentes de um sistema mais amplo). A

- **Melhoria do Contador de Tarefa:** O contador de tarefa sempre demonstra a tarefa mais próxima, independente do tipo, além de quando ser clicada demonstrar todas tarefas (ainda não realizadas, expiradas e concluidas) com a possibilidade de organiza-las por tipo ou por ordem (padrão).

- **Mudanças na Interface/Gerais:** Pequenas mudanças visuais, como a criação de abas para cada tipo de tarefa, mudanças na coloração, ao passar o mouse por cima demonstra o tipo de tarefa junto a uma pequena tag, melhoria na aba de configurações e polimento na lógica.

---

### Terceira Release (12/05/25 - 19/05/25)

**Responsáveis pelo desenvolvimento desta versão:** Henrique de Freitas, Pedro Augusto e Rafael Ferreira
**Responsáveis pela documentação desta versão:**  Rafael Adolfo, Jader Oliveira, João Pedro Rodrigues e Samuel Silva

Durante a reunião de acompanhamento da terceira semana, alguns pontos críticos e sugestões importantes foram destacados pela equipe. Em especial, ressaltou-se a dificuldade relacionada à obrigatoriedade do uso do Firebase como ferramenta de persistência de dados, o que impacta diretamente na flexibilidade de testes e no tempo de desenvolvimento. Apesar de ser uma solução prática para autenticação e banco de dados em tempo real, o acoplamento do projeto à plataforma exigiu uma curva de aprendizado mais acentuada, principalmente em tarefas como autenticação, armazenamento de arquivos e atualização de documentos aninhados.

Outro ponto abordado diz respeito à nova rotação de membros na equipe de desenvolvimento. A chegada de novos colaboradores ao projeto exigiu uma reorganização do código e melhor documentação das funcionalidades já implementadas. Para isso, conselhos e práticas voltadas à estruturação modular do código foram enfatizados, visando facilitar a assimilação da base existente e evitar bugs causados por más interpretações da lógica previamente desenvolvida.

Nesta etapa, o foco principal está na consolidação e evolução das funcionalidades centrais já implementadas, com destaque para:

* **Aprimoramento das abas por tipo de tarefa**: Embora a separação por categorias (periódica, não-periódica e personalizada) tenha sido introduzida na segunda release, sua implementação ainda pode ser melhorada em termos de UX e organização visual. A meta é tornar essa divisão mais intuitiva e com feedbacks mais claros para o usuário.

* **Melhoria das tarefas do tipo “personalizado”**: O objetivo é permitir que este tipo de tarefa opere de forma mais livre, inclusive removendo a obrigatoriedade do checkbox de conclusão. Isso é relevante para tarefas que não seguem um fluxo tradicional de "fazer e concluir", como lembretes contínuos ou metas abertas.

* **Anexação de arquivos às tarefas**: Uma funcionalidade altamente solicitada é a capacidade de associar arquivos diretamente às tarefas. Esta feature começa a ser prototipada nesta semana, utilizando o armazenamento do Firebase como backend para upload e download de documentos e imagens.

* **Baixa prioridade para sistema de tags**: Apesar de útil para a categorização das tarefas, a implementação do sistema de tags foi considerada menos urgente no momento. Seu desenvolvimento será postergado para releases futuras, após a consolidação das funcionalidades críticas.

* **Integração gradual com a gamificação do aplicativo**: O sistema de recompensas e níveis do app deve futuramente se beneficiar da introdução de tags e da definição de metas baseadas em hábitos. No entanto, nesta fase, a gamificação permanece em segundo plano e será revisitada apenas após as prioridades funcionais.

---

