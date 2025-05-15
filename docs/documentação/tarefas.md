# 📄 Arquivo `tarefas.js`

## 1. Visão Geral

O módulo **`tarefas.js`** implementa a lógica de carregamento, exibição e manipulação de tarefas de um usuário, integrando-se ao Firebase Firestore para persistência de dados e ao sistema de autenticação do Firebase Auth. Seu foco principal é apresentar listas de tarefas futuras, expiradas e concluídas, fornecer um contador regressivo para o próximo evento, além de tratar tarefas periódicas.

---

## 2. Dependências e Importações

```js
import { auth } from './auth.js';
import { db }   from './firebase-config.js';
import {
  collection, getDocs, getDoc, doc,
  updateDoc, deleteDoc, Timestamp, addDoc
} from 'https://www.gstatic.com/firebasejs/11.6.0/firebase-firestore.js';
```

* **`auth`**: objeto de autenticação do Firebase.
* **`db`**: instância do Firestore.
* **Firestore SDK**: funções para CRUD e manipulação de `Timestamp`.

---

## 3. Estado Global

```js
let carregandoTarefas = false;
let tempoMaisRecente     = null;
let intervaloContador    = null;
let tarefasFuturas       = [];
let tarefasExpiradas     = [];
let tarefasConcluidas    = [];
```

* Flags de carregamento e referência ao próximo prazo.
* Três arrays para categorizar tarefas conforme o seu estado.

---

## 4. Fluxo de Carregamento e Renderização

1. **`async function carregarTarefas()`**

   * (Implementação não mostrada) deve buscar todas as tarefas do Firestore, filtrar por `finalizada` e `dataLimite`, popular os arrays e chamar funções de renderização.
2. **`function renderizarTarefa(t)`**

   * Encapsula a criação de elementos DOM para cada tarefa (detalhes omitidos).

---

## 5. Manipulação de XP e Nível

```js
function atualizarXP(tarefasConcluidas) { … }
```

* Cada tarefa concluída rende **10 XP**.
* Nível = ⌊(XP\_total / 100)⌋ + 1.
* Barra de progresso e texto são atualizados no elemento `.xp-info`.

---

## 6. Limpeza e Organização de Cards

* **`limparCards()`**: reseta o conteúdo dos containers `.purple-card` (expiradas) e `.blue-card` (concluídas).
* **`adicionarNaCard(tarefa, cardClass)`**: adiciona um `<p>` com descrição, data/hora formatadas e botão de exclusão.

---

## 7. Operações no Firestore

* **`atualizarTarefaNoFirestore(id, descricao, dataLimite)`**
* **`excluirTarefaDoFirestore(id)`**

  * Obtêm o `uid` do usuário atual, referenciam o documento e aplicam atualização ou exclusão.

---

## 8. Modais de Edição e Detalhe

```js
function abrirModalDetalhe(tarefa) { … }
```

* Exibe campos para editar descrição, prazo e tipo de tarefa.
* Botões “Salvar” e “Excluir” disparam as funções de CRUD e recarregam a lista.

---

## 9. Contador para Próxima Tarefa

```js
function atualizarContadorProximaTarefa() { … }
```

* Executado a cada segundo via `setInterval`.
* Move tarefas vencidas de `tarefasFuturas` → `tarefasExpiradas`, atualiza DOM.
* Ordena `tarefasFuturas` e calcula diferença de tempo para exibir no elemento `.next-event`.

---

## 10. Atualização da Data Atual

```js
function atualizarDataAtual() { … }
```

* Exibe no formato “📅 Dia da Semana, DD/MM/AAAA” no elemento `.current-day`.

---

## 11. Tarefas Periódicas

* **`ajustarRecurrentes(tarefas)`**

  * Para cada tarefa periódica expirada e não-finalizada, calcula próximo prazo (diário, semanal, mensal ou customizado), cria nova entrada e marca a antiga como `finalizada`.
* **`processarTarefaPeriodicaAoMarcar(t)`**

  * Similar, mas disparado ao concluir manualmente (listener externo).

---

## 12. Interações Extras e Ordenação

* **Clique em `.next-event`** abre modal com listas organizadas de:

  * Tarefas vencidas, futuras e concluídas.
  * Concatena HTML via templates literais.
* **Ordenar por tipo/tempo**

  * Botões `#ordenar-tipo` e `#ordenar-tempo` chamam `mostrarTarefasOrganizadas(criterio)`, que reagrupa ou reordena `tarefasFuturas` e atualiza o modal.

---

## 13. Função Auxiliar de Tempo

```js
function calcularTempoRestante(dataLimite) { … }
```

* Retorna string “X dias, Y horas e Z minutos” ou “Já passou”.


---

