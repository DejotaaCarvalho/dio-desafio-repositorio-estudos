## O que realmente é CSS?

Assim como o HTML, o CSS não é realmente uma linguagem de programação. Também não é uma linguagem de marcação — é uma *linguagem de folhas de estilos*. Isso significa que o CSS permite aplicar estilos seletivamente a elementos em documentos HTML. Por exemplo, para selecionar **todos** os elementos parágrafo de uma página HTML e tornar o texto dentro deles vermelho, você escreveria este CSS:

```css
p {
  color: red;
}
```

Ainda assim, precisamos aplicar o CSS ao seu documento HTML. Do contrário, o estilo CSS não irá afetar a maneira como o seu navegador mostra seu documento HTML.



### Anatomia de um conjunto de regras do CSS

<img src="D:\Downloads\css1.png" style="zoom: 80%;" />

Toda essa estrutura é chamada de **conjunto de regras** (mas geralmente usamos o termo "regra", por ser mais curto). Note os nomes das partes individuais:

- Seletor (Selector)

  O nome do elemento HTML no começo do conjunto de regras. Ele seleciona o(s) elemento(s) a serem estilizados (nesse caso, elementos <p>). Para dar estilo a um outro elemento, é só mudar o seletor.

- Declaração (Declaration)

  Uma regra simples como `color: red;` especificando quais das **propriedades** do elemento você quer estilizar.

- Propriedades (Property)

  Forma pela qual você estiliza um elemento HTML. (Nesse caso, `color` é uma propriedade dos elementos <p>.) Em CSS, você escolhe quais propriedades você deseja afetar com sua regra.

- Valor da propriedade (Property value)

  À direita da propriedade, depois dos dois pontos, nós temos o **valor de propriedade**, que escolhe uma dentre muitas aparências possíveis para uma determinada propriedade (há muitos valores `color(cor)` além do `red(vermelho)`).



Então para modificar múltiplos valores de propriedades de uma vez, você deve escrevê-los separados por ponto e vírgula, desse modo:

```css
p {
  color: red;
  width: 500px;
  border: 1px solid black;
}
```



### Selecionando múltiplos elementos

Você também pode selecionar vários tipos de elementos e aplicar um único conjunto de regras a todos eles. Inclua múltiplos seletores separados por vírgulas. Por exemplo:

```css
p, li, h1 {
  color: red;
}
```



### Diferentes tipos de seletores

Há muitos tipos diferentes de seletores. Abaixo, nós mostramos apenas os **seletores de elementos**, que selecionam todos os elementos de um determinado tipo nos documentos HTML. Mas nós podemos fazer seleções mais específicas que essas. Aqui estão alguns dos tipos mais comuns de seletores:

| Nome do seletor                                              | O que ele seleciona                                          | Exemplo                                                      |
| :----------------------------------------------------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| Seletor de elemento (às vezes, chamado tag ou seletor de tipo) | Todos os elementos HTML de determinado tipo.                 | `p` Seleciona `<p>`                                          |
| Seletor de ID                                                | O elemento na página com o ID específicado. Em uma determinada página HTML, é uma boa prática usar um elemento por ID (e claro, um ID por elemento) mesmo que seja permitido usar o mesmo ID para vários elementos. | `#my-id` Seleciona `<p id="my-id">` ou `<a id="my-id">`      |
| Seletor de classe                                            | O(s) elemento(s) na página com a classe específicada (várias instâncias de classe podem aparecer em uma página). | `.my-class` Seleciona `<p class="my-class">` e `<a class="my-class">` |
| Seletor de atributo                                          | O(s) elemento(s) na página com o atributo especificado.      | `img[src]` Seleciona `<img src="myimage.png">` mas não `<img>` |
| Seletor de pseudo-classe                                     | O(s) elemento(s) específicado(s), mas somente quando estiver no estado especificado. Ex.: com o mouse sobre ele. | `a:hover` Seleciona `<a>`, mas somente quando o mouse está em cima do link. |





## Caixas, caixas, é tudo sobre caixas

Uma coisa que você notará sobre escrever CSS é que muito disso é sobre caixas — indicar seu tamanho, cor, posição, etc. Muitos dos elementos HTML da sua página podem ser pensados como caixas umas em cima das outras. Como esperado, o layout CSS é baseado principalmente no *modelo de caixas*.

Cada um dos blocos que ocupam espaço na sua página tem propriedades como essas:

- `padding`, o espaço ao redor do conteúdo (ex.: ao redor do texto de um parágrafo).
- `border`, a linha sólida do lado de fora do padding.
- `margin`, o espaço externo a um elemento.

<img src="D:\Downloads\css2.png"  />


Nessa seção nós também vamos usar:

- `width` (largura de um elemento).
- `background-color`, a cor atrás do conteúdo de um elemento e do padding.
- `color`, a cor do conteúdo de um elemento (geralmente texto).
- `text-shadow`: cria uma sombra no texto dentro de um elemento.
- `display`: define a maneira de dispor um elemento (não se preocupe com isso ainda).





# Flexbox

O **Flexbox** é um conceito do **CSS3** que visa organizar os elementos de uma página HTML dentro de seus containers de forma dinâmica. Ou seja, independente das suas dimensões eles sempre manterão um layout flexível dentro do seu elemento pai, reorganizando-se e acordo com a necessidade.



### Conceitos iniciais

O **Flexbox** é um conjunto de propriedades que tem por objetivo organizar itens dentro de um elemento pai, normalmente chamado de container, conforme ilustra a **Figura 1**.

![Estrutura dos elementos para aplicação do Flexbox](https://arquivo.devmedia.com.br/artigos/Fernando_gaspar/flex/estrutura_elementos.png)

Portanto, para utilizar esse recurso é necessário ter no HTML ao menos um elemento (container) contendo outros (itens), como no código abaixo:

```css
<div class="container">
     <div class="item item1"></div>
     <div class="item item2"></div>
     <div class="item item3"></div>
</div>
```



### Propriedades do Flexbox

### display

O primeiro passo para **utilizar o Flexbox** é definir a propriedade *display* do container com o valor *flex*. Isso é necessário para que as demais propriedades apresentem o resultado esperado.

A sintaxe de uso dessa propriedade é a seguinte:

```css
.container {
     display: flex;
 }
```

### flex-direction

A propriedade *flex-direction* deve ser aplicada ao container e define o eixo/fluxo de exibição em que os elementos serão organizados. A sintaxe e os valores possíveis para essa propriedade são apresentados a seguir:

```
.container {
     display: flex;
     flex-direction: [row / row-reverse / column / column-reverse];
 }
```

- **row** (padrão): Os itens são organizados em forma de linha da esquerda para a direita;
- **row-reverse**: Os itens são organizados em forma exibição em linha da direita para a esquerda;
- **column**: Os itens são organizados em forma de colunas iniciando de cima para baixo;
- **column-reverse**: Os itens são organizados em forma de colunas iniciando de baixo para cima.

A **Figura 3** ilustra o funcionamento de cada valor.

<img src="https://arquivo.devmedia.com.br/artigos/Fernando_gaspar/flex/flex-direction.png" alt="Funcionamento da propriedade flex-direction"  />

### flex-wrap

Por padrão os itens do container tentarão se ajustar em uma única linha dentro do container, mas para isso a sua largura original pode ser ajustada para que todos caibam na largura do elemento pai. Com a propriedade *flex-wrap* aplicada ao container podemos alterar esse comportamento, fazendo com que ocorra a “quebra de linha” nos itens.

A sintaxe e os valores possíveis para essa propriedade são apresentados a seguir:

```css
.container {
     display: flex;
     flex-wrap: [nowrap / wrap / wrap-reverse];
 }
```

- **nowrap** (padrão): Todos os itens serão dispostos em uma linha;
- **wrap**: Ocorrerá a quebra de linha e os itens mais à direita serão deslocados para a linha de baixo;
- **wrap-reverse**: Ocorrerá a quebra de linha e os itens mais à direita serão deslocados para a linha de cima;

### flex-flow

Esta propriedade é uma forma abreviada para a escrita das propriedades flex-direction e *flex-wrap*, nesta ordem. Portanto, ela se aplica ao container.

Normalmente essas propriedades são definidas uma a uma, da seguinte forma:

```css
.container {
  display: flex;
 flex-direction: column;
04  flex-wrap: wrap;
05 }
```

Já com o flex-flow podemos escrever as duas de forma simplificada:

```css
flex-flow: column wrap;
```

### justify-content

A propriedade *justify-content* define o alinhamento dos itens ao longo do eixo principal do container. A sintaxe e os valores possíveis para essa propriedade são apresentados a seguir:

```css
.container {
     display: flex;
     justify-content: [flex-start/flex-end/center/space-between/space-around];
 }
```

- **flex-start (padrão)**: Os itens são alinhados a partir do início do eixo principal;
- **flex-end**: Os itens são alinhados a partir do fim do eixo principal;
- **center**: Os itens são alinhados ao centro do eixo principal;
- **space-between**: O primeiro item é deslocado para o início do eixo principal, o último é deslocado para o final do eixo principal e os demais são distribuídos uniformemente entre eles;
- **space-around**: Os itens são uniformemente distribuídos ao longo do eixo principal. Aqui, porém, são atribuídas margens iguais à esquerda e à direita (ou acima e abaixo, dependendo da direção do eixo principal). Por isso o primeiro e o último item não ficam “colados” nas bordas do container.

A **Figura 4** ilustra o funcionamento de cada valor:

![Representação da propriedade justify-content](https://arquivo.devmedia.com.br/artigos/Fernando_gaspar/flex/justify-content.png)

### align-content

Essa propriedade define como as linhas são distribuídas ao longo do eixo transversal do container. Ela só terá efeito se o elemento tiver mais de uma linha, ou seja, se ele tiver elementos suficientes para quebrar a linha e a propriedade flex-wrap:wrap tiver sido definida. A sintaxe e os valores possíveis para essa propriedade são apresentados a seguir:

```css
.container {
     display: flex;
     align-content: [stretch/flex-start/flex-end/center/space-between/space-around];
 }
```

- **stretch** (padrão): As linhas são distribuídas uniformemente ao longo do eixo transversal, ocupando todo o espaço disponível;
- **flex-start**: As linhas são distribuídas a partir do início do eixo transversal;
- **flex-end**: As linhas são distribuídas a partir do fim do eixo transversal;
- **center**: As linhas são mantidas no centro do eixo transversal;
- **space-between**: A primeira linha é deslocada para o início do eixo transversal, a última é deslocada para o final do eixo transversal e as demais são distribuídas uniformemente entre eles;
- **space-around**: As linhas são uniformemente distribuídas ao longo do eixo transversal. Aqui, porém, são atribuídas margens iguais à esquerda e à direita (ou acima e abaixo, dependendo da direção do eixo transversal). Por isso a primeira e a última linha não ficam “coladas” nas bordas do container.

A **Figura 5** ilustra o funcionamento de cada valor:

![Funcionamento da propriedade align-content](https://arquivo.devmedia.com.br/artigos/Fernando_gaspar/flex/align-content.png)

### align-items

Essa propriedade define como os itens são distribuídos ao longo do eixo transversal do container. A sintaxe e os valores possíveis para essa propriedade são apresentados a seguir:

```css
.container {
  display: flex;
  align-items: [stretch/flex-start/flex-end/center/baseline];
 }
```

- **stretch** (padrão): Os itens serão esticados para preencher toda a dimensão do eixo transversal (altura ou largura);
- **flex-start**: Os itens são deslocadas para o início do eixo transversal;
- **flex-end**: Os itens são deslocadas para o final do eixo transversal;
- **center**: Os itens são centralizados no eixo transversal;
- **baseline**: Os itens são alinhados a partir da base da primeira linha de texto de cada um.

A **Figura 6** ilustra o funcionamento de cada valor:

![Representação da propriedade align-items](https://arquivo.devmedia.com.br/artigos/Fernando_gaspar/flex/align-items.png)

### Order

Por padrão, os itens são distribuídos no container na ordem em que são inseridos no HTML. No entanto, essa ordem pode ser alterada por meio da propriedade order, cuja sintaxe vemos abaixo:

```css
.item2 {
  order: [número];
}
```

O valor numérico atribuído a essa propriedade define a ordem do item. Por exemplo, o valor 2 faz com que o item seja o segundo item ao longo do eixo principal, enquanto o valor -1 faz com que ele apareça antes do primeiro.

### flex-grow

Esta propriedade define a proporção com que um item deve crescer caso seja necessário. Por padrão seu valor é 0, o que indica que o item não deve crescer, e são aceitos apenas valores numéricos positivos.

A sintaxe dessa propriedade é a seguinte:

```css
.item2 {
  flex-grow: [número];
}
```

### flex-shrink

Esta propriedade define a proporção com que um item deve encolher caso seja necessário. Por padrão seu valor é 0, o que indica que o item não deve encolher, e são aceitos apenas valores numéricos positivos.

A sintaxe dessa propriedade é a seguinte:

```css
.item2 {
  flex-shrink: [número];
}
```

### flex-basis

O flex-basis define o tamanho inicial que um item deve ter antes que o espaço ao seu redor seja distribuído. Ou seja, dependendo da direção do eixo principal (horizontal ou vertical), essa propriedade define a largura ou altura mínima do elemento antes que ele seja redimensionado por outras propriedades.

A sintaxe dessa propriedade é a seguinte:

```css
.item2 {
  flex-basis: [número];
}
```

O valor atribuído a essa propriedade pode ser em percentual, em pixels, ou a palavra auto, que é o valor padrão (considera as dimensões do item - width e height).

### flex

Esta propriedade é uma forma abreviada para a escrita das propriedades *flex-grow*, *flex-shrink* e *flex-basis*, nesta ordem.

A sintaxe dessa propriedade é a seguinte:

```css
.item2 {
  flex: [flex-grow] [flex-shrink] [flex-basis];
}
```

### align-self

Esta propriedade permite sobrescrever no item o comportamento que foi definido pela propriedade align-items.

A sintaxe e os valores possíveis para essa propriedade são apresentados a seguir:

```css
.item2 {
     align-self: [auto/stretch/flex-start/flex-end/center/baseline];
 }
```

- **auto** (padrão): Respeita o comportamento definido no container por meio do align-items;
- **stretch**: O item será esticado para preencher toda a dimensão do eixo transversal (altura ou largura);
- **flex-start**: O item é deslocado para o início do eixo transversal;
- **flex-end**: O item é deslocado para o final do eixo transversal;
- **center**: O item é centralizado no eixo transversal;
- **baseline**: O item é alinhado a partir da base da primeira linha de texto dos demais.





## Referências:

[CSS básico - Aprendendo desenvolvimento web | MDN (mozilla.org)](https://developer.mozilla.org/pt-BR/docs/Learn/Getting_started_with_the_web/CSS_basics)

[A Complete Guide to Flexbox | CSS-Tricks - CSS-Tricks](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

[CSS Flexbox Container (w3schools.com)](https://www.w3schools.com/csS/css3_flexbox_container.asp)

[CSS Flexbox Items (w3schools.com)](https://www.w3schools.com/csS/css3_flexbox_items.asp)

[CSS3 Flexbox: Funcionamento e propriedades (devmedia.com.br)](https://www.devmedia.com.br/css3-flexbox-funcionamento-e-propriedades/29532#grow)
