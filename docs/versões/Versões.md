# Histórico de Versões

Essa seção ficará responsável por descrever as atualizações feitas durante as semanas com o _Sprint_ relativo ao projeto R.U.N.A. Os registros específicos feitos pelos contribuidores do Projeto podem ser verificados no GitHub: [https://github.com/Ak4ai/TasksApp](Github R.U.N.A).

---


## Oitava Release (25/06/25 - 02/07/25)

**Responsáveis pelo desenvolvimento desta versão:** Henrique de Freitas, João Pedro Rodrigues e Pedro Augusto

**Responsáveis pela documentação desta versão:** Jader Oliveira, Rafael Adolfo, Rafael Ferreira e Samuel Silva

A equipe passou uma semana a mais desenvolvendo o projeto para polir e acrescentar features novas ao mesmo tempo em que organizamos os documentos do trabalho final.Como nas últimas semanas, a interface foi polido, mais conteúdo foi adicionado e houveram correções visuais e de bugs, especialmente no sistema de combate e em um novo sistema de dano nos inimigos. Vale ressaltar que a equipe encontrou uma boa forma de adicionar informações dentro do app através de uma aba própria e a visualização de informações em áreas como a da troca de classes;

No geral, concluímos que o aplicativo está em um bom estágio de desenvolvimento e features, com a prioridade voltada agora para correção de bugs, pequenas features, atualização da documentação e a possibilidade de adcionar artes originais para o R.U.N.A.

**Metas da Semana:**
- Finalizar funções (missão com amigos, edição de tarefas);
- Polimento e melhorias visuais;
- Preparar o programa para a fase de testes.

---


## Sétima Release (09/06/25 - 16/06/25)

**Responsáveis pelo desenvolvimento desta versão:** Henrique de Freitas, Jader Oliveira e Pedro Augusto

**Responsáveis pela documentação desta versão:** João Pedro Rodrigues, Rafael Adolfo, Rafael Ferreira e Samuel Silva

No preparo para a release, ficou claro que as metas da última release foram mais do que cumpridas, features extras foram implementadas e foi a semana mais bem documentada. Por isso, revisamos o que fizemos de mais importante na última semana.

Além disso, planejamos em manter o foco em finalizar as features funcionais estabelecidas para depois focar inteiramente na UI do app, mas também discutimos feedbacks na interface para as próximas versões (especialmente no ambiente mobile), como a possibilidade de adicionar uma barra lateral. Também discutimos como adicionar informações importantes e tutoriais dentro do app e planejamos criar artes oficiais para o R.U.N.A para o momento de foco na UI.

***Metas da Semana:***

* **Avançar mais o desenvolvimento das features funcionais**

* **Continuar o desenvolvimento do sistema de amizade**

* **Terminar o sistema de combate**

* **Estudar como implementar tutoriais in-app**

### 📄 Changelog da Release:

**Adições gerais:**

- Novas missões diárias;
- Imagens do inimigos sem fundo;
- Modal de missão com botão de trocar;
- Adição do ataque especial;
- Novos backgrounds e animações;
- Botão de ajuda na topbar;
- Ajustes no inventário e modais de tarefas;

**Organização de informação das classes:**

- Sublinhado abaixo da classe informando seus bônus;
- Informação dos bônus da classe na tela de troca

**Correções de bugs:**

- Corrigidos bugs nas moedas;
- Correção de sprites;
- Ajustes no visual dos modais

---


## Sexta Release (02/06/25 - 09/06/25)

**Responsáveis pelo desenvolvimento desta versão:** Jader Oliveira, João Pedro Rodrigues, Pedro Augusto e Henrique de Freitas

**Responsáveis pela documentação desta versão:** Rafael Adolfo,  Rafael Ferreira e Samuel Silva

Durante a reunião de acompanhamento da sexta semana, o foco foi voltado para a gameficação do projeto. Foi discutida a possibilidade de se implementar um sistema de inimigos ao R.U.N.A, de forma com que o usuário precise gerenciar a vida de seu personagem e tomar cuidado para não tomar penalidades por não cumprir tarefas. Além disso, a proposta de notificações mobile da última release começou a se encaminhar, mas ainda precisa de melhorias.

A equipe concluiu que o projeto chegou em um estágio de desenvolvimento bom o suficiente para começar a fase de testes. Não houve uma definição formal, mas chegaram a um acordo do uso acompanhado das releases mais recentes para gerar relatórios de erros e bugs a serem consertados.

Com isso, as metas de desenvolvimento da semana foram:

- **Aprofundar a gameficação:** Isso seria feito através da implementação da mecânica de combate com inimigos, além da adição de mais itens e upgrades para o personagem.

- **Polir as notificações do aplicativo**: Além de continuar o desenvolvimento da release passada, seria preciso estudar maneiras de fazer as notificações funcionarem bem para diferentes tipos de dispositivos (por exemplo, testar as notificações no iPhone).

- **Testar o aplicativo**: Uso das releases recentes por parte dos desenvolvedores para gerar relatórios de erros e bugs, como citado anteriormente.

### 📄 Changelog da Release:

**Implementação do multiplayer (sistema de amizade):**

- Início da implementação do ID para o multiplayer
- Criação do sistema de amizade
- Modal de amigos e possibilidade de desfazer amizade
- Nova info dos amigos

**Organizações visuais:**

- Ícone de carregando interface
- Organização de interface geral
- Organização de interface de inventário
- Atualização de ícones
- ID simplificado na topbar e com mensagem nas configurações

**Implementação de inimigos e combate:** 

- O usuário causa dano ao inimigo completar tarefas 
- Inimigos causam dano quando tarefas expiram 
- O usuário recebe grande quantidade de XP e moedas ao derrotar um inimigo
- Diversificação de inimigos
- Sistema de progressão de inimigos
- Aba de combate contra Inimigos
- Adição da mecânica de itens no combate
- Ajuste na defesa do combate e seção de proteção na loja

**Novas mecânicas e features adicionais:**

- XP agora é carregado no Firestore
- Adição de novas Classes
- Reimplementação do bônus de XP das Classes
- Adição de Cooldown para Mudança + Item que retira Cooldown
- Implementação de missões diárias

**Correções de bugs:**

- Correção de bugs na UI
- Correção de bugs no sistema das moedas
- Algumas correções de bugs no sistema de amizade

---


## Quinta Release (26/05/25 - 02/06/25)

**Responsáveis pelo desenvolvimento desta versão:** João Pedro Rodrigues, Pedro Augusto e Henrique de Freitas

**Responsáveis pela documentação desta versão:** Jader Oliveira, Rafael Adolfo,  Rafael Ferreira e Samuel Silva

Na reunião de acompanhamento da quinta semana, percebemos que o projeto estava bastante encaminhado, e as propostas para esse ciclo não fogem do que foi proposto nas últimas duas releases. Isso significa que ainda existe foco na interface de usuário e nos sistemas voltados à gameficação do R.U.N.A, seja atualizando os que já começaram a ser implementados como solidificando a base para novos.

Com isso, as metas da semana foram:

- **Continuar atualizações na interface do usuário**: A proposta de vez foi em implementar um calendário com tarefas na página inicial da plataforma.

- **Melhorar a gameficação**: Adicionar novos itens para uso do personagem do usuário, incluindo placeholders de ícones para melhorias na interface visual. Esses novos itens incluem tanto utilitários quanto cosméticos para o personagem.

- **Continuar melhorando o tipo personalizado**: Foi proposto incluir novas customizações de tarefa e mais opções de tipos de frequência nelas.

- **Integrar notificações na versão mobile**: Uma proposta interessante e que foi discutida no acompanhamento: é uma prioridade, mas que provavelmente vai durar mais ciclos de desenvolvimento para ser devidamente immplementada.

---


## Quarta Release (19/05/25 - 26/05/25)

**Responsáveis pelo desenvolvimento desta versão:** João Pedro Rodrigues, Pedro Augusto e Henrique de Freitas

**Responsáveis pela documentação desta versão:** Jader Oliveira, Rafael Adolfo,  Rafael Ferreira e Samuel Silva

A reunião de acompanhamento da quarta semana foi focada na necessidade de continuar o desenvolvimento das features implementadas na Terceira Release. O ciclo de desenvolvimento anterior terminou com implementação de melhorias visuais, sistemas básicos para gerenciamento de arquivos e abas por tipo de tarefa, além da criação da logo oficial do aplicativo. Portanto, foi decidido manter o foco nas melhorias visuais e de interface, mas sem deixar de adicionar a base de alguns outros sistemas.

As metas estabelecidas para esse ciclo de desenvolvimento foram

- **Atualizar interface do usuário**: Parte da prioridade dessa semana em continuar implementando melhorias visuais;
- **Adcionar sistema de tags**: Embora classificado como baixa prioridade na release passada, foi estudado pelos desenvolvedores que a implementação seria necessária para complementar a base do sistema de classes e a interface visual das tarefas.
- **Criar a base do sistema de classes**: Permitir com que o usuário use as classes como um foco para tipos de atividades específicas, com bônus de experiência com base nas tags associadas a uma tarefa.
- **Melhorar o tipo personalizado**: Focar as melhorias pensando na inclusão do sistema de tags.
- **Melhorar anexos em tarefas**: Foco em melhorar a integração do Firebase com o restante do sistema para anexar as tarefas.

---

## Terceira Release (12/05/25 - 19/05/25)

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

## Segunda Release (05/05/25 - 12/05/25)

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

## Protótipo Inicial (28/04/25 - 05/05/25)


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

- **Logar**. Dessa maneira, através da API de Login da Google, tornou-se possível armazenar os dados (tarefas e preferências do usuário).
- **Criar Tarefas** (que erão distribuidas entre dois blocos, um para tarefas ainda não realizadas e outro para tarefas realizadas). As tarefas eram contabilizadas como realizadas quando a data selecionada para a mesma era ultrapassada.
- **Modificar e Excluir Tarefas**. Havia a possibilidade de modificar a data selecionada para a tarefa, junto a sua descrição, bem como excluir a mesma.
- **Deslocar-se pelas abas**. Tentou-se dentro do _R.U.N.A_ implementar uma interface interativa associada a dois parâmetros: necessidade de organização das tarefas de acordo com a prefência do usuário e priorizar a utilização em dispositivos móveis através de deslocamentos horizontais em abas distintas. Além disso a interface possuia duas barra, uma no topo que demonstrava o nome do usuário, junto a data e um contador relativo a próxima tarefa em tempo.
 

---

