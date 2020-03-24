# Animações CSS - _Keyframes_ (7.2)

Você aprendeu até agora que o HTML é uma liguagem de marcação que te permite estruturar páginas web.

Correto.

Aprendeu, também, que o javascript é a linguagem de programação repsonsável por permitir interatividade da página com os eventos que ocorrem nela (como cliques, teclas apertadas e o mover do mouse). 

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

- # Saber implementar.

---

# Conteúdo

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

Para iniciarmos a configuração inicial de nossa animação, é necessário implementar a propriedade `animation`, a qual permite a indicação de diversos valores, sendo os primeiros o nome da animação e a sua duração. **Estes dois valores são obrigatórios.**

Neste exemplo, vamos dar o nome da animação de `trybe-test` e atribuir a duração de 2 segundos:

    .square {
      animation: trybe-test 2s;
      background: red;
      height: 100px;
      width: 100px;
    }

Definidas essas duas propriedades básicas da animação, estamos aptos a criar `keyframes`, que servem para definir qual será a animação e como será seu comportamento ao longo do tempo. Faremos, então, uma animação em que o quadrado se transformará num retângulo, mantendo seus 100 pixels de altura, mas se estendendo a 300 pixels de comprimento.

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

O resultado final de nossa singela animação pode ser conferido [neste link](https://codepen.io/laurolyra/pen/NWqONaY).

Algumas informações merecem destaque: a um, toda animação precisa ter implementado pelo menos dois estágios: o momento inicial (0%) e o final (100%), sendo opcionais a adição de estágios intermediários dentre desse intervalo.

A dois, note que não é necessário transcrever todas as propriedades do CSS que será animado, mas somente aquelas que serão afetadas pelo `keyframe` (aqui trouxemos só a propriedade `width`).

Por fim, assim como `margin` e `border`, por exemplo, a propriedade `animation` aceita muitos (muitos!) valores. Todavia, para uma melhor compreensão do assunto (e para um código de melhor manutenção e legibilidade), recomenda-se, sempre que possível, aplicar cada propriedade da animação e seu respectivo valor separadamente. Dessa forma, após uma pequena refatoração, nosso código seria o seguinte:

    .square {
      animation-name: trybe-test;
      animation-duration: 2s;
      background: red;
      height: 100px;
      width: 100px;
    }

Dito isso, comecemos com as duas principais propriedades para a animação: `animation-name` e `animation-duration` que, como o nome diz, definem o nome da animação a ser criada e a sua duração, respectivamente.



Elaborar um conteúdo no _Estilo Trybe_ significa ter as seções:
- O que vamos aprender?
- Você será capaz de:
- Porque isso é importante?
- Conteúdos
- Exercícios
- Recursos Adicionais

Além disso, deve-se ter um gabarito num arquivo separado.

O arquivo do conteúdo **deve ser formatado em MarkDown. Concentre-se em transmitir o conhecimento com uma didática caprichada e acessível para o tempo certo**, isso é o ponto mais importante do desafio. Representada o que é o dia a dia de um Summer Jobber aqui na Trybe!

---

# Regras gerais

- Redação do conteúdo deve estar gramaticalmente correta, no tom de voz e pessoa certas (se dirigindo diretamente a quem lê, como em "Você vai estudar...") e com linguagem neutra de gênero;

## Conteúdo

- **Um terço** do tempo alocado para os estudos deve ser dedicado a conteudo a ser lido e aprendido, **com exercícios de fixação acompanhando**;
- Todo o conteúdo deve ser original, feito **inteiramente por você**;
- É desejável que exista uma seção de _Recursos Adicionais_, com links e referências de bons materiais acerca do tema;
- O conteúdo deve ser **didático**: seu texto deve ensinar o conteúdo a uma pessoa que não sabe nada do assunto e **tem uma quantidade conhecimento correspondente ao bloco do curso em que tal conteúdo aparece**. Não deve ser denso demais, mas de fácil digestão e com raciocínio fácil de acompanhar. "Seus saltos de raciocínio" devem ser pequenos.

## Exercícios

- Dois terços do tempo alocados para a realização de exercícios acerca do tema;
- Todos os exercícios devem ser originais, **inteiramente feitos por você**;
- O enunciado dos exercícios deve ser claro e sem margem para subjetividade;
- Todos os exercícios devem ter sua resolução proposta num **gabarito**. Tal gabarito deve respeitar as regras de acessibilidade, do code climate e deve ser um exemplo a ser seguido de qualidade de código. Ele não pode conter nada que a turma não tenha aprendido até aquele momento;
- Devem haver exercícios bônus para quem terminar os exercícios mais rápido do que o esperado. Esses exercícios também precisam ter gabarito.
 Student Internship - Desafio Prático