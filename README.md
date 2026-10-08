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

### 1. 🔤 Modo de Sorteio: Números ou Letras (Alfabeto)
- **1 2 3 Números**: sorteio numérico sequencial (1 a 15).
- **A B C Letras**: sorteio alfabético (**A**, **B**, **C**, **D**... até 15 letras). As faces 3D do pião e o histórico na tela exibem as letras correspondentes com sincronia total.

### 2. 📐 Geometria 3D Dinâmica (2 a 15 Faces)
- O pião é um polígono cilíndrico tridimensional gerado via CSS 3D (`preserve-3d`, `translateZ` e `rotateY`).
- A largura de cada face e o raio de rotação são calculados dinamicamente através de trigonometria precisa ($w = 2R \sin(\frac{\pi}{n})$ e $r = R \cos(\frac{\pi}{n})$), mantendo as proporções estéticas perfeitas em qualquer quantidade de faces.

### 3. ⌨️ Giro Interativo com a Barra de Espaço
- **Giro Contínuo**: segure a tecla **[Espaço]** (ou mantenha pressionado o botão do mouse sobre "Girar Pião") para o pião acelerar e rodar em velocidade máxima contínua.
- **Desaceleração Realista**: ao soltar a tecla, o pião entra em uma curva suave de inércia (`cubic-bezier`), parando exatamente na face sorteada perfeitamente centralizada e nítida.

### 4. ⚡ Sorteios em Sequência (1 a 50)
- Permite rodar múltiplos sorteios seguidos de forma automática.
- Ideal para definir a ordem completa de apresentações de uma sala ou grupo de uma só vez.

### 5. 🔁 Controle de Repetição (Sim / Não)
- **Sem Repetição**: garante que cada integrante, número ou letra seja sorteado no máximo uma única vez durante a sequência.
- **Com Repetição**: sorteios totalmente aleatórios e independentes a cada rodada.

### 6. 🚀 Velocidade de Giro (1x e 2x)
- Alternador rápido entre o ritmo clássico com suspense tradicional (**1x**) ou modo acelerado para eventos dinâmicos (**2x**).

### 7. 🏆 Placar / HUD de Sorteados na Tela
- Exibe o histórico de todos os sorteados em badges de alto contraste estilo TV.
- **Posicionamento flexível**: clique no placar (ou no botão do cabeçalho) para alternar a exibição entre a **base inferior (horizontal)** e a **lateral direita (vertical)**.
- Botão integrado para limpar o histórico a qualquer momento.

### 8. 🎵 Trilha Sonora Clássica e Áudio Inteligente
- Reproduz a autêntica trilha musical do Pião da Casa Própria.
- **Gerenciamento inteligente**: a música toca continuamente durante sequências sem recomeçar abruptamente e encerra automaticamente ao fim do sorteio.
- Botão liga/desliga integrado no painel.

### 9. 🎛️ Painel Retrátil com Ícone Flutuante (FAB)
- O menu de opções pode ser recolhido a qualquer momento para liberar 100% da visualização para projeções e telões.
- Quando recolhido, exibe um elegante **botão circular flutuante** em vermelho rubi com borda dourada e ícone **⚙️ ampliado**.

### 10. 🔄 Botão Reset de Configurações
- Restaura com um único clique todas as opções para o estado padrão (Modo Números, 6 faces, 1 sorteio, sem repetição, velocidade 1x).

---

## 🚀 Como Executar

Por ser uma aplicação 100% estática, nenhuma instalação de dependências ou compilação é necessária.

### Opção 1: Diretamente no Navegador
Basta abrir o arquivo `index.html`:
```bash
open index.html
# ou no Linux: xdg-open index.html
```

### Opção 2: Servidor Local (Recomendado para Áudio)
Para evitar eventuais políticas de autoplay restritivas de navegadores para arquivos locais (`file://`), você pode iniciar um servidor HTTP simples:

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
| **Girar Pião** | Clique no botão ou pressione **[Espaço]** |
| **Giro Contínuo com Suspense** | **Segure [Espaço]** (ou segure o clique no botão) e solte para sortear |
| **Interromper Sequência** | Clique em **"Parar Sequência"** ou aperte **[Espaço]** |
| **Mudar Posição do Placar** | Clique em qualquer lugar sobre o placar ou no botão **Lateral / Base** |
| **Recolher / Abrir Painel** | Clique no botão **✕** para fechar ou no ícone flutuante **⚙️** para reabrir |
| **Ligar / Desligar Som** | Clique no botão **🔊 Som** no cabeçalho do painel |

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
