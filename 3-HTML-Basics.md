# HTML Básico

HTML é um padrão definido pelo **WHATWG**, um acrônimo para Web Hypertext Application Technology Working Group, uma organização formada por pessoas trabalhando nos navegadores web mais populares. Isto significa que basicamente é contolado por Google, Mozilla, Apple e Microsoft. 

No passado, a **W3C** (World Wide Web Consortium) era a organização responsável por criar os padrões HTML.

O controle informalmente mudou da W3C para WHATWG quando ficou claro que a investida da W3C para o XHTML não era uma boa idéia.

Se você nunca ouviu falar sobre XHTML, aqui vai uma breve história. No incício dos anos 2000, nós acreditávamos que o futuro da Web era o XML (é sério). Então, o HTML mudou de uma linguagem de autoria baseada em SGML para uma linguagem de marcação XML.

Essa foi uma grande mudança. Nós tínhamos que conhecer, e respeitar mais regras. Regras mais rígidas.

No fim, as empresas de navegadores perceberam que este não era o caminho correto para a Web, e voltaram atrás, criando aquilo que é conhecido como HTML5.

O W3C não concordou em perder o controle do HTML, e por anos nós tivemos 2 padrões competindo, cada um almejando ser o oficial.
Por fim, em 28 de maio de 2019, foi declarado oficialmente pela W3C que a "verdadeira" versão do HTML era aquela publicada pela WHATWG.

Eu mencionei HTML5. Deixe-me explicar isso. Eu sei, é um pouco confuso, como ocorre com muitas coisas na vida em que muitos atores estão envolvidos, mas também é fascinante. 

Nós tínhamos o **HTML versão 1** em 1993. [Aqui está o RFC original](https://tools.ietf.org/html/rfc1983).

Em seguida, o **HTML 2** em 1995.

Tivemos o **HTML3** em janeiro de 1997, e o **HTML4** em dezembro de 1997.

Época movimentada!

Mais de 20 anos se passaram, nós passamos por toda essa questão do XHTML, e por fim chegamos a essa "coisa" do HTML5, que não é mais realmente _apenas HTML_.

O HTML agora é um termo que define todo um conjunto de tecnologias, que inclui HTML, mas adiciona um monte de APIs e padrões como WebGL, SVG e mais.

O ponto chave para entender é: não existe (mais) uma versão do HTML. Ele é um padrão vivo. Tal como o CSS, que é chamado de "3", mas na verdade é um monte de módulos independentes desenvolvidos separadamente. Como o Javascript, onde temos uma nova edição a cada ano, mas hoje, a única coisa que interessa é que funcionalidades individuais são implementadas pela engine.

Sim, chamamos de HTML5, mas HTML4 é de 1997. Isso é muito tempo para qualquer coisa, ainda mais para a web.

Aqui está onde o padrão agora "reside": [https://html.spec.whatwg.org/multipage](https://html.spec.whatwg.org/multipage).


HTML é a linguagem de marcação que usamos para estruturar o conteúdo que consumimos na Web.

O HTML é oferecido ao navegador de diferentes formas.
* Pode ser gerado pelo lado do servidor da aplicação, que o monta a depender da requisição ou dos dados da sessão, como por exemplo uma aplicação em Rails, Laravel ou Django.
* Pode ser gerado por uma aplicação Javascript do lado do cliente, que gera o HTML na hora.
* No caso mais simples, pode ser armazenado em um arquivo e servido ao navegador por um servidor Web.

Vamos nos aprofundar neste último caso. Apesar de que na prática essa seja a maneira menos popular de gerar HTML, ainda é essencial saber os blocos de construção básicos.

Por convenção, um arquivo HTML é salvo com uma extensão `.html` ou `.htm`.

Dentro deste arquivo, nós organizamos o conteúdo usando **tags**.

Tags envolvem o conteúdo, e cada tag dá um sentido especial ao texto que ela envolve.

Vamos ver alguns exemplos.

Este snippet HTML cria um parágrafo utilizando a tag `p`:

```html
<p>O texto de um parágrafo</p>
```

Este snippet HTML cria uma lista de items usando a tag `ul`, que significa *lista não-ordenada*, e tags `li`, que significa *item de lista*:

```html
<ul>
  <li>Primeiro item</li>
  <li>Segundo item</li>
  <li>Terceiro item</li>
</ul>
```
Quando uma página HTML é servida ao navegador, as tags são interpretadas, e o navegador renderiza os elementos de acordo com as regras que definem a sua aparência visual.

Algumas dessas regras são internas, como o modo que uma lista é renderizada ou o modo como um link é sublinhado em azul.

Algumas outras regras são definidas por você com o CSS.

HTML não é de apresentação. Ele não se preocupa com a forma como as coisas *se mostram*. Ao invés disso, se preocupa com o que as coisas *significam*.

Fica a cargo do navegador determinar como as coisas se mostram, com as diretivas definidas por quem constrói a página, usando a linguagem CSS.

Agora, aqueles dois exemplos que fiz são snippets HTML tirados do contexto de uma página.


### Estrutura de página HTML

Vamos criar um exemplo de uma página HTML adequada.

As coisas começam com a Declaração do Tipo de Documento (conhecido como _doctype_), que é um modo de dizer ao navegador que isso é uma página HTML, e qual versão do HTML estamos usando.

O HTML moderno utiliza este doctype:

```html
<!DOCTYPE html>
```

E então nós temos o elemento `html`, o qual possui uma tag de abertura e de fechamento:

```html
<!DOCTYPE html>
<html>
...
</html>
```

A maioria das tags vêm em pares com uma tag de abertura e uma tag de fechamento. A tag de fechamento é escrita da mesma maneira que a tag de abertura, mas com uma barra `/`:


```html
<algumatag>algum conteúdo</algumatag>
```
Existem algumas tags auto-fechadas, o que significa que elas não precisam de uma tag de fechamento, já que elas não contêm nada _dentro delas_.

A tag inicial `html` é usada no começo do documento, logo após a declaração do tipo do documento.

A tag de fechamento `html` é a última coisa presente em um documento HTML.

Dentro do elemento `html` nós temos 2 elementos: `head` e `body`:

```html
<!DOCTYPE html>
<html>
	<head>
	...
	</head>
	<body>
	...
	</body>
</html>
```

Dentro do `head` nós vamos ter tags que são essenciais para criar uma página web, como o título, os metadados, e CSS e Javascript interno ou externo. Principalmente as coisas que não aparecem diretamente na página, e que apenas ajudam o navegador (ou bots como o bot de busca da Google) a mostrar essas coisas na tela adequadamente.

Dentro do `body` nós vamos ter o conteúdo da página. As **coisas visíveis**.

### Tags vs elementos

Eu mencionei tags e elementos. Qual a diferença?

Elementos possuem uma tag de abertura e de fechamento. Neste exemplo, usamos as tags de abertura e fechamento `p` para criar um elemento `p`:

```html
<p>Um parágrafo de texto</p>
```

Então, um elemento constitui todo o _pacote_:

- tag de abertura
- conteúdo de texto (e possivelmentes outros elementos)
- tag de fechamento

Caso um elemento não possua uma tag de fechamento, ele é escrito apenas com a tag de abertura, e não pode conter nenhum conteúdo de texto.

Dito isto, eu posso usar o termo tag ou elemento neste livro significando a mesma coisa, exceto se eu explicitamente mencionar tag de abertura ou tag de fechamento.

### Atributos

A tag de abertura de um elemento pode ter snippets especiais de informação que podemos incluir, chamados **atributos**.

Atributos possuem a sintaxe `chave="valor"`:


```html
<p class="uma-classe">Um parágrafo de texto</p>
```

> Você também pode usar aspas simples, mas usar aspas duplas em HTML é uma boa convenção.

Podemos ter várias delas:

```html
<p class="uma-classe" id="uma-id">Um parágrafo de texto</p>
```

e alguns atributos são booleanos, o que quer dizer que você precisa apenas da chave:


```html
<script defer src="file.js"></script>
```

Os atributos `class` e `id` são dois dos atributos mais comuns que você vai encontrar.

Eles possuem um significado especial, e são úteis em CSS e Javascript.

A diferença entre os dois é que uma `id` é única no contexto da página web; ela não pode estar duplicada.

Classes, por outro lado, podem aparecer várias vezes em vários elementos.

Além disso, uma `id` é apenas um valor. `class` pode conter vários valores, separados por um espaço:

```html
<p class="uma-classe outra-classe">Um parágrafo de texto</p>
```

É comum usar o traço `-` para separar palavras no valor da classe, mas é apenas uma convenção.

Esses são apenas dois dos atributos possíveis que você pode usar. Alguns atributos são usados apenas em uma tag. Eles são altamente especializados.

Outros atributos podem ser usados de maneira mais geral. Você viu apenas `id` e `class`, mas temos outros também, como `style`, que pode ser usado para inserir regras inline (na própria linha) de CSS em um elemento.


### Case insensitive

HTML é _case insensitive_. Tags podem ser escritas em letras maiúsculas ou minúsculas. Tempos atrás, letras maiúsculas eram a regra. Hoje letras minúsculas são a regra. É uma convenção.

Você geralmente escreve assim:

```html
<p>Um parágrafo de texto</p>
```

e não escreve assim:

```html
<P>Um parágrafo de texto</P>
```

### Espaço em branco

Isso é muito importante. Em HTML, mesmo que você adicione múltiplos espaços em branco em uma linha, eles são retirados pela engine CSS do navegador. 

Por exemplo a renderização deste parágrafo:

```html
<p>Um parágrafo de texto</p>
```

é o mesmo que isso:

```html
<p>      Um parágrafo de texto</p>
```

e o mesmo que isso:

```html
<p>Um parágrafo

de
           texto          </p>
```

> Usando a [propriedade CSS](https://developer.mozilla.org/en-US/docs/Web/CSS/white-space) `white-space` você pode alterar esse comportamento. Você pode encontrar mais informação de como o CSS processa espaços em branco na [Documentação CSS](https://www.w3.org/TR/CSS2/text.html#white-space-model)

Eu diria para usar a sintaxe que deixe as coisas visualmente mais organizadas e mais fáceis de ler, mas você pode usar a sintaxe que preferir.


Eu normalmente prefiro:

```html
<p>Um parágrafo de texto</p>
```

ou

```html
<p>
	Um parágrafo de texto
</p>
```

Tags aninhadas devem ser identadas com 2 ou 4 caracteres, a depender da sua preferência:

```html
<body>
	<p>
		Um parágrafo de texto
	</p>
	<ul>
		<li>Um item de lista</li>
	</ul>
</body>
```

> Nota: esta funcionalidade "espaço em branco não é relevante" significa que caso você queira adicionar mais espaço, isso pode deixar tudo bem ruim. Eu sugiro que você use o CSS para criar mais espaço quando necessário. 

> Nota: em casos especiais, você pode usar a entidade HTML `&nbsp;` (um acrônimo que significa _non-breaking space_) - mais informações sobre entidades HTML posteriormente. Penso que isto não deve ser abusado. O CSS é sempre o preferido para alterar a apresentação visual.
