# Introdução ao R.U.N.A

##  Sobre o Projeto R.U.N.A

###  **Objetivo do Projeto**

Criar um aplicativo mobile que ajude os usuários a organizarem melhor sua rotina, compromissos e tarefas do dia a dia, permitindo mais produtividade e controle do tempo.

## 🌟 Ideia Central do Projeto (Resumo)

> Criar um app de agenda que seja simples de usar, com visual moderno e que permita ao usuário **criar, organizar e acompanhar tarefas e compromissos** de forma eficiente. O app busca ser um “assistente pessoal leve”, voltado para estudantes e profissionais que precisam de mais organização, mas sem complicações. Além de elementos gameficados para um maior apelo com o público jovem.


###  **Principais Funcionalidades Planejadas**

- Cadastro/Login.
    
- Adicionar tarefas e manipular as mesmas para uma integração coerente com o usuário.
    
- Visualizar a agenda (organização das tarefas) em diferentes formatos.
    
- Auxiliar na criação rotinas e checklists.
    
- Receber lembretes e notificações acerca das tarefas criadas de acordo com a personalização do usuário.
    
- (Extras futuramente: integração com calendário do dispositivo e com os documentos do mesmo, modo foco, estatísticas)
    
##  Ferramentas Utilizadas no Projeto

###  **Desenvolvimento**

- **Visual Studio Code:** Ambiente de desenvolvimento, com
extensões para auxiliar na criação de software.

- **Java Script:** Linguagem de programação moderna e segura,
utilizada no desenvolvimento web e mobile.

- **HTML & CSS:** Como linguagens de marcação para estilização
front end do aplicativo.

###  **Controle de Versão**

- **Git + GitHub**: Controle de versões e colaboração no código-fonte.    

###  **Gerenciamento Ágil**

- **Mattermost**: Organização do backlog e tarefas das sprints.
        
- **Google Drive/Docs**: Armazenamento de arquivos e documentação compartilhada.
    

###  **Comunicação**

- **WhatsApp**: Comunicação rápida entre os membros da equipe.
    
- **Discord**: Reuniões do time, Sprint Reviews e Planning.
    

---


###  Como Priorizar?

Usou-se a técnica **MoSCoW** para organizar:

- **Must have** (essenciais): login, adicionar tarefas, visualização
    
- **Should have** (importantes, mas não essenciais agora): categorias, notificações
    
- **Could have** (desejáveis): pomodoro, estatísticas
    
- **Won’t have (por agora)**: integração com Google Calendar

### Possíveis Gastos Computacionais

A construção de um aplicativo de tarefas baseado em tecnologias Web, como HTML, CSS e JavaScript, implica na criação e manipulação dinâmica de múltiplos elementos de interface, especialmente estruturas _div_ . Essa prática, embora usual, exige atenção ao desempenho, uma vez que a renderização e reatividade desses elementos no navegador têm impacto direto na performance da aplicação, especialmente em dispositivos com recursos limitados, como smartphones mais antigos.

Com o crescimento funcional esperado — incluindo manipulação de tarefas, estilização visual, anexação de arquivos, integração com calendário e agenda, além de aspectos de gamificação — torna-se evidente a necessidade de uma arquitetura eficiente. A densidade de tarefas que um usuário pode acumular, aliada às interações dinâmicas (como marcar tarefas como concluídas, reorganizar prioridades e visualizar estatísticas) demanda uma abordagem otimizada tanto no front-end quanto no back-end, especialmente no gerenciamento e atualização do DOM.

Para oferecer um sistema de autenticação robusto e confiável, optou-se pela utilização do serviço de gerenciamento de identidade do Google Firebase. Essa escolha introduz camadas adicionais de complexidade relacionadas à segurança, modularidade e privacidade dos dados. O sistema precisa lidar com múltiplas sessões, permissões granulares e sincronizações em tempo real, o que exige um planejamento cuidadoso para evitar sobrecarga computacional, especialmente quando usuários estiverem simultaneamente ativos em dispositivos distintos.

A interface gamificada — composta por barras de progresso, níveis de experiência, recompensas visuais e outros elementos de motivação — traz uma camada adicional de complexidade visual e lógica. Tais elementos não apenas aumentam o consumo de recursos gráficos no navegador, mas também exigem ciclos de atualização constantes e armazenamentos intermediários (cache e sincronização com banco de dados), elevando o custo computacional e o número de requisições à nuvem.

Dessa forma, o desenvolvimento do aplicativo exige decisões arquitetônicas que equilibrem responsividade, eficiência de renderização, modularidade de código e escalabilidade. Técnicas como virtual DOM, debouncing em interações frequentes, lazy loading de componentes e compressão de assets tornam-se estratégias fundamentais para manter a fluidez e a experiência do usuário em alto nível.

### Possíveis Riscos e Soluções

Durante o desenvolvimento e a execução do aplicativo, diversos riscos técnicos podem comprometer sua eficiência e confiabilidade. Um dos principais desafios está relacionado à alta densidade de dados que o sistema pode acumular com o tempo, especialmente considerando tarefas periódicas. Esse crescimento pode acarretar em um aumento significativo no custo computacional, impactando diretamente no desempenho da aplicação, tanto no lado do cliente quanto no servidor.

Uma estratégia eficaz de mitigação consiste na personalização consciente e funcional das tarefas, bem como na implementação criteriosa da recriação automatizada de tarefas recorrentes. A lógica por trás dessa funcionalidade deve garantir que tarefas sejam recriadas apenas quando necessário, conforme a frequência previamente selecionada pelo usuário (diária, semanal, etc.), evitando execuções desnecessárias ou duplicações em massa. Dessa forma, o sistema tende a favorecer a criação de um conjunto reduzido de tarefas críticas para o dia a dia, ao mesmo tempo em que mantém flexibilidade para tarefas mais distantes no tempo.

A má implementação da lógica de recorrência representa um risco técnico elevado. Um algoritmo ineficiente, por exemplo, poderia gerar tarefas em cascata de forma exponencial, levando a problemas como estouro de memória ou lentidão sistêmica. Para mitigar tal cenário, o projeto adota uma estrutura modular, com código desacoplado e foco em otimizações de uso de memória e controle de chamadas assíncronas.

Além disso, a integridade dos dados do usuário é considerada prioridade crítica. A perda de dados comprometeria não apenas a confiança na aplicação, mas também sua utilidade prática. Por isso, o sistema se apoia em estratégias de sincronização com o Firebase, backup automático e autenticação segura para garantir a preservação das tarefas registradas, mesmo diante de falhas pontuais.

Embora ações de má-fé por parte de usuários estejam fora do escopo de controle direto, o game design adotado atua como ferramenta preventiva e motivacional. A proposta de recompensas simbólicas, acúmulo de experiência e metas internas visa transformar o cumprimento de tarefas em um desafio pessoal, promovendo o engajamento sem recorrer a práticas competitivas externas.

Dessa forma, os riscos foram mapeados e tratados com soluções específicas que visam garantir a escalabilidade, segurança e fluidez do software em contextos reais de uso.

### Possíveis ferramentas e frameworks.

- Vanilla Stack (HTML + CSS + Javascript)
- Node.js (para contato com servidor)
- ngrok (para testes com servidor)
- VS Code com Live Server (para desenvolvimento)
- API do Firebase (para o controle de databases)
- API do Google Authenticator (para autenticação de usuário)

### Divisões dos Membros da Equipe.

- Henrique (Desenvolvedor, Design Lead)
- Jader (Desenvolvedor/Tester)
- João Pedro (Desenvolvedor, Product Owner)
- Pedro (Desenvolvedor/Tester)
- Rafael Adolfo (Desenvolvedor, Scrummaster)
- Rafael Ferreira (Desenvolvedor/Tester)
- Samuel (Desenvolvedor/Tester)

### Exemplos de User Case

_1. Rotina de organização da casa:_

O usuário vai criar tarefas baseadas em rotinas caseiras (como varrer a casa, limpar o banheiro ou arrumar a cozinha). Para isso, ao abrir o aplicativo, ele vai criar uma nova tarefa com base nas preferências dele e vai marcar o prazo de conclusão caso seja necessário.

_2. Rotina de academia_

O usuário vai criar tarefas baseadas em seu treino na academia (quais exercícios ele precisa fazer em determinado dia, por exemplo). Para isso, ao abrir o aplicativo, ele pode criar uma tarefa que corresponde a um dia de academia e adicionar na descrição os exercícios que ele precisa fazer, podendo incluir até mesmo anexos relevantes como imagens dos exercícios. Essa tarefa pode ser programada para se repetir semanalmente em um dia específico (por exemplo, uma tarefa "Dia de Perna" que inclui todos os exercícios de perna do usuário e que se repete toda sexta-feira).

_3. Rotina de estudos na escola/faculdade_

O usuário vai criar rotinas baseadas nos seus estudos na escola ou na faculdade. Para isso, ao abrir o aplicativo, ele pode criar uma tarefa que corresponde a uma sessão de estudo e adicionar na descrição da tarefa qualquer informação relevante. Um exemplo disso seria um aluno do ensino médio criar uma tarefa chamada "Estudo de História", onde ele adiciona na descrição os conteúdos relevantes da matéria para serem estudados, além de links importantes e anexos de livros para estudo. A tarefa pode também ser repetida semanalmente, caso esse estudo precise se tornar um hábito.

_4. Acompanhamento de progressão na academia_

O usuário pode acompanhar o progresso de sua continuidade na academia. Para isso, o usuário vai criar e concluir diversas tarefas relacionadas ao tema, e poderá perceber que seu avatar no aplicativo está também evoluindo e ganhando mais status de força, o que indica que uma progressão está sendo feita nessa categoria de exercícios.

_5. Acompanhamento de conclusão de tarefas da escola/faculdade_

O usuário pode acompanhar a conclusão de suas tarefas escolares ou da graduação. Para isso, o usuário vai criar e concluir diversas tarefas relacionadas ao estudo, e seu avatar no aplicativo irá evoluir em status com base nessa categoria de tarefas.

_6. Planejamento de rotina de hobbies_

O usuário pode criar e planejar uma rotina pessoal de hobbies. Para isso, ao abrir o aplicativo, ele pode criar uma tarefa que corresponde a uma sessão de prática de um hobby e adicionar na descrição as informações relevantes para isso. Essa tarefa também pode ser programada para se repetir semanalmente ou mensalmente. Um exemplo disso seria um usuário criar uma tarefa chamada "Aula de Tricô", em que ele adiciona na descrição informações relevantes sobre a aula e links de vídeos sobre tipos específicos de técnicas de tricô. Essa tarefa também pode se repetir semanalmente caso o usuário tenha essas aulas na quinta-feira.  

_7. Notificação de datas importantes_

O usuário pode criar tarefas que atuam como notificações para datas importantes. Para isso, ao abrir o aplicativo, ele pode criar uma tarefa com um título que remete à data que precisa ser lembrada, habilitar notificações com base em uma data selecionada (relembrar diariamente, semanalmente, mensalmente, em um dia específico ou anualmente) e adicionar informações relevantes à descrição. Um exemplo seria um usuário criar uma tarefa chamada "Aniversário da Irmã" que o notifica todo dia 15 de Junho e possui informações na descrição sobre o tipo de presente que ela gosta. 

_8. Montagem de materiais de estudo por tarefa_

O usuário pode, através da edição de uma tarefa, montar um guia de materiais de estudo a serem utilizados. Para isso, ao abrir o aplicativo e criar uma tarefa, ele pode adicionar na descrição todos os links relevantes e materiais de estudo a serem usados. Por exemplo, um usuário pode criar uma tarefa chamada "Trabalho de Trigonometria", em que ele adiciona na descrição uma série de anexos de livros e vídeos relevantes da internet para sumarizar os conceitos básicos da trigonometria.

_9. Notificação de tarefas do dia-a-dia_

O usuário pode, através da habilitação de notificações, permitir que ele possa ser notificado de tarefas do dia-a-dia. Para isso, ao abrir o aplicativo e criar tarefas de repetição diária, o usuário pode habilitar as notificações, inclusive em horários específicos. Um exemplo disso seria um usuário que habilita a notificação de uma tarefa chamada "Varrer a Rua" todos os dias às 9 da manhã.

_10. Busca por satisfação ao concluir uma tarefa_

Ao concluir uma tarefa, o avatar do usuário no aplicativo se desenvolve evoluindo e ganhando recompensas, o que pode atender à busca por satisfação imediata ao mesmo tempo em que o usuário concluir uma tarefa. Para isso, é apenas preciso que o usuário marque uma tarefa criada no aplicativo como concluída e algum progresso será feito.


## Modelo utilizado durante o Projeto

A metodologia organizacional utilizada durante o projeto foi o **Scrum**. Esta é uma metodologia ágil de desenvolvimento de software que ajuda equipes a trabalharem de forma colaborativa, adaptável e eficiente. É ideal para projetos com requisitos que podem mudar com o tempo — como é o caso de aplicativos voltados ao público final. O modelo **Scrum** surgiu no início dos anos 1990 como uma resposta às limitações dos métodos tradicionais de desenvolvimento de software (como o modelo cascata), que muitas vezes resultavam em projetos longos, inflexíveis e com entregas de baixo valor ao cliente. 

Esta metodologia foi escolhida visando empregar as vantagens da mesma (como as reuniões periódicas entre toda equipe para o levantamento de pontos cruciais dentro do projeto) para assim tornar o projeto organicamente bem estruturado.

📚 **Referência recomendada**

> Sutherland, J., & Schwaber, K. (2020). _The Scrum Guide™ – The Definitive Guide to Scrum: The Rules of the Game_. [https://scrumguides.org](https://scrumguides.org/)

Esse é o guia oficial mantido pelos criadores do Scrum. Ele explica os fundamentos, papéis, eventos e artefatos da metodologia, sendo a principal fonte de consulta para equipes ágeis no mundo todo.

### **Elementos principais do Scrum:**

#### 1. **Papéis**

- **Product Owner (PO)**: Responsável por representar os interesses do cliente/usuário. Ele define e prioriza as funcionalidades no _Product Backlog_.
    
- **Scrum Master**: Garante que o time siga os princípios do Scrum, remove impedimentos, facilita reuniões e ajuda todos a colaborarem melhor.
    
- **Time de Desenvolvimento**: Conjunto de programadores, designers e outros membros que constroem o produto.
    

#### 2. **Artefatos**

- **Product Backlog**: Lista priorizada de funcionalidades (histórias de usuário) que o produto precisa ter.
    
- **Sprint Backlog**: Subconjunto do _product backlog_ com as tarefas que serão feitas na sprint atual.
    
- **Incremento**: É o produto parcialmente desenvolvido no final de cada sprint, com uma ou mais funcionalidades já implementadas e testadas.
    

#### 3. **Eventos**

- **Sprint**: Período de tempo fixo (geralmente 1 a 4 semanas) em que o time desenvolve parte do produto.
    
- **Sprint Planning**: Reunião para planejar o que será feito na sprint.
    
- **Daily Scrum (Daily Stand-up)**: Reunião diária de no máximo 15 minutos para alinhamento rápido.
    
- **Sprint Review**: Apresentação do que foi desenvolvido na sprint.
    
- **Sprint Retrospective**: Discussão sobre o que funcionou e o que pode melhorar para a próxima sprint.

    

# Interface de usuário
