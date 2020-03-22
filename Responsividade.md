# Layout responsivo

* [Aula 1](#aula-1)
  * [O que é layout responsivo?](#o-que-é-layout-responsivo)
  * [Alguns princípios do design responsivo](#alguns-princípios-do-design-responsivo)
  * [Porque layout responsivo é 😍 ](#porque-layout-responsivo-é-)
  * [Porque layout responsivo é 🤦 ](#porque-layout-responsivo-é--1)
  * [Resolução de tela x tamanho de tela](#resolução-de-tela-x-tamanho-de-tela)
  * [Quando vale a pena ter um site com](#quando-vale-a-pena-ter-um-site-com)
  * [Técnicas de layout responsivo que vamos aprender](#técnicas-de-layout-responsivo-que-vamos-aprender)
    * [Grid fluído](#grid-fluído)
    * [Media queries](#media-queries)
  * [Breakpoints utilizados em aula](#para-facilitar-a-nossa-vida-em-aula-nós-vamos-utilizar-os-seguintes-breakpoints)

***

## Aula 1

#### O que é layout responsivo?

![responsive](https://media.giphy.com/media/b2CD0Qrq2ulwY/giphy.gif)

Hoje em dia temos uma enorme variedade de dispositivos onde um site pode ser visualizado (laptops, tablets, netbooks, celulares, desktops com tela pequena, iMacs com telas gigantescas, televisão, etc.). Seria inviável (e enlouquecedor) desenhar uma versão específica de um site para cada tamanho e resolução de tela disponíveis no mercado.

![many devices](images/many-devices.jpg)

O design responsivo é uma das soluções (design responsivo não é uma técnica, é um conceito) para nos ajudar a resolver esse problema. Um layout responsivo que é aquele que se adapta aos diversos tamanhos de telas existentes. É layout que vai se adaptar desde a tela de um celular até uma televisão de 42 polegadas.
No design responsivo o designer não apenas encolhe o conteúdo, mas adapta os elementos a fim de entregar ao usuário o melhor conteúdo e navegação para aquele cenário.

A ideia do layout responsivo surgiu em 2010, com um designer chamado Ethan Marcotte


* https://alistapart.com/article/responsive-web-design
* https://alistapart.com/d/responsive-web-design/ex/ex-site-flexible.html
* https://alistapart.com/d/responsive-web-design/ex/ex-site-linearize.html
* https://alistapart.com/d/responsive-web-design/ex/ex-site-FINAL.html


***

#### Alguns princípios do design responsivo:

* Adaptar o layout da página de acordo com a resolução em que está sendo visualizada;
* Redimensionar as imagens automaticamente para que caibam na tela e para que não sobrecarreguem a transferência de dados em um celular, por exemplo;
* Simplificar e/ou ocultar elementos da tela para dispositivos móveis;
* Adaptar tamanho de botões e links para interfaces touch onde o ponteiro do mouse é substituído pelo dedo do usuário;
* Utilizar de forma inteligente recursos mobile como mudança na orientação do aparelho (horizontal ou vertical).

***

#### Porque layout responsivo é 😍  

* UX friendly: mantém o mesmo design adaptado para diferentes formatos de tela, sempre pensando na melhor usabilidade para cada formato;
* É mais barato desenvolver um site responsivo do que ter que desenvolver versões diferentes do site, como uma versão mobile, por exemplo;
* É mais fácil dar manutenção, porque o código está todo em um lugar só (se tivesse uma versão mobile e um app, por exemplo, uma mudança de código teria que ser feita em três lugares);
* SEO friendly: como a aplicação só tem uma URL isso ajuda a manter todos os dados consistentes e a melhorar a posição no ranking do Google.

***

#### Porque layout responsivo é 🤦‍

![omg](images/too-many-devices.jpg)

* Normalmente os desenvolvedores testam o site nas principais resoluções/dispositivos disponíveis no mercado, porém é possível que em alguns dispositivos com formato de tela/resoluções não tão comuns o site não renderize conforme o esperado;
* Versões antigas do IE;
* Se o layout e a arquitetura do código não forem desenhadas antes de começar o trabalho, o site pode ficar muito difícil de manter/modificar;
* O site responsivo pode ser mais demorado para carregar (se tiver muitas imagens redimensionadas, se tiver muitas chamadas externas de scripts, etc.).

***

#### Resolução de tela x tamanho de tela

Resolução de tela: A resolução da tela de um dispositivo é o número de pixels em cada dimensão que podem ser exibidos.

Tamanho de tela: tamanho físico da tela, normalmente medido em polegadas

A resolução de monitores de dispositivos digitais indica o número de pontos (ou pixels) que compõem a imagem que aparece na tela. Uma tela com 1920 x 1080 mostra 1920 pontos em cada uma das 1080 linhas do monitor, ou 2.073.600 pixeis reais.

A qualidade da definição de uma imagem ou texto que aparece na tela depende da relação entre o número de pontos por polegada quadrada (ppi, pixels per inch) com que a tela está configurada, sua resolução nativa e o tamanho físico do monitor.

Dispositivos com o mesmo tamanho podem ter resoluções de tela diferentes (Exemplo: iPhone 3 e 4)

***

#### Quando vale a pena ter um site com:

* Layout responsivo
* Versão mobile/tablet
* App (aplicativo que você baixa no seu celular)


***

#### Técnicas de layout responsivo que vamos aprender

Grid fluído + media queries

***

#### Vamos começar?

#### Grid fluído

É o uso de % ao invés de valores absolutos (px) para definir tamanhos de elementos no css.
Essa é uma técnica que pode ser usada sempre, não apenas visando os layouts responsivos.

![omg](images/grid.jpg)

Um dos grids mais utilizados pelos designers e programadores é o grid de 12 colunas, pela facilidade de dividir por 2, 3, 4 e 6.

Vamos usar o exemplo fixo abaixo para calcular o tamanho em % de um layout.

![omg](images/calculo-fixo.jpg)

O cálculo que temos que sempre vamos utilizar é:

```
elemento / contexto = resultado
resultado * 100 = valor do elemento em porcentagem
```

No caso do layout acima, o cálculo seria (para o sidebar):
```
300 / 960 = 0,3125
0,3125 * 100 = 31,35
```

![omg](images/calculo-fluido.jpg)

***

#### Media queries

São breakpoints que modificam o CSS para cada resolução de tela.
Breakpoint em programação significa uma pausa em algum momente específico determinado pelo programador. No caso de breakpoints de css, são as resoluções de tela nas quais queremos modificar o conteúdo do site.

Com as media queries e os breakpoints vamos começar a adicionar um pouco de lógica no css.
O que vai acontecer é que o browser vai ler a folha de estilos, e **SE** a condição for verdadeira, ela vai executar o bloco de código, **SENÃO** ele vai apenas ignora-lo.

***

**Importante:** Quando formos utilizar media queries, o primeiro passo é adicionar uma metatag chamada viewport no <head> do site. Essa tag vai passar instruções para o browser renderizar o conteúdo do site conforme o tamanho do dispositivo.

```html
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link href="css/style.css" rel="stylesheet">
</head>
```

*Se [largura do dispositivo] for menor ou igual a 768px, então execute o {...}*
```css
@media (max-width: 768px) {
  .nome-da-classe {
    color: #fff; /* elemento que vai ser modificado/adicionado/sobrescrito nessa resolução */
  }
}
```


*Se [largura do dispositivo] for maior ou igual a 768px, então execute o {...}*
```css
@media (min-width: 768px) {
  .nome-da-classe {
    color: #fff; /* elemento que vai ser modificado/adicionado/sobrescrito nessa resolução */
  }
}
```

*Se [largura do dispositivo] for entre 768px e 600px, então execute o {...}*
```css
@media (max-width: 768px) and (min-width: 600px) {
  .nome-da-classe {
    color: #fff; /* elemento que vai ser modificado/adicionado/sobrescrito nessa resolução */
  }
}
```


```css
/* esse é um bloco normal de css, o browser vai ler e mostrar esses valores na tela do usuário */
.box {
  border: 1px solid #000;
  width: 320px;
  height: 120px;
  background-color: red;
}

/* esse é um bloco condicional, o browser vai ler e mostrar esses valores na tela do usuário SE a resolução da tela for menor que 768px */
@media (max-width: 768px) {
  .box {
    background-color: blue;
  }
}

/* esse é um bloco condicional, o browser vai ler e mostrar esses valores na tela do usuário SE a resolução da tela for menor que 420px */
@media (max-width: 420px) {
  .box {
    width: 100%;
    background-color: yellow;
  }
}
```


#### Para facilitar a nossa vida, em aula nós vamos utilizar os seguintes breakpoints:

```
1280px (desktop)
1024px (tablet - horizontal)
768px (tablet - vertical)
420px (mobile)
```

***
