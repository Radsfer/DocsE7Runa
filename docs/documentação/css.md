# 📄 Arquivo `style.css`

Esse módulo é responsável por organizar e aplicar estilos visuais às páginas HTML.

---

### Importações

Como o HTML é uma linguagem de marcação, e não de lógica como python, C ou outras linguagens, sua interpretação é feita diretamente pelo navegador, de modo que não é necessário realizar nenhuma importação.

---

### Estrutura
```js
html, body{
    ...
}

body{
    ...
}
```
* Define fundo escuro e altura total, aplicando layout de Flexbox vertical. Além disso remove margens e paddings padrão do navegador.


```js
body.ios-pwa{
    ...
}
```
* Garante que a interface esteja correta para dispositivos IOS.


```js
.container{
    ...
}
```

* Faz a definição de contêiner transparente, aplicando efeito de desfoque. Também previne a rolagem **horizontal**.

```js
.hidden{
    ...
}
```
* Em tradução literal, hidden significa "escondido", exatamente o que essa linha faz, permitindo que elementos sejam escondidos dinamicamente.


```js
.loja-grid, .inventario-grid{
    ...
}
```

* Apresenta os itens da **loja** em duas colunas com espaçamento uniforme.


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


```js
.btn-comprar{...}
.btn-comprar:hover{...}
```

* Botão de compra verde com interação hover.

```js
.app{
    ...
}
```

* Layout Principal, é o container central que engloba o conteúdo da aplicação.


```js
#app-body{
    ...
}
```

* Corpo da aplicação.


```js
#tarefas-periodico,
#tarefas-nao-periodico,
#taregas-personalizado{
    ...
}
```

* Definição de dimensões das áreas que exibem listas de tarefas.


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


```js
.main-content{
    ...
}
```

* Área principal