🗺️ HLL Map Detector
Versão 1.0.0

Feito por: Vinícius dos Santos (Clã CAIVERAS)

## 📖 **Sobre o Projeto**

Um utilitário simples para automatizar a troca de cenas no OBS Studio ao abrir e fechar o mapa do jogo Hell Let Loose.

Este programa foi desenvolvido para streamers e criadores de conteúdo que desejam ocultar o mapa do jogo em transmissões. Ele detecta automaticamente quando o jogador abre o mapa e alterna a cena no OBS, retornando para a cena principal quando o mapa é fechado.

## 🛠️ **Requisitos**

Para usar este programa, você precisa ter:

OBS Studio (v28.0 ou superior) com o OBS-WebSocket ativado.

Habilite em Configurações > WebSocket no OBS.

O jogo Hell Let Loose rodando em modo janela ou tela cheia sem bordas.

Windows (o programa foi compilado para rodar em .exe).

## 💾 **Download**

Baixe a versão mais recente do programa aqui:

[👉 Download do HLL Map Detector (.exe)](https://drive.google.com/file/d/1WBzVWxwdqfG_M9dqfi5zF8LjwPUR065O/view?usp=sharing)

## 🚀 **Como Usar**
1. **Configuração do OBS**

No OBS Studio, crie duas cenas:

Cena principal para o jogo (ex: "Game").

Cena secundária para quando o mapa estiver aberto (ex: "Map").

A cena secundária pode ser uma tela preta, uma imagem ou qualquer outro conteúdo desejado.

2. **Configuração do settings.json**

Na mesma pasta do executável (.exe), crie um arquivo chamado settings.json com o seguinte conteúdo:

``` json

{
    "obs_host": "localhost",
    "obs_port": 4455,
    "obs_password": "",
    "game_scene_name": "Game",
    "map_scene_name": "Map"
}

```

obs_password → Senha configurada no OBS WebSocket (se houver).

game_scene_name → Nome exato da cena principal no OBS.

map_scene_name → Nome exato da cena secundária que será exibida quando o mapa estiver aberto.

⚠️ Atenção: os nomes das cenas devem ser exatamente iguais aos usados no OBS (incluindo maiúsculas e espaços).

3. **Primeira Execução** ⚡

Na primeira vez que o programa for aberto, ele pode demorar um pouco para preparar as configurações iniciais.
Durante esse processo, será exibida a mensagem:

``` cmd
creating new ultralytics settings...
```

Se esse carregamento demorar muito, basta fechar e abrir o programa novamente.
Nas próximas execuções, ele iniciará normalmente sem essa espera. ✅

4. **Executando o Programa**

Dê duplo clique no arquivo hll_detector.exe.

Um console (CMD) será aberto mostrando os logs do programa.

Para encerrar, basta fechar o console.

## ⚙️ Como Funciona

O programa:

Captura a tela do Windows.

Localiza a janela do Hell Let Loose.

Analisa a região central usando OpenCV para detectar o mapa.

Quando o mapa é detectado → alterna para a cena do mapa.

Quando o mapa não é detectado → retorna para a cena principal após um curto período.

## 📝 **Observações**

Desenvolvido em Python, compilado para Windows (.exe).

Otimizados para baixa latência.

Pensado para streamers que desejam ocultar o mapa sem precisar alternar manualmente no OBS.

## ☕ **Apoie este projeto**

Se este projeto te ajudou, que tal me apoiar com um cafézinho via PIX?  

**Chave PIX:** `f9b6943a-5da5-46cb-a3f2-57f8858fdf60`  

<img src="https://github.com/santoss90/Detector-Mapa-HLL/blob/main/QR_Pix.png" alt="PIX QR Code" width="200">


