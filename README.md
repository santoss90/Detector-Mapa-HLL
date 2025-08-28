🗺️ HLL Map Detector
Versão 1.0.0
Feito por: Vinícius dos Santos (Clã CAIVERAS)

Um utilitário simples para automatizar a troca de cenas no OBS Studio ao abrir e fechar o mapa do jogo Hell Let Loose.

Este programa foi desenvolvido para streamers e criadores de conteúdo que desejam ocultar a visão do mapa do jogo de suas transmissões. Ele detecta automaticamente quando o jogador abre o mapa e alterna a cena no OBS, retornando para a cena principal quando o mapa é fechado.

🛠️ Requisitos

Para usar este programa, você precisa ter:

OBS Studio (v28.0 ou superior) com o OBS-WebSocket ativado. Você pode habilitar esta opção em Configurações > WebSocket no OBS.

O jogo Hell Let Loose rodando em modo janela ou tela cheia sem bordas.

Windows (o programa foi desenvolvido para rodar via .exe).

💾 Download

Baixe a versão mais recente do programa aqui:

[🔗 Download do HLL Map Detector (.exe)](https://drive.google.com/file/d/1WBzVWxwdqfG_M9dqfi5zF8LjwPUR065O/view?usp=sharing)

🚀 Como Usar
1. Configuração do OBS

No OBS Studio, crie duas cenas:

Cena principal para o jogo (ex: "Game").

Cena secundária para quando o mapa estiver aberto (ex: "Map"). Esta cena pode ser uma tela preta, uma imagem de mapa ou qualquer outro conteúdo desejado.

2. Configuração do settings.json

Na mesma pasta do executável (.exe), crie um arquivo chamado settings.json com o seguinte conteúdo:

```json
{
    "obs_host": "localhost",
    "obs_port": 4455,
    "obs_password": "",
    "game_scene_name": "Game",
    "map_scene_name": "Map"
}
```

obs_password: Senha configurada no OBS WebSocket (se houver).

game_scene_name: Nome exato da sua cena principal no OBS.

map_scene_name: Nome exato da sua cena secundária que será exibida quando o mapa estiver aberto.

⚠️ Atenção: os nomes das cenas devem ser exatamente iguais aos nomes usados no OBS, incluindo maiúsculas e espaços.

3. Executando o Programa

Dê duplo clique no arquivo hll_detector.exe.

Um console será aberto mostrando os logs do programa.

Para encerrar, basta fechar o console.

💡 Se quiser ver uma janela de debug mostrando o que está sendo detectado em tempo real, execute o programa via Prompt de Comando ou PowerShell usando:

hll_detector.exe --show-debug-window

⚙️ Como Funciona

O programa:

Captura a tela do Windows.

Localiza a janela do Hell Let Loose.

Analisa uma região central da tela usando processamento de imagem (OpenCV) para detectar elementos do mapa do jogo.

Quando o mapa é detectado, envia um comando via OBS WebSocket para alternar para a cena do mapa.

Quando o mapa não é mais detectado, retorna para a cena principal após um curto período.

📝 Observações

O programa foi desenvolvido em Python e compilado para Windows como .exe.

Arquivos grandes como modelos YOLO estão inclusos e a detecção é otimizada para baixa latência.

Ideal para streamers que querem manter o mapa oculto sem precisar alternar cenas manualmente.