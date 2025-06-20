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
const subTagsPorCategoria = {...}
const ITENS_CONFIG = {...}
const NOMES_ITENS = {...}
const VALORES_ITENS = {...}
const classesJogador = {...}
const avataresPorClasse = {...}
const frasesPorClasse = {...}
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

## 8. Operações no Firestore
```js
atualizarTarefaNoFirestore(id, descricao, dataLimite){...}
salvarXPNoFirestore(classeAtiva){...}
excluirTarefaDoFirestore(id){...}
```

  * Obtêm o `uid` do usuário atual, referenciam o documento e executam o comando em questão.

---

## 9. Calendário

```js
function atualizarDataAtual() { … }
function renderizarCalendario() {...}
```

** Exibe a data no formato “📅 Dia da Semana, DD/MM/AAAA” no elemento `.current-day`.
* Renderiza um calendário interativo que exibe visualmente as tarefas do usuário com estilos diferenciados por status e tipo.
* Preenche células vazias para alinhamento
* Gera células para cada dia do mês
* Adiciona eventos de clique para interatividade
 
## 10. Popups e Modais

```js
function mostrarPopup() {...}
function mostrarPopupPersonagem() {...}
function abrirModalVisualizacaoAnexo() {...}
function abrirModalDetalhe() {...}
```

* Gerencia Popups e modais necessários
---

## 11. Utilitários
### Manipulação de Datas

```js
function getInicioDoDia() {...}
function getFimDaSemana() {...}
function calcularTempoRestante() {...}
```

### Helpers

```js
function isIOSDevice() {...}
function fileToBase64() {...}
function limparCards() {...}
```
---

## 12. Sistema de Classes

### Gerenciamento

```js
function preencherClasseSelectorComBonus() {...}
function atualizarVisualClasse() {...}
function personagemFalaAleatoriamente() {...}
```

---

## 13. Função Auxiliar de Tempo

```js
function calcularTempoRestante(dataLimite) { … }
```

* Retorna string “X dias, Y horas e Z minutos” ou “Já passou”.


---

