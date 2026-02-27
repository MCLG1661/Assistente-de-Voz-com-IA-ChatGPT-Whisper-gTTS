# 🎙️ Assistente de Voz com IA - ChatGPT + Whisper + gTTS

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1rHGq5N-sbEGtZsNUiQFT8q60BhRbj99b?usp=sharing)
![Python](https://img.shields.io/badge/python-3.8+-blue.svg)
![OpenAI](https://img.shields.io/badge/OpenAI-Whisper%20%7C%20GPT--3.5-green)
![License](https://img.shields.io/badge/license-MIT-orange)

## 📋 Sobre o Projeto

Melhorar um assistente de voz interativo que combina o poder do reconhecimento de fala da OpenAI (Whisper) com a inteligência do ChatGPT e síntese de voz do Google (gTTS). O sistema permite uma conversa natural totalmente por voz, com uma interface amigável e diversas funcionalidades avançadas.

### ✨ Melhorias Implementadas

- Detecção de silêncio (VAD) - Gravação para automaticamente
- Interface gráfica - Botões e campos de texto intuitivos
- Cache inteligente - Respostas repetidas são instantâneas
- Histórico de conversa - Mantém contexto das interações
- Processamento em threads - Interface não trava
- Normalização de áudio - Volume consistente nas respostas
- Múltiplos modelos Whisper - Escolha entre precisão e velocidade
- Tratamento de erros - Mensagens claras e recuperação

### Funcionalidades Principais

- 🎤 **Gravação inteligente** com detecção automática de silêncio (VAD)
- 🔤 **Transcrição precisa** usando Whisper da OpenAI
- 🤖 **Respostas contextuais** com ChatGPT (modelo gpt-3.5-turbo)
- 🔊 **Síntese de voz natural** com gTTS e normalização de áudio
- 💾 **Sistema de cache** para respostas frequentes
- 📜 **Histórico de conversa** mantendo contexto
- 🎛️ **Interface gráfica** com ipywidgets
- ⚡ **Processamento paralelo** sem travar a interface

### Pré-requisitos

- Uma conta no [Google Colab](https://colab.research.google.com/)
- Chave de API da [OpenAI](https://platform.openai.com/api-keys)
- Microfone funcionando no seu computador

### 📖 Como Usar

Interface Principal :

1. GRAVAÇÃO

- Clique no botão "Gravar"
- Fale claramente (máximo 10 segundos)
- A gravação para automaticamente ao detectar silêncio

2. TRANSCRIÇÃO

- O sistema converte áudio em texto usando Whisper
- O texto aparece automaticamente no campo "Pergunta"
- Você pode editar o texto se necessário

3. PROCESSAMENTO

- Clique em "Processar" para enviar ao ChatGPT
- O sistema verifica primeiro no cache
- Se não encontrar, consulta a API da OpenAI

4. RESPOSTA

- O texto da resposta aparece no campo "Resposta"
- O áudio é gerado automaticamente com gTTS
- A resposta é reproduzida em voz alta

### 🏗️ARQUITETURA DO SISTEMA

Componentes Principais :

Entrada

- Microfone do navegador (JavaScript)
- Detecção de silêncio (WebRTC VAD)
- Buffer de áudio em memória

Processamento

- Whisper (transcrição áudio → texto)
- Cache local (armazenamento JSON)
- Histórico de conversa (contexto)

Inteligência

- API ChatGPT (geração de respostas)
- Gerenciamento de tokens
- Controle de contexto

Saída

- gTTS (texto → áudio)
- Normalização de volume
- Reprodução automática

### PARÂMETROS CONFIGURÁVEIS

No início do notebook você encontra a seção CONFIG :

- Modelo de Transcrição : Você pode escolher entre tiny, base, small, medium ou large. O modelo base é o recomendado para uso diário por oferecer o melhor equilíbrio entre velocidade e precisão.
- Idioma : O sistema está configurado para português (pt), mas você pode alterar para outros idiomas como inglês (en), espanhol (es) ou francês (fr).
- Voz e Áudio : A síntese de voz usa o gTTS no idioma português do Brasil (pt-br). A velocidade pode ser normal ou lenta, e o volume é ajustado automaticamente para um nível confortável.
- Cache de Respostas : O cache armazena respostas já geradas para evitar consultas repetidas à API. Quando ativado, reduz custos e acelera o processamento.
- Detecção de Silêncio : O sistema para de gravar automaticamente após 1,5 segundos de silêncio. O tempo máximo de gravação é de 10 segundos. A sensibilidade do microfone pode ser ajustada conforme o ambiente.
- Histórico de Conversa : O sistema mantém as últimas 10 mensagens para manter o contexto da conversa. O histórico pode ser exportado para um arquivo JSON.

### Adaptando para Outros Idiomas

- Mude "idioma" para o código do idioma desejado
- Ajuste "voz_gtts" conforme necessário
- O sistema detectará automaticamente o idioma falado 

### 📈 Performance Detalhada

Opções de Modelo Whisper :

- Ttiny : Processa áudio em 5 segundos, acerta 70% das palavras, usa 1GB de RAM é indicado para testes rápidos.
- Base : Processa áudio em 8 segundos, acerta 80% das palavras, usa 1.5GB de RAM é indicado para uso diário.
- Small : Processa áudio em 12 segundos, acerta 85% das palavras, usa 2GB de RAM é indicado para ambientes com ruído.
- Medium : Processa áudio em 20 segundos, acerta 90% das palavras, usa 5GB de RAM é iIndicado para uso profissional.
- Large : Processa áudio em 30 segundos, acerta 95% das palavras, usa 10GB de RAM é iIndicado para pesquisa acadêmica.

### Para Melhorar Ainda Mais

- Adicionar suporte a mais serviços de TTS (Amazon Polly, Microsoft Azure)
- Implementar reconhecimento de emoções na voz
- Criar versão standalone (fora do Colab)
- Adicionar tradução simultânea
- Melhorar a detecção de idioma automática

### 🙏 Agradecimentos

- OpenAI pelo Whisper e ChatGPT
- Google pelo gTTS
- Comunidade do Google Colab pela infraestrutura
- Prof. Diego rena Bruno - Bootcamp GenAI DIO/Bradesco - Módulo : OS PILARES FORMAIS DA IA

### Autor

- Marcus Guedes
- Linkedin : https://www.linkedin.com/in/marcusguedes/
- GitHub :  https://github.com/MCLG1661
