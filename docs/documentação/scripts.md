
# 📄 Arquivo `script.js`

## 🧩 1. Visão Geral
  O arquivo 'script.js' é responsável por implementar scripts necessários em outras partes do projeto.

  ---
  
## 🔗 2. Dependências e Importações

```js
import { auth } from './auth.js';
import { db, carregarMeuSimpleID, listarAmigosAceitos } from './firebase-config.js';
import { getAuth, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.0/firebase-auth.js";
import { doc, collection, addDoc, getDocs, Timestamp, deleteDoc, serverTimestamp, setDoc, getDoc, increment } from 'https://www.gstatic.com/firebasejs/11.6.0/firebase-firestore.js';
import { carregarTarefas,mostrarPopup,carregarInventario, calcularDefesa } from './tarefas.js';
```
* **`auth`**: objeto de autenticação do Firebase.
* **`imports from firebase-config`**: instância configurada do Firestore e funcionalidades referentes a interações sociais do software.
* **`imports from firebase-auth.js`**: métodos do Firebase para gerenciar autenticação
* **`imports from firebase-firestore`**: étodos do Firebase para gerenciar documentos
**`imports from tarefas.js`**: auxílio na criação de tarefas, popups, sistema de inventário e PVE.

---

## 🎯 3. Sistema de Missões Diárias

```js
const MISSOES_DIARIAS = [ ... ];
async function sortearMissoesDiarias(uid)
async function carregarMissoesDiarias(uid)
function abrirModalTrocarMissao(missao, idx, uid)
async function trocarMissaoDiaria(uid, missaoId)
async function mostrarMissoesDiarias(uid)
export async function atualizarProgressoMissoes(uid, tipoTarefa, xpGanho = 0)
```
* Implementa a lógica de missões diárias por usuário, as quais são aleatórias e concedem recompensas adicionais que se intercalam com o sistema de progressão e PVE.

---

## 🐉 4. Sistema de inimigos (PVE)

```js
const INIMIGOS = [ ... ]
function getNovoInimigo(indice = 0)
async function carregarInimigoFirestore(uid)
async function salvarInimigoFirestore(uid, inimigo)
async function atualizarUIInimigo()
async function atualizarProgressoDanoInimigo(uid, dano)
async function atacarInimigo(dano = 10)
async function inimigoAtaca()
async function darRecompensa(uid, xp, moedas)
async function perderXP(uid, xp)
```

* Implementa a lógica de PVE, enfrentando inimigos aleatórios que podem ser derrotados por ataques concedidos através da conclusão de tarefas e missões.

---

## ✨ 5. Ataques Especiais

```js
export async function adicionarAtaqueExtra(uid, quantidade = 1)
export async function atacarInimigoExtra(dano = 10)
export async function ataqueEspecialInimigo()
function atualizarBotaoEspecial()
function playEspecialAttackAnimation(canvasId = 'especial-attack-canvas');
```

* Sistema de ataques com animações e efeitos especiais.

  ---

## 📝 6. Adicionar Tarefas

```js
async function adicionarTarefa(nome, descricao, dataLimite)
```
- Verifica se o usuário já é autenticado
- Valida a estrutura de dados da tarefa
- Cria uma tarefa e age conforme o seu tipo
- Armazena a tarefa no banco de dados
- Recarrega a lista de tarefas
---

## 🔔 7. Notificações

```js
const notificacoes = ...;
await addDoc(collection(db, "scheduledNotifications"), { ... });
```

* Sistema de notificações entregues ao usuário nas datas especificadas.
---

## 💬 8. Mensagens, Modais e Popups

```js
const filaDeMensagens = []
function mostrarMensagem(mensagem)
```
- Recebe uma mensagem como parâmetro
- Exibe a mensagem ao usuário através do modal
- Utiliza do blur quando há um plano de fundo
- Garante que uma mensagem não sobreponha outra.

```js
function exibirProximaMensagem()
```
- Utiliza elementos HTML
- Verifica se há mensagens na fila
- Obtém a primeira mensagem da fila, a exibe e retira da fila
- Se certifica se há mais mensagens a serem exibidas depois do usuário fechar o diálogo
- Exibe a próxima mensagem da fila, caso haja.

```js
function abrirModalTrocarMissao(missao, idx, uid)
```

* Gerencia o processo de troca de missões a partir de um modal.

```js
function mostrarPopup(mensagem, duracao = 2000)
```
- Recebe uma mensagem e uma duração (em ms) como parâmetro
- Exibe a janela com a mensagem pela duração escolhida

---

## 🌫️ 9. Blur

```js
function exibirBlurBackground()
```
- Aplica blur em segundo plano

```js
function esconderBlurBackground()
```
- Remove blur

---

## 📱 10. Verificação de sistema operacional

```js
function isIOSDevice()
```
- Identifica o navegador e o sistema operacional do usuário
- Retorna 'true' se é um dispositivo IOS

---

## 📎 11. Anexação de Arquivos

```js
function fileToBase64(file)
```
- Converte arquivos para base64
- Auxilia no upload de anexos

---

## 🎠 12. Carrosséis e Sliders

```js
function setupGraficoCarousel();
function setupTarefasSliderCarousel();
function atualizarVisibilidadeTarefasSlider();
```
* Sistemas de carrossel para gráficos e tarefas com controles responsivos.

---


## ↔️ 13. Função de Swipe

```js
const minSwipeDistance = 100;
function atualizarVisibilidadeAppBody()
function handleSwipe()
```
Configura a função de swipe:
- Verifica a intensidade do gesto
- Coleta elementos como botões de navegação
- Determina a direção do deslizamento
- Aplica CSS para adicionar uma transição animada
- Atualiza estado da aba ativa
- Configura a visibilidade de elementos

---



## 🧭 14. Manipulação do DOM

### 14.1. Criação de Tarefas
```js
document.getElementById('botao-criar-tarefa').addEventListener('click', handleCreateTask)
```
- Preenche campos obrigatórios
- Chama a função 'adicionarTarefa()' com os dados preenchidos
- Por fim, cria uma tarefa
<br><br><br>

### 14.2. Exclusão de todas as tarefas
```js
document.getElementById('delete-all-tasks-button').addEventListener('click', handleDeleteAllTasks)
```
- Confirmação e validação de usuário antes de excluir
- Remove todas as tarefas do banco de dados
- Recarrega a página após conclusão
  <br><br><br>

### 14.3. Atualização de Interface
```js
document.querySelectorAll('.bottom-nav .nav-button').forEach(btn => {
  btn.addEventListener('click', handleTabChange)
})
```
- Gerencia a transição entre abas
- Atualiza a estilização a partir de classes CSS
- Carrega conteúdo específico
<br><br><br>

### 14.4. Gestos Touch
```js
document.addEventListener('touchstart', handleTouchStart)
document.addEventListener('touchend', handleTouchEnd)
```
- Implemente a função de swipe
- Delimita a sensibilidade do gesto
- Anima as transições entre abas

