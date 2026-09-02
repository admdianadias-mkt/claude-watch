# Benchmark de Concorrentes — Terra Negra
## Parte 1: Método, Limites e Mapa Competitivo

---

## ⚠️ Nota de método — leia antes de usar

Este documento foi produzido **sem assistir aos vídeos**. É importante que isso fique explícito, porque muda como você deve confiar em cada parte.

### O que foi tentado e falhou

A skill `/watch` deste repositório está funcional, mas o ambiente de execução **bloqueia todo o egress de rede**:

```
www.youtube.com   -> 403 CONNECT (policy denial)
youtu.be          -> 403
www.tiktok.com    -> 403
www.instagram.com -> 403
terranegra.online -> 403
thebranding.ai    -> 403
```

Pipeline verificado como pronto: `yt-dlp` instalado, `ffmpeg` 7.0.2 instalado, scripts `watch.py` / `frames.py` / `hook.py` / `report.py` presentes. **O único bloqueio é a política de rede da organização.** A tentativa foi repetida e o resultado foi idêntico.

### Consequência direta para este documento

| Camada | Origem | Confiança |
|---|---|---|
| Quem são os concorrentes | Pesquisa web real (fontes citadas) | **Alta** — dados públicos verificáveis |
| Números de audiência | Pesquisa web real | **Alta** — mas checar data |
| Assinatura de formato de cada concorrente | Descrição pública dos canais | **Média** — é o que se diz do canal, não frame a frame |
| Estruturas dos vídeos (Parte 2) | Arquétipos consolidados de short-form + assinatura pública | **Inferida** — *não* extraída dos vídeos |
| Roteiros adaptados (Parte 3) | Construção autoral sobre o acima | Autoral |

**O que isto NÃO é:** engenharia reversa. Engenharia reversa exige extrair o corte real, o beat real, a palavra que caiu no frame real. Isso não aconteceu. As estruturas da Parte 2 são arquétipos que eu reconheço como dominantes no formato — não medições das peças dos concorrentes.

**A referência `thebranding.ai` não pôde ser consultada** (domínio bloqueado, e busca web não retornou o framework proprietário deles). Nada neste documento deriva dela. Se ela é central para você, é o primeiro gap a fechar.

### Como fechar o gap depois

```bash
/plugin marketplace add taoufik123-collab/claude-watch
/plugin install watch@claude-watch

/watch <url-do-concorrente> extraia a estrutura exata: corte a corte, o que
está na tela em cada beat dos primeiros 10s, quando entra a primeira troca de
enquadramento, onde está o loop de retenção, e onde entra o CTA
```

Rodando localmente (onde o YouTube é acessível), a Parte 2 deixa de ser inferência e vira medição. **Marque a Parte 2 como hipótese até isso acontecer.**

---

## Contexto Terra Negra (base da adaptação)

Levantado por pesquisa pública:

- **O que é:** plataforma de Ciências Humanas para ENEM e vestibulares (FUVEST, UNICAMP, paulistas)
- **Origem:** coletivo nascido em **2005**; internet desde **2015**
- **Escala:** ~700–800 aulas gravadas em estúdio profissional; +10 milhões de views; +10 mil aprovações
- **Equipe:** professores de Geografia, História, Filosofia e Sociologia, +20 anos de pré-vestibular presencial (incluindo Bernoulli)
- **Selo:** ScienceVlogs Brasil — chancela de divulgação científica
- **Produtos:** Sniper de Humanas, Intensivo K2, Live de Revisão
- **Diferencial de origem:** vídeos de **expedição** gravados em campo, pelo Brasil e pelo mundo

### Os 4 ativos que ninguém consegue copiar

Isto é o que deve ancorar a adaptação — não adianta imitar formato sem apoiar no que só a Terra Negra tem:

1. **Expedição / campo real.** Concorrente nenhum da lista grava geografia *no lugar*. Um vídeo sobre desertificação gravado no sertão não é reproduzível por um canal de estúdio. **É o maior ativo desperdiçado se ficar só no acervo.**
2. **20 anos de sala presencial.** Você sabe *qual erro o aluno comete*, não só qual é a resposta. Isso é o combustível do arquétipo "autópsia de erro".
3. **Selo ScienceVlogs.** Autoridade científica formal num nicho onde muito concorrente é entretenimento. Diferencial em temas polêmicos.
4. **Quatro disciplinas sob o mesmo teto.** Os concorrentes são majoritariamente monodisciplinares (história, sobretudo). Conexão Filosofia↔Sociologia↔História↔Geografia numa peça só é território livre.

---

## Mapa competitivo

Concorrentes identificados por pesquisa pública. Números conforme reportado nas fontes — **revalide antes de usar em apresentação**.

### 1. Débora Aladim
- **Escala:** +4,3 milhões de seguidores somados; um vídeo de opinião sobre o ENEM passou de **4 milhões de views**
- **Perfil:** historiadora, graduada em História pela UFMG, produz videoaulas desde 2013
- **Assinatura:** comentário com humor sobre o ENEM; **reação à prova em tempo real** — no ENEM 2024 dominou o X/Twitter ao anunciar que estava com a prova em mãos
- **Por que viraliza:** ancoragem em evento. Ela não compete por atenção o ano todo — ela captura o pico em que o país inteiro busca "ENEM" ao mesmo tempo
- **Lição para a Terra Negra:** o ativo não é o conteúdo, é o **timing**. A janela de 48h do ENEM vale mais que 3 meses de posting regular

### 2. Se Liga Nessa História
- **Escala:** +1 milhão de inscritos
- **Perfil:** professor Walter Solla + produtor Ary Neto
- **Assinatura:** história brasileira e mundial **dramatizada**; conteúdo de entretenimento, com atualidades, Sociologia e Filosofia
- **Por que funciona:** a dupla professor+produtor separa quem sabe de quem edita. Valor de produção acima da média do nicho
- **Lição:** dramatização não é enfeite — é o que permite reter em tema árido

### 3. Eduardo Bueno (Buenas Ideias)
- **Escala:** +600 mil inscritos
- **Perfil:** pesquisador e escritor
- **Assinatura:** quadros nomeados — **"Não vai cair no ENEM"** e "Ora, pílulas"
- **Por que funciona:** "Não vai cair no ENEM" é um golpe de posicionamento. Ele usa a **negação do vestibular** como isca de curiosidade para um público que está estudando para o vestibular
- **Lição:** o quadro nomeado e recorrente cria hábito. É o formato mais subutilizado pela Terra Negra

### 4. Leitura ObrigaHISTÓRIA
- **Escala:** 271 mil inscritos
- **Perfil:** historiadores Icles Rodrigues e Luana Jalles + cientista social Mariane Pisani
- **Assinatura:** rigor historiográfico, correção de erro histórico, divulgação científica
- **Por que funciona:** ocupa a faixa "confiável" — cresce em cima do erro dos outros
- **Lição:** é o concorrente mais próximo do território ScienceVlogs da Terra Negra. Disputa direta

### 5. Descomplica
- **Escala:** operação comercial de grande porte
- **Assinatura:** cobertura completa de História, Geografia, Sociologia e Filosofia com narrativa e base teórica
- **Por que funciona:** volume e SEO. Cobre tudo
- **Lição:** não dá para vencer no volume. Vence-se na profundidade e no campo

### 6. História Online
- **Perfil:** foco em Humanas, professores de cursinhos de São Paulo
- **Assinatura:** posicionamento por qualificação docente
- **Lição:** concorrente direto no argumento "nossos professores são melhores". Se esse é seu único diferencial, ele já está tomado — **por isso o campo/expedição importa tanto**

---

## Leitura estratégica

**Onde o nicho está saturado:** videoaula de estúdio explicando conteúdo. Todo mundo faz. Descomplica faz em escala industrial.

**Onde há espaço livre:**

| Espaço | Por que está livre | Ativo da Terra Negra que ocupa |
|---|---|---|
| Geografia em campo | Caro e trabalhoso; ninguém faz | Acervo de expedição |
| Conexão entre as 4 disciplinas | Concorrentes são monodisciplinares | Equipe completa |
| Autópsia de erro do aluno | Exige dado de sala, não de câmera | 20 anos presenciais |
| Repertório de redação sistematizado | Tratado como acessório | Filosofia + Sociologia juntas |
| Rigor em tema polêmico | Entretenimento evita | Selo ScienceVlogs |

**Onde a Terra Negra está perdendo:** ancoragem em evento (Aladim domina) e quadro recorrente nomeado (Bueno domina). Ambos são recuperáveis — são decisões editoriais, não ativos.

---

**Fontes:** [Débora Aladim — Correio Braziliense](https://www.correiobraziliense.com.br/diversao-e-arte/2024/11/6980116-quem-e-debora-aladim-youtuber-que-viralizou-no-x-por-causa-do-enem.html) · [Débora Aladim — Rádio Itatiaia](https://www.itatiaia.com.br/brasil/2024/11/04/veja-quem-e-a-mineira-debora-aladim-youtuber-que-viralizou-por-causa-do-enem) · [Canais de Humanas — Quero Bolsa](https://querobolsa.com.br/revista/11-canais-do-youtube-para-estudar-humanas-para-o-enem) · [Canais de História — Quero Bolsa](https://querobolsa.com.br/revista/8-canais-do-youtube-para-quem-ama-historia) · [Terra Negra](https://terranegra.online/) · [Terra Negra — Quem somos](https://cursos.terranegra.online/info.aspx?page=quemsomos)
