# Slides da palestra (HTML)

Abra `index.html` no navegador (Chrome, Firefox, Edge). Funciona **offline**, sem instalar nada. Para levar,
copie a pasta `slides/` inteira (o `index.html` e a pasta `media/` com as animações).

| Tecla | Ação |
|---|---|
| `→` `Espaço` `Enter` ou clique | avança (revela o próximo item, depois o próximo slide) |
| `←` `Backspace` ou clique na borda esquerda | volta |
| `F` | tela cheia |
| `L` | alterna **português / espanhol** (também os botões PT/ES no canto) |
| `N` | notas do apresentador (fatos, fontes e cuidados) |
| `Home` / `End` | primeiro / último slide |

`index.html#7` abre direto no slide 7. Para ver todos os itens de uma vez (útil para revisar), use
`index.html?frags`; para abrir em espanhol, `index.html?es`.

## Como editar
Todo o texto está em `index.html`, na lista `S`. Cada trecho é `b('português','español')`. Uma linha com
`class="frag"` aparece só quando você avança. As animações são GIFs de `media/`, copiados de
`../animacoes/saida/`: se regenerar uma animação, copie o novo GIF para `media/`.

## Estrutura (24 slides)
1 capa · 2 a tese · 3–5 regras exatas (Newton, gás) · 6–8 regras simples (autômatos; o 8 mostra autômatos na ciência:
ondas no coração, trânsito, incêndios florestais) · 9–11 o acaso entra (DLA, epidemia) · **12–13 percolação e transição de fase** (nasce da epidemia e dos incêndios: "existe um
caminho?"; o limiar, o efeito do tamanho, a transição de fase e a ponte para o Monte Carlo) ·
14–20 Monte Carlo (Los Alamos, π histórico, agulha de Buffon, dardos, **19 do π ao Monte Carlo de verdade: amostragem por
importância / cadeia de Markov**, Galton, **21 cadeia de Markov num sistema de spins: Potts q=10, GIF de `../../figuras/fig14_anim_potts.py`**) · 22 muitos graus de liberdade (o resumo do problema) · 23 a tese de novo · 24 fim.

## Pendente de verificação
O slide 16 ("π ao acaso, antes dos computadores") traz só fatos conferidos (Buffon, Lazzarini). A ideia de que
vários artigos calcularam π por Monte Carlo nos anos 1940 **não foi confirmada**; ver as notas do slide (`N`).

## Referências dos slides históricos
Aparecem em letra pequena no rodapé dos slides 15 (Los Alamos) e 16 (π antes dos computadores), e completas nas notas (`N`).
- N. Metropolis e S. Ulam, "The Monte Carlo Method", *J. Am. Stat. Assoc.* **44**(247), 335–341 (1949).
- N. Metropolis, "The Beginning of the Monte Carlo Method", *Los Alamos Science* **15** (edição especial, 1987), 125–130.
  Conferido no texto: nome sugerido por Metropolis (tio de Ulam que ia a Monte Carlo), Fermi em Roma nos anos 1930
  (citando Segrè, sem publicar), ENIAC como primeiro teste ambicioso.
- R. Eckhardt, "Stan Ulam, John von Neumann, and the Monte Carlo Method", *Los Alamos Science* **15** (1987), p. 131 em diante.
  A pergunta da paciência (Canfield, 1946) é citada daí, nas palavras de Ulam (1983).
- G.-L. Leclerc, conde de Buffon, *Essai d'arithmétique morale* (1777, suplemento da *Histoire naturelle*, vol. 4).
- É. Barbier, "Note sur le problème de l'aiguille et le jeu du joint couvert", *J. Math. Pures Appl.* (2) **5**, 273–286 (1860).
- L. Badger, "Lazzarini's Lucky Approximation of π", *Math. Mag.* **67**(2), 83–91 (1994).

**Não confirmado:** (a) periódico, volume e páginas do artigo original de Lazzarini (1901); só o resultado, 355/113 com
3408 lançamentos, foi conferido (via Badger); (b) o ano 1948 do cartão do ENIAC (o texto de Metropolis diz só que o
teste veio depois da mudança do ENIAC, no fim de 1947); (c) a página final do artigo de Eckhardt.

## Regenerar as animações
As simulações estão em Fortran (`../fortran/`, ver o README de lá) e o Python só desenha:
`cd ../fortran && ./run_tudo.sh && cd ../animacoes && ./gera_gifs.sh && cp saida/*.gif ../slides/media/`.

## Versão PowerPoint
`../pptx/gera_pptx.py` gera `palestra_pt.pptx` e `palestra_es.pptx` (16:9, GIFs embutidos, notas do apresentador)
**lendo o `index.html`**: edite o texto aqui e rode `cd ../pptx && python3 gera_pptx.py`. Os itens `frag` ficam
todos visíveis e a animação de fundo da capa vira imagem estática. Os `.pptx` não vão para o git (`pptx/.gitignore`).
Logos (USP no topo de todos os slides; IFSC/USP e FAPESP + processo na capa e no fim): arquivos em `media/`
(`usp_branco.png`, `ifsc_usp.jpg`, `fapesp_branco.png`; cópias em `../pptx/logos/`).
