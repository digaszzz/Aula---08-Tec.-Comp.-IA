
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Você decide o futuro da IA</title>
</head>
<body>
  <main class="caixa-principal">
    <h1>Você decide o futuro da IA</h1>

    <!-- Primeira tela -->
    <section class="tela-entrada">
      <p class="subtitulo">O futuro está nas suas mãos.</p>
      <button class="entrar-btn">Entrar</button>
    </section>

    <!-- Introdução da missão -->
    <section class="tela-inicial" hidden>
      <p>
        Novembro de 2022. A humanidade se viu em uma realidade
        perturbadora. As máquinas evoluíram para além do que
        imaginávamos.

        Agora, elas escrevem, falam e criam imagens de um jeito
        tão parecido com humanos que é quase impossível
        diferenciá-las.

        Em meio a esse cenário, uma missão surgiu: explorar
        o impacto da Inteligência Artificial em nossas vidas
        e confrontar as possibilidades que o futuro nos reserva.

        O mundo nunca mais será o mesmo.
      </p>
      <button class="iniciar-btn">Iniciar missão</button>
    </section>

    <!-- Perguntas e alternativas -->
    <section class="caixa-jogo" hidden>
      <p class="progresso"></p>
      <div class="caixa-perguntas"></div>
      <div class="caixa-alternativas"></div>
    </section>

    <!-- Resultado final -->
    <section class="caixa-resultado" hidden>
      <p class="etiqueta">RELATÓRIO DO FUTURO · 2049</p>
      <h2 class="titulo-resultado">O futuro que você construiu</h2>
      <p class="texto-resultado"></p>
      <button class="novamente-btn">Jogar novamente</button>
    </section>

    <footer>
      <span>MISSÃO IA</span>
      <span>O futuro depende das escolhas.</span>
    </footer>
  </main>
</body>
</html>


@import url('https://fonts.googleapis.com/css2?family=Chakra+Petch:wght@400;500;600;700&family=Inter:wght@400;500;600;700&display=swap');

:root {
  --cor-fundo: #01080e;
  --cor-principal: #0b0d20;
  --cor-secundaria: #212333;
  --cor-destaque: #2bdefd;
  --cor-texto: #d7f9ff;
  --cor-suave: #9cb9c5;
}

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  min-height: 100vh;
  padding: 24px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  background:
    radial-gradient(ellipse at top, #10283a 0%, transparent 60%),
    var(--cor-fundo);
  color: var(--cor-texto);
  font-family: "Inter", sans-serif;
}

.caixa-principal {
  position: relative;
  width: 90%;
  max-width: 720px;
  padding: 36px;
  overflow: hidden;
  background: var(--cor-principal);
  border: 1px solid #263c51;
  border-radius: 18px;
  box-shadow: 0 0 45px #2bdefd12;
}

h1 {
  margin: 0 0 28px;
  color: var(--cor-destaque);
  font-family: "Chakra Petch", sans-serif;
  font-size: clamp(28px, 5vw, 42px);
  line-height: 1.15;
  text-align: center;
}

h2 {
  font-family: "Chakra Petch", sans-serif;
}

.subtitulo {
  color: var(--cor-suave);
  text-align: center;
  margin-bottom: 30px;
}

.tela-entrada,
.tela-inicial {
  text-align: center;
  line-height: 1.8;
}

.tela-inicial p {
  white-space: pre-line;
}

button {
  width: 100%;
  margin-top: 14px;
  padding: 16px;
  background: var(--cor-secundaria);
  color: var(--cor-texto);
  border: 1px solid #33465a;
  border-radius: 10px;
  font: inherit;
  font-weight: 600;
  cursor: pointer;
  transition:
    background 0.2s,
    color 0.2s,
    border-color 0.2s,
    transform 0.2s;
}

button:hover {
  background: var(--cor-destaque);
  color: var(--cor-principal);
  border-color: var(--cor-destaque);
  transform: translateY(-2px);
}

button:focus-visible {
  outline: 3px solid white;
  outline-offset: 3px;
}

.progresso,
.etiqueta {
  color: var(--cor-destaque);
  font-family: "Chakra Petch", sans-serif;
  font-size: 12px;
  font-weight: 700;
  letter-spacing: 2px;
}

.caixa-perguntas {
  margin: 20px 0 26px;
  font-family: "Chakra Petch", sans-serif;
  font-size: 21px;
  line-height: 1.6;
}

.caixa-alternativas {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.caixa-alternativas button {
  margin: 0;
  text-align: left;
  line-height: 1.5;
}

.caixa-resultado {
  padding-top: 10px;
  line-height: 1.8;
}

.titulo-resultado {
  color: var(--cor-destaque);
  font-size: 27px;
}

.texto-resultado {
  white-space: pre-line;
  color: var(--cor-texto);
  line-height: 1.9;
}

footer {
  display: flex;
  justify-content: space-between;
  gap: 12px;
  margin-top: 35px;
  padding-top: 18px;
  border-top: 1px solid #263c51;
  color: var(--cor-suave);
  font-size: 10px;
  letter-spacing: 1px;
}

footer span:first-child {
  color: var(--cor-destaque);
  font-weight: 700;
}

[hidden] {
  display: none !important;
}

@media (max-width: 480px) {
  .caixa-principal {
    padding: 24px 18px;
  }

  .caixa-perguntas {
    font-size: 18px;
  }

  footer {
    flex-direction: column;
    text-align: center;
  }
}


const caixaPerguntas = document.querySelector(".caixa-perguntas");
const caixaAlternativas = document.querySelector(".caixa-alternativas");
const caixaJogo = document.querySelector(".caixa-jogo");
const caixaResultado = document.querySelector(".caixa-resultado");
const textoResultado = document.querySelector(".texto-resultado");
const progresso = document.querySelector(".progresso");

const telaEntrada = document.querySelector(".tela-entrada");
const telaInicial = document.querySelector(".tela-inicial");
const botaoEntrar = document.querySelector(".entrar-btn");
const botaoIniciar = document.querySelector(".iniciar-btn");
const botaoJogarNovamente = document.querySelector(".novamente-btn");

const nomes = [
  "Fernanda",
  "Giuliana",
  "Maria Eduarda",
  "Marcelo",
  "Amanda",
  "Gustavo",
  "Gabriel"
];

const perguntas = [
  {
    enunciado:
      "Assim que saiu da escola, você se depara com uma tecnologia capaz de responder dúvidas, gerar imagens e criar áudios realistas. Qual é seu primeiro pensamento?",
    alternativas: [
      {
        texto: "Isso é assustador!",
        afirmacao: [
          "No início, você ficou com medo do que essa tecnologia poderia fazer.",
          "Achou assustador pensar na velocidade com que a tecnologia estava avançando."
        ],
        proxima: 1
      },
      {
        texto: "Isso é maravilhoso!",
        afirmacao: [
          "Você quis descobrir como usar a Inteligência Artificial no dia a dia.",
          "A curiosidade falou mais alto, e você decidiu explorar as possibilidades dessa tecnologia."
        ],
        proxima: 2
      }
    ]
  },

  {
    enunciado:
      "Uma professora propõe um trabalho sobre Inteligência Artificial. Como você decide pesquisar o assunto?",
    alternativas: [
      {
        texto: "Usar uma ferramenta de IA para pesquisar e entender o conteúdo.",
        afirmacao: [
          "Você utilizou a IA como ponto de partida para aprender sobre o assunto.",
          "A tecnologia ajudou você a organizar as ideias e encontrar novas informações."
        ],
        proxima: 3
      },
      {
        texto: "Pesquisar em diferentes fontes e escrever com suas próprias palavras.",
        afirmacao: [
          "Você preferiu construir o trabalho com suas próprias palavras e pesquisas.",
          "Decidiu comparar diferentes fontes antes de formar uma opinião."
        ],
        proxima: 4
      }
    ]
  },

  {
    enunciado:
      "Durante um debate, a turma discute como a IA pode transformar os empregos do futuro. Qual é sua posição?",
    alternativas: [
      {
        texto: "Precisamos proteger trabalhadores que podem perder seus empregos.",
        afirmacao: [
          "Você passou a refletir sobre os trabalhadores que podem ser afetados pela automação.",
          "Percebeu que o avanço tecnológico também exige responsabilidade social."
        ],
        proxima: 4
      },
      {
        texto: "A IA pode criar oportunidades e ajudar as pessoas.",
        afirmacao: [
          "Você enxergou possibilidades de novas profissões e oportunidades.",
          "Acreditou que as pessoas poderiam aprender novas habilidades com a ajuda da IA."
        ],
        proxima: 5
      }
    ]
  },

  {
    enunciado:
      "Seu trabalho precisa de informações geradas por IA. Como você garante que o resultado seja confiável?",
    alternativas: [
      {
        texto: "Conferir as informações em fontes confiáveis e corrigir possíveis erros.",
        afirmacao: [
          "Você conferiu as informações e percebeu que a IA também pode cometer erros.",
          "Aprendeu que verificar as fontes é essencial antes de compartilhar qualquer informação."
        ],
        proxima: 6
      },
      {
        texto: "Entregar o resultado sem revisar, pois a IA parece muito inteligente.",
        afirmacao: [
          "Você confiou demais na resposta automática e não percebeu algumas informações incorretas.",
          "Descobriu que respostas convincentes nem sempre são respostas verdadeiras."
        ],
        proxima: 7
      }
    ]
  },

  {
    enunciado:
      "Você precisa criar uma imagem para apresentar suas ideias sobre o futuro. Qual caminho escolhe?",
    alternativas: [
      {
        texto: "Criar a imagem manualmente usando uma ferramenta de desenho.",
        afirmacao: [
          "Você explorou sua criatividade desenhando a própria representação do futuro.",
          "Descobriu que ferramentas tradicionais também podem transformar boas ideias em imagens."
        ],
        proxima: 6
      },
      {
        texto: "Experimentar um gerador de imagens com Inteligência Artificial.",
        afirmacao: [
          "Você experimentou gerar imagens com IA e percebeu como os comandos influenciam o resultado.",
          "Descobriu novas possibilidades criativas ao combinar suas ideias com ferramentas de IA."
        ],
        proxima: 7
      }
    ]
  },

  {
    enunciado:
      "Uma empresa começa a usar IA em várias atividades. O que você considera mais importante para o futuro do trabalho?",
    alternativas: [
      {
        texto: "Preparar as pessoas para aprender novas habilidades.",
        afirmacao: [
          "Você percebeu que aprender continuamente pode ajudar as pessoas a enfrentar mudanças.",
          "Passou a valorizar a educação e a adaptação diante das novas tecnologias."
        ],
        proxima: 7
      },
      {
        texto: "Permitir que as máquinas decidam tudo com mais rapidez.",
        afirmacao: [
          "Você priorizou a rapidez das máquinas, mas começou a questionar os limites dessa escolha.",
          "Percebeu que decisões automatizadas também podem trazer consequências inesperadas."
        ],
        proxima: undefined
      }
    ]
  },

  {
    enunciado:
      "Antes de publicar um conteúdo criado com IA, qual atitude você toma?",
    alternativas: [
      {
        texto: "Revisar o conteúdo e deixar claro quando a IA foi utilizada.",
        afirmacao: [
          "Você escolheu usar a tecnologia com transparência e responsabilidade.",
          "Entendeu que criatividade e honestidade precisam caminhar juntas."
        ],
        proxima: undefined
      },
      {
        texto: "Publicar imediatamente, sem verificar a origem das informações.",
        afirmacao: [
          "Você percebeu que compartilhar conteúdo sem conferir pode espalhar informações falsas.",
          "Aprendeu que a velocidade da tecnologia não elimina a responsabilidade de quem a utiliza."
        ],
        proxima: undefined
      }
    ]
  },

  {
    enunciado:
      "Em 2049, a sociedade precisa decidir como conviver com a Inteligência Artificial. Qual princípio deve orientar esse futuro?",
    alternativas: [
      {
        texto: "Desenvolver tecnologias com ética, segurança e supervisão humana.",
        afirmacao: [
          "Você defendeu um futuro em que a IA é utilizada com ética, segurança e responsabilidade.",
          "Concluiu que a tecnologia pode contribuir para a sociedade quando existem limites e supervisão."
        ],
        proxima: undefined
      },
      {
        texto: "Aceitar qualquer avanço tecnológico sem questionar suas consequências.",
        afirmacao: [
          "Você percebeu que aceitar toda novidade sem reflexão pode trazer riscos.",
          "Concluiu que o progresso precisa ser acompanhado de questionamento e responsabilidade."
        ],
        proxima: undefined
      }
    ]
  }
];

let atual = 0;
let perguntaAtual;
let historiaFinal = "";
let nome = "";
let jogoIniciado = false;

// Escolhe um elemento aleatório de qualquer lista não vazia.
function aleatorio(lista) {
  const posicao = Math.floor(Math.random() * lista.length);
  return lista[posicao];
}

// Personaliza os textos sem alterar permanentemente os enunciados.
function personaliza(texto) {
  return texto.replace(/\bvocê\b/gi, palavra => {
    return palavra[0] === palavra[0].toUpperCase()
      ? nome
      : nome;
  });
}

function mostraPergunta() {
  if (atual < 0 || atual >= perguntas.length) {
    mostraResultado();
    return;
  }

  perguntaAtual = perguntas[atual];

  progresso.textContent =
    "ETAPA " + (atual + 1) + " · MISSÃO IA";

  caixaPerguntas.textContent = personaliza(
    perguntaAtual.enunciado
  );

  caixaAlternativas.replaceChildren();

  mostraAlternativas();
}

function mostraAlternativas() {
  for (const alternativa of perguntaAtual.alternativas) {
    const botao = document.createElement("button");

    botao.textContent = personaliza(alternativa.texto);

    botao.addEventListener("click", () => {
      respostaSelecionada(alternativa);
    });

    caixaAlternativas.appendChild(botao);
  }
}

function respostaSelecionada(opcaoSelecionada) {
  if (!jogoIniciado) return;

  const afirmacoes = aleatorio(opcaoSelecionada.afirmacao);

  historiaFinal += personaliza(afirmacoes) + "\n\n";

  if (opcaoSelecionada.proxima !== undefined) {
    atual = opcaoSelecionada.proxima;
  } else {
    mostraResultado();
    return;
  }

  mostraPergunta();
}

function mostraResultado() {
  jogoIniciado = false;

  caixaJogo.hidden = true;
  caixaResultado.hidden = false;

  textoResultado.textContent =
    nome + ", esta foi a história construída pelas suas escolhas:\n\n" +
    historiaFinal +
    "O futuro da Inteligência Artificial não depende apenas das máquinas. " +
    "Ele também depende das decisões, dos valores e da responsabilidade das pessoas.";
}

function substituiNome() {
  // A personalização é aplicada ao exibir os textos.
  // Assim, um novo nome pode ser escolhido em cada partida.
  nome = aleatorio(nomes);
}

function iniciaJogo() {
  atual = 0;
  historiaFinal = "";
  jogoIniciado = true;

  substituiNome();

  telaEntrada.hidden = true;
  telaInicial.hidden = true;
  caixaResultado.hidden = true;
  caixaJogo.hidden = false;

  mostraPergunta();
}

function jogaNovamente() {
  atual = 0;
  historiaFinal = "";
  jogoIniciado = false;

  caixaResultado.hidden = true;
  caixaJogo.hidden = true;
  telaEntrada.hidden = false;
  telaInicial.hidden = true;
}

botaoEntrar.addEventListener("click", () => {
  telaEntrada.hidden = true;
  telaInicial.hidden = false;
});

botaoIniciar.addEventListener("click", iniciaJogo);
botaoJogarNovamente.addEventListener("click", jogaNovamente);

