# 🌀 Pião da Casa Própria em CSS 3D

> **Sorteador interativo para apresentações em grupo, dinâmicas de equipe e eventos**, inspirado no lendário quadro de Silvio Santos no SBT.

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)](https://en.wikipedia.org/wiki/HTML5)
[![CSS3 3D](https://img.shields.io/badge/CSS3-3D_Transforms-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transforms/Using_CSS_transforms)
[![Vanilla JS](https://img.shields.io/badge/JavaScript-Vanilla-F7DF1E?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-success?style=flat-square)](#)

---

## 📖 Visão Geral

O **Pião da Casa Própria** recria a experiência clássica do programa de TV utilizando apenas tecnologias web nativas (**HTML5, CSS 3D Transforms e JavaScript puro**, sem frameworks ou bibliotecas pesadas).

Projetado especialmente para:
- 👥 **Sorteio de integrantes e ordem de apresentação** em trabalhos escolares e acadêmicos;
- 🎤 **Dinâmicas de eventos, meetups e confraternizações**;
- 🎁 **Sorteios de brindes, números e equipes**.

---

## ✨ Funcionalidades Principais

### 1. 🌀 Gire o pião com o dedo (ou o mouse)
- **Dois toques** (ou duplo clique) no pião: gira e sorteia.
- **Arrastar** na horizontal: o pião acompanha o dedo; ao soltar, a velocidade do gesto define a força e o tempo do giro (~1,5 a 6 s). Gestos fracos só realinham, sem sortear.
- Desaceleração realista até parar exatamente na face sorteada.

### 2. 🎛️ Controles em ícones
Barra de ícones no topo da tela, sem painel de configurações:

| Ícone | Função |
| :--- | :--- |
| **− 6 +** | Quantidade de faces (2 a 15) |
| **123 / ABC** | Faces com números ou letras |
| **Não repetir** | Quem já saiu não sai de novo (faces sorteadas ficam apagadas); com todos sorteados, dois toques recomeçam |
| **Todos** | Liga o modo sequência: sorteia todas as faces, uma de cada vez, sem repetir. Tocar nele durante a sequência para |
| **Som** | Liga/desliga a trilha |
| **Tela cheia** | Só no computador |

Nada é salvo: ao recarregar a página tudo volta ao estado inicial (6 faces, números, um por vez, som ligado).

### 3. 📐 Geometria 3D Dinâmica (2 a 15 Faces)
- O pião é um polígono cilíndrico tridimensional gerado via CSS 3D (`preserve-3d`, `translateZ` e `rotateY`).
- A largura de cada face e o raio de rotação são calculados dinamicamente através de trigonometria precisa ($w = 2R \sin(\frac{\pi}{n})$ e $r = R \cos(\frac{\pi}{n})$), mantendo as proporções estéticas perfeitas em qualquer quantidade de faces.

### 4. 🏆 Sorteados na tela
- Faixa discreta abaixo do pião com os números na ordem em que saíram (o último em destaque).
- Copiar a ordem e limpar (com opção de desfazer).

### 5. 🎵 Trilha sonora com Web Audio API
- A trilha é decodificada uma vez e tocada via Web Audio API, liberada no primeiro toque: toca de forma confiável a cada giro, inclusive no iPhone (sessão "playback", não é silenciada pela chave lateral).

---

## 🚀 Como Executar

Por ser uma aplicação 100% estática, nenhuma instalação de dependências ou compilação é necessária. A trilha é carregada via `fetch`, então **é preciso servir os arquivos por HTTP** (abrindo o `index.html` direto do disco o pião funciona, mas sem música):

```bash
# Com Python 3
python3 -m http.server 8080

# Ou com Node.js
npx serve .
```
Em seguida, acesse no navegador: **`http://localhost:8080`**.

---

## ⌨️ Atalhos e Controles

| Ação | Controle |
| :--- | :--- |
| **Girar** | Dois toques / duplo clique no pião, **[Enter]** ou **[Espaço]** (segure para mais força) |
| **Girar com força do gesto** | Arraste o pião na horizontal e solte |
| **Parar a sequência** | Dois toques no pião, ícone **Todos** ou **[Esc]** |
| **Ligar / Desligar Som** | Ícone de som ou **[S]** |
| **Tela cheia** | Ícone de tela cheia ou **[F]** (computador) |

---

## 🛠️ Estrutura de Arquivos

```
piao/
├── index.html                           # Estrutura HTML5, Estilos CSS 3D e Lógica JS
├── README.md                            # Documentação completa
├── piao-da-casa-propria-soundtrack.mp3   # Áudio clássico (MP3)
├── piao-da-casa-propria-soundtrack.m4a   # Áudio (M4A)
└── piao-da-casa-propria-soundtrack.ogg   # Áudio (OGG)
```

- **Sem dependências externas**: sem React, sem Vue, sem jQuery, sem Tailwind.
- **CSS 3D Hardware Accelerated**: cálculos de matrizes 3D e rotações com aceleração por GPU.
- **Sintaxe moderna e compatível**: suporte nativo a Chrome, Safari, Firefox, Edge e navegadores mobile.

---

## 📜 Créditos e Referências

- Base conceitual original desenvolvida por [Loop Infinito](http://loopinfinito.com.br/2012/05/13/piao-da-casa-propria-em-css-3d/) (2012).
- Inspirado no clássico quadro de auditório do **Baú da Felicidade / Sistema Brasileiro de Televisão (SBT)**, apresentado por Silvio Santos.
