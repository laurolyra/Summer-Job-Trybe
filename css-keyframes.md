# Animações CSS - _Keyframes_ (7.2)

Você aprendeu até agora que o HTML é uma liguagem de marcação que te permite estruturar páginas web.

Correto.

Aprendeu, também, que o javascript é a linguagem de programação responsável por permitir interatividade da página com os eventos que ocorrem nela (como cliques, teclas apertadas e o mover do mouse).

Certo também.

Após algumas aulas, ficou claro que o CSS é uma poderosa ferramenta para estilização de páginas, podndo aplicar _designs_ atrativos, alterando cor de font, fundo, opacidade, altura, largura da seção e etc.

Correto? Não totalmente.

Nesta aula você aprenderá que o famigerado _Cascading Style Sheets_ é responsável por atribuir animaçoẽs à sua página HTML, tornando-a mais atrativa ainda!

---

## Você será capaz de:

- Criar suas primeiras animações em ppáginas HTML;
- Aprender os primeiros conceitos para a implementação de animações nas páginas por meio das _animation-properties_;
- Estipular cada movimento que sua animação realizará por meio dos estágios de animação.

---

## Por que isso é importante?

Animações em CSS são uma ótima ferramenta para ter uma página atraente, dinâmica e, principalmente, mais leve e estável, visto que ela não dependerá de carregamento de scripts, tampouco de recursos externos ao seu site para ter toda a fluidez e dinamismo necessários. 

---

## Conteúdo

Como dito acima, o nosso querido CSS também nos permite implementar animações em páginas web. Neste primeiro momento, veremos como aplicar uma animação que implicará na mudança de uma propriedade CSS.

Para tanto,comecemos com a criação de um HTML qualquer com a seguinte marcação:

    <div class="square"></div>

E este seria seu CSS:

    .square {
      background: red;
      height: 100px;
      width: 100px;
    }

Como você já consegue perceber, as propriedades acima permitem exibir na tela a criação de um quadrado vermelho, com 100 pixels de lado.

Neste primeiro momento, é necessário implementar a propriedade `animation`, a qual permite a indicação de diversos valores, sendo os dois primeiros o nome da animação e a sua duração. **Estes dois valores são obrigatórios.**

Neste exemplo, vamos dar o nome da animação de `trybe-test` e atribuir a duração de 2 segundos:

    .square {
      animation: trybe-test 2s;
      background: red;
      height: 100px;
      width: 100px;
    }

Etabelecidas essas duas propriedades básicas da animação, estamos aptos a criar `keyframes`, que nada mais são do que as coordenadas a serem seguidas pelo nosso elemento estilizado. Faremos, então, uma animação em que o quadrado se transformará num retângulo, mantendo seus 100 pixels de altura, mas se estendendo a 300 pixels de comprimento.

Para tanto, devemos inserir os `keyframes` após as regras da animação (preferenciamente ao final do arquivo CSS):

    @keyframes trybe-test {
      0% {
        width: 100px;
      }
      100% {
        width: 300px;
      }
    }

O código acima atribuiu dois estágios da animação: o seu momento inicial e seu momento final. Seguindo as diretrizes propostas, apontamos a largura inicial em conformidade com o CSS descrito anteriormente (100px) e, em seguida, o novo valor da largura, transformando a classe "square" em um retângulo de 300px x 100px.

O resultado final pode ser conferido [neste link](https://codepen.io/laurolyra/pen/NWqONaY).

Algumas informações merecem destaque: a um, a animação passou por dois estágios: o momento inicial (0%) e o final (100%) - sendo este o único obrigatório na implementação de uma animação. É perfeitamente possível a adição de estágios intermediários dentre esse intervalo.

A dois, note que não é necessário transcrever todas as propriedades do CSS que será animado, mas somente aquelas que serão afetadas pelo `keyframe` (aqui trouxemos só a propriedade `width`). É possível, inclusive, atribuir novas propriedades da mesma forma que você faria com um CSS inanimado.

Por fim, assim como `margin` e `border`, por exemplo, a propriedade `animation` aceita muitos (muitos!) valores. Todavia, visando uma melhor compreensão do assunto (e para um código de melhor manutenção e legibilidade), recomenda-se, sempre que possível, aplicar cada propriedade da animação e seu respectivo valor separadamente. Dessa forma, após uma pequena refatoração, nosso código seria o seguinte:

    .square {
      animation-name: trybe-test;
      animation-duration: 2s;
      background: red;
      height: 100px;
      width: 100px;
    }
Sabendo disso, que tal experimentarmos um pouco? abra o editor do nosso código e altere a animação como você quiser! teste uma mudança de cores, teste novas instruções intermediárias, aplique novas propriedades ao longo do tempo, enfim, fique à vontade! Mas volte aqui porque ainda tem conteudo e exercício pra fazer, viu?

Agora que você aprendeu as duas principais propriedades para a animação - `animation-name` e `animation-duration` - saiba que existem muitas outras, tais como `animation-fill-mode` (que determina quais estilos de animação estarão visíveis), `animation-direction` (que detemrina se a animação será executada em seu sentido normal, ao contrário ou alternada), `animation-iteration-count` (que especifica o número de vezes que a animação será executada), `animation-delay` (que aponta em quanto tempo a animação iniciará), dentre várias outras.

Em apertadísismo resumo: tenha em mente que a animação nada mais é do que uma propriedade do CSS, podendo ser manipulada como todas as outras (inclusive via javaScript!) - diferindo somente pelos `keyframes` inseridos ao final do arquivo.

---
## Exercícios

Agora, é a sua vez de criar várias animações.

Comece criando uma página html com um menu de navegação, colocando pelo menos 5 itens, bem como uma divisória ao final. Coloque o texto que quiser em cada item, mas deixe a divisória sem texto.

Agora, faça o seguinte:

1- No primeiro item, crie uma animação de 6 segundos que comece com a cor de texto diferente da inicial e alterne entre outras 5 cores (no total, seu texto terá tido seis cores diferentes além da inicial) e, ao final, tenha sua fonte aumentada para 50 pixels;

2- No segundo, tenha um texto que produza uma sombra preta. Não coloque propriedades iniciais de sombra nele. A animação deverá durar 6 segundos.

3- No terceiro, crie uma animação que, após dois segundos, se inicie. O item da lista deverá ser deslocado para o centro da tela na metade do tempo e retornará para sua posição inicial ao final. Use somente estágios da animação para fazer esse requisito.

4- Tenha um item que, ao colocar o mouse sobre ele, deverá iniciar com o tamanho de 20 pixels. A animação deverá durar 2 segundos, deverá ficar com 60 pixels ao final e manter esse tamanho enquanto o mouse estiver por cima desse item.

5- Tenha um item que apareça e desapareça da tela infinitamente e de forma bem rápida. A transição entre aparecer e desaparecer deverá ser gradual;

6- Na divisória sem texto, crie um retângulo que deverá preencher 100% da largura tela ao longo de 2 segundos, simulando uma barra de carregamento;

7(Bônus) - Exiba um alerta na sua página quando uma de suas animações terminar.

---

## Recursos adicionais

- [CSS animation for beginners](https://thoughtbot.com/blog/css-animation-for-beginners);
- [Codex CSS animations por Origamid](https://www.origamid.com/codex/css-animation/);
- [CSS animations por W3Schools](https://www.w3schools.com/css/css3_animations.asp);
