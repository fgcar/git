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

### Setup

1. Clone o repositório:
   ```bash
   git clone https://github.com/seuusuario/seurepo.git
   cd seurepo
