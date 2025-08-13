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


Isso vai exibir o comando formatado como código, e o texto que vier depois no seu README continuará normal, sem ser interpretado como código ou comentário.

---

Exemplo no Markdown:

  ```bash
  pip install -r requirements.txt
  ```

### Setup

1. Clone o repositório:
   ```bash
   git clone --branch GR2 https://github.com/IagoBiundini/ene140_2025.git
   cd ene140_2025


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



