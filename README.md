<div align="center">

<img src="assets/logo.gif" alt="WhatsApp 3 Sol Logo" width="128" />

# ☀️ WhatsApp 3 Sol — Finally Tests Versão 3.4

**Aplicativo desktop multi-contas para Windows baseado no WhatsApp Web, com sessões isoladas, privacidade granular, fixação ilimitada de conversas, transcrição 100% offline, equalizador e efeitos de voz ao vivo.**

[![Version](https://img.shields.io/badge/versão-3.4.0-f97316?style=for-the-badge)](https://github.com/Doguinha012/whatsapp-3sol-releases/releases)
[![Platform](https://img.shields.io/badge/Windows-x64-0078D6?style=for-the-badge&logo=windows)](#)
[![Clematis](https://img.shields.io/badge/Clematis_Player-GitHub-6366f1?style=for-the-badge)](https://github.com/Doguinha012/Clematis-Player)

</div>

---

## 🔥 Correções Urgentes & Novidades da Versão 3.4 (`v3.4.0`)

- **☀️ Correção Completa do Bad Sun (Layout & Flicker de Fogo):**
  - Movido o filtro de cor para `#app` e ancorado o quadrado de censura como camada `position: fixed` diretamente em `document.body` apenas quando uma conversa está aberta (`#main`). Isso elimina totalmente os deslocamentos para cima ao reiniciar, atualizar abas ou abrir Status/Comunidades, e o quadrado nunca cresce nem sai da posição.
  - Efeito de luz/sombra de fogo acelerado (`~1.35s` orgânico) cobrindo a **tela inteira** de maneira uniforme em vez de apenas as bordas.
- **🎞️ Exportação Real de GIFs & Figurinhas Animadas em Vídeo:**
  - Figurinhas animadas (`.webp` animado) agora têm todos os quadros decodificados via `ImageDecoder` ao exportar em **MP4**, **WebM** ou **GIF**, eliminando arquivos congelados em 1 frame.
  - GIFs do WhatsApp (streams `<video>`) agora usam seek quadro-a-quadro sem taint CORS e compressão em base64 compacto para salvar corretamente em **`.gif`** além de `.mp4` e `.webm`.
- **🎵 Spotify UTF-8 (`ç`, `ã`, `ó`) & Link Direto da Faixa:**
  - Leitura da janela do Spotify em UTF-8 puro (`Get-Process MainWindowTitle`), corrigindo acentos corrompidos (`Modão`, `Coração`, etc.) e permitindo resolver links diretos `https://open.spotify.com/track/...` corretamente.
- **🎤 Efeitos de Microfone ao Vivo Aprimorados:**
  - Novo processador OLA com pré-amplificador e compressor para **Voz de Esquilo**, **Voz de Monstro** e **Onda Lenta**, filtro **Wah-Wah** ressonante, **Rádio/Telefone** e **Megafone** nítidos, e **Áudio 8D** com phaser giratório + reverberação espacial audível mesmo em gravações PTT do WhatsApp.

---

## 🛠️ Desenvolvimento & Build (Windows)

```bash
npm install
npm run lint
npm test
npm run pack:all
```

> Desenvolvido por **Douglas da Cunha Zanetti (Doguinha)** — Versão 3.4 (`3.4.0`).
