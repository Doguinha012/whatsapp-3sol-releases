<div align="center">

<img src="assets/logo.gif" alt="WhatsApp 3 Sol Logo" width="128" />

# ☀️ WhatsApp 3 Sol — Finally Tests Versão 3.6

**Aplicativo desktop multi-contas para Windows baseado no WhatsApp Web, com sessões isoladas, privacidade granular, fixação ilimitada de conversas, transcrição 100% offline, equalizador e efeitos de voz ao vivo.**

[![Version](https://img.shields.io/badge/versão-3.6.0-f97316?style=for-the-badge)](https://github.com/Doguinha012/whatsapp-3sol-releases/releases)
[![Platform](https://img.shields.io/badge/Windows-x64-0078D6?style=for-the-badge&logo=windows)](#)
[![Clematis](https://img.shields.io/badge/Clematis_Player-GitHub-6366f1?style=for-the-badge)](https://github.com/Doguinha012/Clematis-Player)

</div>

---

## 🛠️ Correção da Versão 3.6 (`v3.6.0`)

- **🖼️ Correção do Carregamento de Figurinhas nos Chats:**
  - Corrigida a rotina `triggerAvatarAndImageRecovery()` ao focar/redimensionar/restaurar a janela para **nunca resetar URLs `blob:`** nem imagens/figurinhas em carregamento dentro dos chats (`#main [data-testid="msg-container"]`).
  - Removidas flags restritivas de GPU/cache/processos (`enable-zero-copy`, `renderer-process-limit=4` e limite de cache de 50 MB -> 256 MB) que podiam descartar bitmaps WebP e caches do Service Worker, alinhando o `User-Agent` ao motor Chromium nativo com preconnect em `mmg.whatsapp.net`.

---

## 🔥 Novidades Anteriores (v3.5) (`v3.5.0`)

- **☀️ Evento Bad Sun Aprimorado (Flicker Suave, Áudios Oficiais & Falhas nos Menus):**
  - Opacidade reduzida do piscamento (`0.01`–`0.085`) para manter o clima temático de fogo sem atrapalhar a leitura das mensagens.
  - No **dia 24**, ao abrir o WhatsApp 3 Sol pela primeira vez com o evento ativo, toca automaticamente o alarme **Siren** (1 vez naquele dia, até finalizar) junto com **Meta Paranoia** em loop contínuo enquanto o tema estiver ativo.
  - **Textos de Menu com Falhas Proporcionais:** ~12 palavras aleatórias nos menus da interface piscam rapidamente trocando letras proporcionalmente (`olá` → 1 letra, palavras longas → 3–5 letras) mantendo a legibilidade, com esticamento, ampliação, preto e inversão de cor, restaurando tudo ao desativar o efeito.
- **🔔 Notificações Clicáveis Direto na Conversa:**
  - Retenção segura das instâncias de `Notification` no Windows + parsing inteligente de títulos de grupos, contatos, contadores `(N)` e `tag` JID, restaurando/focando a janela, trocando para a conta correta e abrindo exatamente a conversa da notificação clicada.
- **🎞️ Exportação de GIF em Alta Qualidade:**
  - Nova quantização adaptativa de paleta por **Median-Cut (255 cores por arquivo)** com dithering ordenado **Bayer 4×4** e resolução elevada para até **480px**, eliminando granulados e faixas de cor ao baixar GIFs e figurinhas animadas.

---

## 🔥 Destaques Anteriores (v3.4)

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

> Desenvolvido por **Douglas da Cunha Zanetti (Doguinha)** — Versão 3.6 (`3.6.0`).
