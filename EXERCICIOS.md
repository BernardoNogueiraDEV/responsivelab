# Exercícios de responsividade

## 1. Identifique a estratégia

- A: `max-width: 100%` e `height: auto` limitam a imagem e preservam sua proporção.
- B: `display: flex` com `flex-wrap: wrap` permite quebrar o grupo de botões em linhas; `gap` mantém o espaçamento.
- C: `repeat(auto-fit, minmax(220px, 1fr))` cria quantas colunas couberem.
- D: use `flex-direction: column` na base e `flex-direction: row` dentro de uma Media Query com `min-width`.
- E: combine `width: 90%` e `max-width: 1200px`.

## 2. Encontre um breakpoint

Forçar duas colunas em 320px deixaria aproximadamente 120px para cada coluna da apresentação, considerando o container de 90% e o gap de 48px. O título ficaria fragmentado. A implementação mantém o empilhamento abaixo de 720px e passa para duas colunas a partir desse ponto, conforme o roteiro.

O desafio adicional usa 880px: nessa região, o container permite cerca de 500px para o texto principal e 250px para a lateral, além do espaçamento. Abaixo disso, a seção permanece empilhada.

## 3. Mobile First

A alternativa A começa com uma coluna e acrescenta a segunda quando há mais espaço. `min-width: 800px` inclui exatamente 800px.

## 4. Necessidade de Media Query

Não é obrigatória. `auto-fit` determina quantas colunas cabem e `minmax` limita suas dimensões. Com `auto-fill`, tracks vazios continuam reservados; com `auto-fit`, eles são recolhidos, permitindo que os artigos existentes preencham a linha.

## Decisões e verificação

A navegação usa Flexbox para distribuir os links, `flex-wrap` para quebrar linhas e `gap` para manter distância entre eles. A Media Query posiciona marca e navegação lado a lado. Os links têm altura mínima de 44px.

As grades usam `min(220px, 100%)` ou `min(260px, 100%)` dentro de `minmax`: preservam o mínimo desejado quando há espaço e permitem uma coluna menor se o próprio container for mais estreito. Textos longos podem quebrar sem serem ocultados.

Verificação automatizada no Edge em larguras de 280, 320, 375, 600, 719, 720, 879, 880, 999, 1000 e 1440px: nenhuma apresentou overflow horizontal. As notícias passaram de uma para duas e três colunas; a seção adicional passou a duas colunas em 880px.

As imagens são externas, como na estrutura inicial, e precisam de conexão para carregar.

## Entrega

No Canvas, enviar apenas a URL: https://github.com/BernardoNogueiraDEV/responsivelab
