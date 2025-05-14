
# 📄 Arquivo `index.html`

O código apresentado estrutura a interface principal do aplicativo **R.U.N.A.**, um gerenciador de tarefas com elementos de gamificação, utilizando tecnologias como HTML, CSS, JavaScript e Firebase.

---

### Cabeçalho (`<head>`)

A seção `<head>` configura o documento e importa os recursos essenciais:

* Metadados sobre o viewport, tema e compatibilidade com web-apps.
* Ícone do app e manifesto (`manifest.json`) para instalação PWA.
* Estilização com `style.css`.
* Importação do parser de Markdown (Markdown-it).
* SDKs do Firebase, separando `firebase-config.js` e `auth.js` com `type="module"`.

---

### Corpo do documento (`<body>`)

#### Login

```html
<div id="login-container">
```

Interface simples para autenticação com Google.

---

#### Pop-ups e Modais

Inclui elementos para interação como:

* Alertas e mensagens (`#popup-alert`, `#custom-dialog`)
* Modal para criar tarefas (`#modal-criar-tarefa`)
* Modal para editar tarefas (`#modal-tarefa`)
* Modal para visualizar tarefas organizadas (`#modal-next-event`)

---

#### Barra superior

```html
<div class="top-info-bar">
```

Exibe o nome do usuário, data atual e o tempo restante para a próxima tarefa.

---

### Área principal (`.main-content`)

#### Abas (Tabs)

```html
<div class="tabs">
```

Organiza a navegação em diferentes seções:

* **Home**: exibe personagem e barra de XP.
* **Tarefas periódicas / não periódicas / personalizadas**: tarefas organizadas por tipo.
* **Configurações**: permite logout, limpar cache e configurações futuras.

---

#### Cards de tarefas

```html
<div class="card purple-card">
```

Dois cards visíveis:

* Tarefas expiradas (cor roxa)
* Tarefas concluídas (cor azul)

---

### Navegação inferior (`.bottom-nav`)

```html
<div class="bottom-nav">
```

Menu fixo que permite trocar de aba com ícones intuitivos.

---

### Service Worker

Inclui script para registro do Service Worker, permitindo o uso offline (PWA).

---

### Scripts finais

```html
<script type="module" src="script.js">
```

Importa a lógica principal do aplicativo, como a manipulação das tarefas, interações com Firebase e comportamento da interface.

---

### Comentário Final

A estrutura modularizada do HTML facilita a manutenção e expansão do sistema. A separação entre lógica de autenticação (`auth.js`), configuração Firebase (`firebase-config.js`), lógica de tarefas (`tarefas.js`) e UI geral (`script.js`) permite uma arquitetura organizada. Além disso, o uso de modais e elementos dinâmicos contribui para uma UX moderna e funcional.

O código mostra preocupação com **responsividade**, **gamificação** e **acessibilidade** (tema escuro, botões claros, estrutura semântica).

---

