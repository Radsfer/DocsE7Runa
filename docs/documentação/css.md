# 📄 Arquivo `style.css`

Esse módulo é responsável por organizar e aplicar estilos visuais às páginas HTML.

---

### Importações

Como o HTML é uma linguagem de marcação, e não de lógica como python, C ou outras linguagens, sua interpretação é feita diretamente pelo navegador, de modo que não é necessário realizar nenhuma importação.

---

### **Estrutura**

## Estilo Base e Reset

```js
html, body{
    ...
}

body{
    ...
}
```
* Define fundo escuro e altura total, aplicando layout de Flexbox vertical. Além disso remove margens e paddings padrão do navegador.

## Suporte IOS

```js
body.ios-pwa{
    ...
}
```
* Garante que a interface esteja correta para dispositivos IOS.

## Container da Aplicação

```js
.container{
    ...
}
```

* Faz a definição de contêiner transparente, aplicando efeito de desfoque. Também previne a rolagem **horizontal**.

## Ocultação de Elmentos

```js
.hidden{
    ...
}
```

* Em tradução literal, hidden significa "escondido", exatamente o que essa linha faz, permitindo que elementos sejam escondidos dinamicamente.

## Layout da Loja e Inventário

```js
.loja-grid, .inventario-grid{
    ...
}
```

* Apresenta os itens da **loja** em duas colunas com espaçamento uniforme. Também organiza o inventário.

## Cartões de Item

```js
.item-card{
    ...
}
```
* Cria cartões com layout fixo para manter uniformidade.


```js
.item-imagem{...}
.item-nome{...}
.item-preco{...}
```
* Essencialmente essas funções ajustam a forma como o item é apresentado ao usuário dentro do aplicativo. Questões como imagem, cor e o preço.

## Botão de Compra

```js
.btn-comprar{...}
.btn-comprar:hover{...}
```

* Botão de compra verde com interação hover.

## Formato Principal da Aplicação

```js
.app{
    ...
}
```

* Layout Principal, é o container central que engloba o conteúdo da aplicação.

## Corpo da Aplicação

```js
#app-body{
    ...
}
```

* Corpo da aplicação, inicialmente oculto. É exibido após o carregamento via javascript.

## Seções de Tarefas

```js
#tarefas-periodico,
#tarefas-nao-periodico,
#taregas-personalizado{
    ...
}
```

* Definição de dimensões das áreas que exibem listas de tarefas.

## Cartões Gerais e Aplicação de Visuais

```js
.card{
    ...
}
```

* Cartões gerais usados para conteúdos diversos dentro da aplicação. Setado com fundo escuto, sombra suave e bordas arredondadas.


```js
.purple-card,
.blue-card{
    ...
}
```

* Cartões temáticos para usos específicos dentro da aplicação.

## Aréas de Navegação e Conteúdos

```js
.main-content{
    ...
}
```

* Define o ambiente principal, com rolagem vertical.


```js
.bottom-nav{
    ...
}

.botom-nav.separator.active,
.bottom-nav-separator{
    ...
}
```

* Implementam a barra inferior fixa com ícones e indicadores vizuais ativous ou inativos.

## Barra Superior de Informações

```js
.top-info-bar{
    ...
}
```

* Barra de cima que mostra informações importantes e se adapta aos limites de largura e conteúdo.


```js
.top-info-bar span,
.top-infor-bar .next-event,
.top-info-bar .icons-info{
    ...
}
```

* Essa implementação é o que garante que os textos da barra superior permaneçam justificados e não estourem o layout definido.

## Campos de Formulário e Interações

```js
input, textarea, select{
    ...
}
```

* Campos de interação com usuário.


```js
input[type="checkbox"]{...}
input[type="checkbox"]:checked {...}
```
* Checkbox customizada.

## Scrollbar Customizada

```js
.slider-container::webkit-scroller{
    ...
}
slider-container::webkit-scrollbar-thumb{
    ...
}
```

* Estilização da barra de rolagem para ambientes de navegador.

## Modais, Diálogos e Notificações

```js
.dialog-container,
.modal,
#popup-alert{
    ...
}
```

* Modais, pop-ups (notificações) e diálogos. Aplicados com fundo semitransparente, bordas arredondadas, blur e sombra como muitos apps fazem.

## Cards Interativos Individualizados por Tarefa

```js
.task-rect[...]{
    ...
}
```

* Implementa cards interativos para cada tipo de tarefa, com esquemas de cores individuais para cada uma. Também aplica animação de hover.

## Tags e Classificações

```js
.tag-nivel-1,
.tag-nivel-2,
.tag-personalizada{
    ...
}
```

* Tags e classificações com estilos vizuais personalizados por nível ou origem.

## Switches e Botões Customizáveis

```js
.switch input:checked + .slider{
    ...
}
```

* Switches e botões customizados com comportamento responsivo e animado.

## Organização das Tarefas

```js
#lista-tarefas-organizada{
    ...
}

.grupo-tipo{
    ...
}
```

* Faz a organização de tarefas em colunas por tipo de tarefa. Aplica uma cor mais clara que contrasta com o fundo geral da aplicação, que é escuro.

## Layout de Gráficos e Painel

```js
.grafico-grid{
    ...
}
.grafico-card{
    ...
}
```

* Layout de gráficos e painel. Aplica a disposição dos gráficos lado a lado.

## Exibição de Anexos

```js
#modal-visualizacao-anexo .modal-content pre, iframe {
    ...
}
.anexo-link{
    ...
}
```

* Implementa a visualização de arquivos e anexos com legibilidade e contraste.

## Avatares e Informações

```js
.popup-personagem{
    ...
}
```

* Exibe informações do usuário, neste caso o personagem.

## Calendário de Tarefas

```js
#calendario-container{
    ...
}
.dia{
    ...
}
```

* Calendário de tarefas, implementado com uma inferface funcional e cores distintas por tipo de tarefa.
