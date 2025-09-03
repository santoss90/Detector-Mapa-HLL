# 🗺️ HLL Map Detector
### Versão 2.0.0

Feito por: **Vinícius dos Santos**

---

## 📖 Sobre o Projeto

Um utilitário simples e leve para automatizar a troca de cenas no **OBS Studio** ao abrir e fechar o mapa do jogo **Hell Let Loose**.

Este programa foi desenvolvido para streamers e criadores de conteúdo que desejam ocultar o mapa do jogo em suas transmissões. Ele detecta automaticamente quando o jogador abre o mapa e alterna a cena no OBS, retornando para a cena principal quando o mapa é fechado.

## 🛠️ Requisitos

Para usar este programa, você precisa ter:

* **OBS Studio** (v28.0 ou superior) com o **OBS-WebSocket** ativado.
    * Habilite em **Configurações > WebSocket** no OBS.
* O jogo **Hell Let Loose** rodando em modo **janela** ou **tela cheia sem bordas**.
* **Windows** (o programa foi compilado para rodar em .exe).

## 💾 Download

Baixe a versão mais recente do programa aqui. O arquivo é um executável portátil e não requer instalação.

👉 **[Baixar Detector de Mapa HLL (.exe)]([https://drive.google.com/sua-url-aqui](https://drive.google.com/file/d/1h37hChcCuOv4wTvJX63FqVrogZceieVX/view?usp=sharing))**

* **Atenção:** Por ser um arquivo executável, seu navegador ou antivírus pode emitir um aviso. Você pode prosseguir com o download e execução com segurança.

## 🚀 Como Usar

### Configuração do OBS

No OBS Studio, crie duas cenas:

**1.  Cena principal para o jogo** (ex: "Cena Jogando")**

**2.  Cena secundária** para quando o mapa estiver aberto (ex: "Cena Remove Mapa")**

A cena secundária pode ser uma tela preta, uma imagem ou qualquer outro conteúdo desejado.

**3. Configuração do `settings.json`**

Na mesma pasta onde você baixou o executável (`.exe`), crie um arquivo chamado **`settings.json`** com o seguinte conteúdo:

```json
{
    "obs_host": "localhost",
    "obs_port": 4455,
    "obs_password": "",
    "game_scene_name": "Cena Jogando",
    "map_scene_name": "Cena Remove Mapa",
    "detection_threshold": 3,
    "sleep_time": 0.10
}
```

obs_host: O endereço do seu OBS WebSocket. Geralmente é localhost.

obs_port: A porta do seu OBS WebSocket. O padrão é 4455.

obs_password: A senha que você configurou no OBS WebSocket. Se não houver, deixe "".

game_scene_name: Nome exato da cena principal no OBS.

map_scene_name: Nome exato da cena que será exibida quando o mapa estiver aberto.

detection_threshold: O número de frames que o programa precisa detectar o mapa para confirmar que ele está aberto. Padrão: 3.

sleep_time: O intervalo de tempo (em segundos) entre cada verificação de tela. Padrão: 0.10.

⚠️ Atenção: Os nomes das cenas (game_scene_name e map_scene_name) devem ser exatamente iguais aos que você usou no OBS, incluindo maiúsculas e espaços.

**4. Executando o Programa**

Dê um duplo clique no arquivo HLL_Map_Detector.exe.

Uma janela do programa será aberta, mostrando os logs de atividade.

Para encerrar o programa, basta fechar a janela principal ou o console.

## ⚙️ Como Funciona
O programa utiliza a biblioteca de visão computacional para identificar a imagem do mapa do Hell Let Loose na sua tela.

Ele captura a tela da sua janela do jogo.

Analisa a região central para verificar se o mapa está visível.

Quando o mapa é detectado por um número de frames consecutivos (definido em detection_threshold) → a cena do OBS é alternada para a cena do mapa.

Quando o mapa desaparece → o programa retorna para a cena principal após um curto período, garantindo que a transição ocorra de forma suave e com baixa latência.

## 📝 Observações
Desenvolvido em Python e compilado para Windows (.exe).

Otimizado para baixa latência.

Perfeito para streamers que desejam uma solução automática e confiável.

## ☕ Apoie este projeto
Se este projeto te ajudou a melhorar suas transmissões, que tal me apoiar com um cafézinho via PIX?

Chave PIX: f9b6943a-5da5-46cb-a3f2-57f8858fdf60

<img src="https://github.com/santoss90/Detector-Mapa-HLL/blob/main/QR_Pix.png" alt="PIX QR Code" width="200">


