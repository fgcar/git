<p align="center">
<br>
<a href="https://github.com/seuusuario/seurepo"><img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg"></a>
<a href="#linux"><img src="https://img.shields.io/badge/os-linux-brightgreen"></a>
<a href="#macos"><img src="https://img.shields.io/badge/os-mac-brightgreen"></a>
<a href="#windows"><img src="https://img.shields.io/badge/os-windows-yellowgreen"></a>
<br>
<h1 align="center">
  <b>Telegram Multimodal Bot</b>
</h1>
<h3 align="center">
Bot Telegram em Python que entende fotos e áudios (com detecção de objetos e transcrição)
</h3>
<br>
</p>

---

## Table of Contents

- [About](#about)  
- [Features](#features)  
- [Architecture](#architecture)  
- [Installation](#installation)  
  - [Requirements](#requirements)  
  - [Setup](#setup)  
- [Usage](#usage)  
- [Supported Platforms](#supported-platforms)  
- [How it Works](#how-it-works)  
- [Contributing](#contributing)  
- [License](#license)  

---

## About

Este projeto é um bot Telegram desenvolvido em Python que suporta dois tipos principais de mensagem:  
- **Fotos:** recebe uma imagem, detecta objetos usando o modelo YOLOv8n e responde com a imagem anotada e a lista dos objetos detectados.  
- **Áudios de voz:** recebe áudio no formato OGG, converte para WAV, realiza transcrição via Google Speech Recognition API e responde com o texto transcrito.  

---

## Features

- Recepção e processamento de imagens com detecção de múltiplos objetos  
- Transcrição automática de mensagens de voz em português brasileiro  
- Comandos básicos `/start` e `/test` para interagir com o bot  
- Integração polimórfica das funcionalidades de áudio e imagem em um único bot  
- Arquitetura modular e orientada a objetos para fácil extensão  

---

## Architecture

| Módulo           | Descrição                                                       |
|------------------|-----------------------------------------------------------------|
| `bot_telegram.py`| Classe base que inicializa o bot, carrega token e handlers básicos |
| `bot_imagem.py`  | Implementa detecção de objetos em imagens e resposta ao usuário |
| `bot_audio.py`   | Implementa transcrição de áudio e resposta ao usuário           |
| `bot_combo.py`   | Junta funcionalidades de áudio e imagem                         |
| `main.py`        | Script para instanciar o bot e iniciar o polling                |

---

## Installation

### Requirements

- Python 3.8+  
- Bibliotecas Python:
  - `pyTelegramBotAPI`  
  - `ultralytics`  
  - `librosa`  
  - `soundfile`  
  - `SpeechRecognition`  
  - `python-dotenv`


  Todas as bibliotecas Python necessárias estão listadas no arquivo `requirements.txt`. Para instalar as dependências, execute o comando abaixo no terminal:

```bash
pip install -r requirements.txt
```

Além disso, certifique-se de ter o ffmpeg instalado no seu sistema, pois ele é necessário para a manipulação de áudio.
Instalando o ffmpeg

  No Ubuntu/Debian:
```bash
sudo apt update
sudo apt install ffmpeg
```
  No macOS (com Homebrew):
```bash
brew install ffmpeg
```
  No Windows:

Baixe o instalador oficial em https://ffmpeg.org/download.html e siga as instruções para adicionar o ffmpeg ao PATH do sistema.

### Setup

1. Clone o repositório:
   ```bash
   git clone --branch GR2 https://github.com/IagoBiundini/ene140_2025.git
   cd ene140_2025

### Ambiente virtual (opcional)
  ```bash
  python3 -m venv venv
  source venv/bin/activate  # Linux/Mac
  venv\Scripts\activate     # Windows
  ```
## Usage

Após instalar as dependências, você pode iniciar o bot executando o arquivo principal:

```bash
python main.py
```

Certifique-se de ter criado um arquivo `.env` na raiz do projeto com a variável BOT_TOKEN configurada com o token do seu bot do Telegram:
```bash
BOT_TOKEN=seu_token_aqui
```
# Como obter seu token do Telegram

1. No Telegram, converse com o **BotFather**.
2. Use o comando `/newbot` para criar um novo bot.
3. Copie o token fornecido pelo BotFather e cole no arquivo `.env`.

Interagindo com o Bot

  - `Envie uma foto para que o bot detecte e identifique objetos presentes na imagem utilizando o modelo YOLOv8.`
  - `Envie um áudio de voz para que o bot transcreva o conteúdo do áudio para texto.`

O bot responderá com a transcrição do áudio ou com a imagem contendo as detecções e a lista dos objetos encontrados.

Se quiser parar o bot, use Ctrl+C no terminal.


## Supported Platforms

- ![Linux](https://img.shields.io/badge/os-linux-brightgreen.svg) Linux  
- ![MacOS](https://img.shields.io/badge/os-mac-brightgreen.svg) MacOS  
- ![Windows](https://img.shields.io/badge/os-windows-yellowgreen.svg) Windows


### How it Works

#### Image Processing

1. Recebe foto do usuário  
2. Salva localmente em `in/`  
3. Executa detecção com YOLOv8n  
4. Salva imagem anotada em `out/`  
5. Envia imagem anotada e lista de objetos detectados  

#### Audio Processing

1. Recebe mensagem de voz (OGG)  
2. Salva e converte para WAV  
3. Transcreve áudio usando Google Speech Recognition API (via SpeechRecognition)  
4. Responde com texto transcrito  


### Contributing

[![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-brightgreen.svg)](https://github.com/seu-usuario/seu-repositorio/issues)

Pull requests são sempre bem-vindos! Para contribuir, você pode abrir uma issue para discutir melhorias ou bugs, ou então fazer um fork do repositório e enviar um pull request.

### License

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

Este projeto está licenciado sob a [MIT License](https://opensource.org/licenses/MIT).



