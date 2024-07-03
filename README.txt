https://www.youtube.com/watch?v=qYFkQa0Bbq0&ab_channel=OnlineTutorials

Esse código CSS e HTML cria uma barra de progresso animada que representa visualmente o quanto a página foi rolada. Vou explicar linha por linha:

### CSS:
1. `::-webkit-scrollbar`: Estiliza a barra de rolagem do navegador no Chrome.
   - `width: 0;`: Define a largura da barra de rolagem como zero, removendo-a.

2. `#scrollPath`: Estiliza o elemento de caminho de rolagem.
   - `position: fixed;`: Define a posição fixa do elemento.
   - `top: 0; right: 0;`: Posiciona o elemento no canto superior direito da tela.
   - `width: 10px; height: 100%;`: Define a largura como 10 pixels e a altura como 100% da tela.
   - `background: rgba(255, 255, 255, 0.05);`: Define um fundo semitransparente para o elemento.

3. `#progressbar`: Estiliza a barra de progresso.
   - `position: fixed;`: Define a posição fixa do elemento.
   - `top: 0; right: 0;`: Posiciona o elemento no canto superior direito da tela.
   - `width: 10px;`: Define a largura como 10 pixels.
   - `background:linear-gradient(to top, #008aff, #00ffe7);`: Define um gradiente linear como fundo da barra de progresso.
   - `animation: animate 5s linear infinite;`: Aplica uma animação chamada `animate` à barra de progresso, com duração de 5 segundos, função de temporização linear e loop infinito.

4. `@keyframes animate`: Define a animação `animate`.
   - `0%, 100%`: Define o estado inicial e final da animação, onde a propriedade `filter` é aplicada com `hue-rotate(0deg)`.
   - `50%`: Define o estado intermediário da animação, onde a propriedade `filter` é aplicada com `hue-rotate(360deg)`.

5. `#progressbar::before`: Estiliza o pseudo-elemento `::before` da barra de progresso.
   - `content: '';`: Adiciona conteúdo ao pseudo-elemento.
   - `position: absolute;`: Define a posição absoluta do pseudo-elemento.
   - `top: 0; right: 0;`: Posiciona o pseudo-elemento no canto superior direito da barra de progresso.
   - `width: 10px; height: 100%;`: Define a largura como 10 pixels e a altura como 100% da barra de progresso.
   - `background:linear-gradient(to top, #008aff, #00ffe7);`: Define um gradiente linear como fundo do pseudo-elemento.
   - `filter: blur(30px);`: Aplica um desfoque ao pseudo-elemento.

6. `#progressbar::after`: Estiliza o pseudo-elemento `::after` da barra de progresso (similar ao `::before`).

### HTML:
- `<div id="progressbar"></div>`: Cria o elemento que representa a barra de progresso.
- `<div id="scrollPath"></div>`: Cria o elemento que representa o caminho de rolagem.
- `<section></section>`: Cria uma seção na página.

### JavaScript:
- O JavaScript atualiza a altura da barra de progresso conforme a página é rolada, ajustando dinamicamente a altura do elemento de barra de progresso com base na quantidade de rolagem da página.