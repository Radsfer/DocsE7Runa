# 📄 Arquivo `tarefas.js`

## 1. Visão Geral

O módulo **`tarefas.js`** implementa a lógica de carregamento, exibição e manipulação de tarefas de um usuário, além da mecânica de gameficação, integrando-se ao Firebase Firestore para persistência de dados e ao sistema de autenticação do Firebase Auth.

---

## 2. Dependências e Importações

```js
import { auth } from './auth.js';
import { db } from './firebase-config.js';
import { collection, query, where, getDocs, getDoc, doc, updateDoc, deleteDoc, Timestamp, addDoc, increment, arrayUnion, setDoc, serverTimestamp } from 'https://www.gstatic.com/firebasejs/11.6.0/firebase-firestore.js';
import { atacarInimigo, inimigoAtaca, darRecompensa, atualizarProgressoMissoes, mostrarMissoesDiarias } from './script.js';
```

* **`auth`**: objeto de autenticação do Firebase.
* **`db`**: instância do Firestore.
* **` imports from 'https://www.gstatic.com/firebasejs/11.6.0/firebase-firestore.js'`**: métodos do Firebase para gerenciar documentos
* **` imports from 'script.js'`**: gerenciamento de missões e elementos PVE

---

## 3. Variáveis Globais

```js
let dropdownAcoesAberto = null;
let carregandoTarefas = false;
let tempoMaisRecente = null;
let intervaloContador = null;
let tarefasFuturas = [];
let tarefasExpiradas = [];
let tarefasConcluidas = [];
```

* Flags de carregamento e referência ao próximo prazo.
* Arrays para categorizar tarefas conforme o seu estado.
---

## 4. Estrutura de Dados

```js
const subTagsPorCategoria = {...};
const ITENS_CONFIG = {...};
const NOMES_ITENS = {...};
const VALORES_ITENS = {...};
const classesJogador = {...};
const avataresPorClasse = {...};
const frasesPorClasse = {...};
```
* Estruturas que armazenam possíveis valores sobre os respectivos itens

## 5. Gerenciamento de tarefas

### Funções principais

1. **`async function carregarTarefas()`**

   * (Implementação não mostrada) deve buscar todas as tarefas do Firestore, filtrar por `finalizada` e `dataLimite`, popular os arrays e chamar funções de renderização.
2. **`function renderizarTarefa(t)`**

   * Encapsula a criação de elementos DOM para cada tarefa (detalhes omitidos).

### Operações básicas

1. **`async function adicionarTarefa() {...}`**
2. **`async function atualizarTarefaNoFirestore() {...}`**
3. **`async function excluirTarefaDoFirestore() {...}`**
4. **`function abrirModalDetalhe() {...}`**

### Tarefas Recorrentes
1. **`async function ajustarRecurrentes() {...}`**
2. **`async function processarTarefaPeriodicaAoMarcar() {...}`**
3. **`async function criarRecorrentePersonalizada() {...}`**
---

## 6. Sistema de Progresso
### XP e Níveis

```js
function xpNecessarioParaNivel() {...}
async function atualizarXP() {...}
function calcularBonusXP() {...}
```
* Implementação do sistema de progresso pessoal
### Moedas e Inventário

```js
async function atualizarMoedas() {...}
async function carregarInventario() {...}
async function comprarItem() {...}
async function venderItem() {...}
```
* Implementação do sistema de inventário e a relação dos itens com outros componentes do software
---

## 7. Limpeza e Organização de Cards

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

