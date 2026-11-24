<div align="center">

<img src="assets/logo.gif" alt="WhatsApp 3 Sol Logo" width="128" />

# ☀️ WhatsApp 3 Sol — Finally Tests Versão 3.7.2

**Aplicativo desktop multi-contas para Windows baseado no WhatsApp Web, com sessões isoladas, privacidade granular, fixação ilimitada de conversas, transcrição 100% offline, equalizador e efeitos de voz ao vivo.**

[![Version](https://img.shields.io/badge/versão-3.7.2-f97316?style=for-the-badge)](https://github.com/Doguinha012/whatsapp-3sol-releases/releases)
[![Platform](https://img.shields.io/badge/Windows-x64-0078D6?style=for-the-badge&logo=windows)](#)
[![Clematis](https://img.shields.io/badge/Clematis_Player-GitHub-6366f1?style=for-the-badge)](https://github.com/Doguinha012/Clematis-Player)

</div>

---

## ☀️ Atualização Especial Bad Sun & Imersão *Voices of the Void* (`v3.7.2`)

- **🌌 Paralaxe em Camadas no Chat + Censura Travada com o Sol:** Fundo, silhuetas e Sol agora reagem com profundidades diferentes ao movimento do mouse, mantendo a censura pixel a pixel alinhada ao Sol e acima de todas as camadas (`z-index: 999999`).
- **🔤 Glitch de Textos dentro do WhatsApp Web:** Efeito proporcional de troca rápida e deformação visual de caracteres estendido também às conversas, contatos e menus do WhatsApp Web (preservando a caixa de digitação).
- **🔊 Segurança de Áudio ao Abrir Tampa / Reiniciar & Reverb Geral:**
  - `Meta Paranoia` (loop) e `Sirene` (1× por abertura do app no dia 24) recuperam automaticamente via `powerMonitor` (`resume`/`unlock-screen`), `focus` e watchdog de suspensão.
  - Reverb de bunker aplicado a áudios do WhatsApp (`<audio>`/`<video>`), notificações (`votv_email.ogg` obrigatório no Bad Sun), cliques em chaves/botões (`votv_flashlight.ogg`) e efeitos especiais VotV (`pcStartup`/`pcShutdown`, `turnon`/`turnoff`) — mantendo Meta Paranoia e Sirene sem reverb.
- **🔒 Trava do Dia 24 & Easter Egg `powerDown`:** No dia 24 não é possível desligar o evento (a chave retorna sozinha); abrir os contatos `+55 27 99612-7513` ou `+55 27 99759-1059` (sob qualquer nome) dispara o som `powerDown`.

---

## 🛠️ Correção Definitiva de Figurinhas & Miniaturas do YouTube da Versão 3.7.1 (`v3.7.1`)

- **🕵️ Causa-Raiz Descoberta para Figurinhas com Falha de Download (HTTP 400 `invalid-header`):**
  - O nome de exibição `WhatsApp 3 Sol Finally Tests Versão 3.7` (caractere não-ASCII `ã` em **`Versão`**) fazia o Electron gerar `app.userAgentFallback` contendo `WhatsApp3SolFinallyTestsVersão3.x/34.5.8`. Service Workers e Web Workers do WhatsApp Web usavam esse fallback em downloads CDN `.enc`, recebendo **`HTTP 400 invalid-header`** dos proxies da Meta.
  - Definido `app.userAgentFallback = getChromeUserAgent()` antes de `app.whenReady()` e adicionado `enforceAsciiUserAgentOnSession()` em todas as sessões (`defaultSession`, contas e IA) para garantir cabeçalho `User-Agent` 100% ASCII do Chrome em janelas, Service Workers e Web Workers.
- **⚡ Acelerador & Recuperação de Miniaturas de Links (YouTube, Spotify e Externos):**
  - O `WAWebLinkPreviewChatAction.getLinkPreview` aguardava até 9–10s pelo celular principal e caía no card vazio (`www.youtube.com`) quando o aparelho demorava a responder.
  - Agora, após `900ms` sem resposta rica do celular (ou em fallback mínimo), o preload aciona em paralelo `WAWebMexFetchPlaintextLinkPreviewJob.mexFetchPlaintextLinkPreview` para entregar título, descrição e miniatura HD instantaneamente sem afetar figurinhas.

---

## 🛠️ Correção de Hook CDN & Preconnect da Versão 3.7 (`v3.7.0`)

- **🖼️ Correção do Hook `fetch` + Retry Real para Mídia CDN & Previews:**
  - Corrigido o erro de sintaxe no template literal do interceptor `window.fetch` em `whatsappPreload.ts` (que impedia a execução do retry automático de mídia e do hook de clipboard em `v3.67`), agora validado por AST em teste unitário (`vm.Script`).
  - Retry automático com backoff (`250ms`, `850ms`) para downloads CDN em `.whatsapp.net`, `.fbcdn.net`, `.ytimg.com` e `.scdn.co`.
  - Mantido HTTP/3 QUIC ativo e re-ativado o `preconnect` imediato de YouTube & Spotify (`2` sockets + `<link rel="preconnect">`) mantendo `mmg.whatsapp.net` fora do `preconnect` ocioso para não derrubar downloads de figurinhas animadas, além de permissões `persistent-storage`/`storage-access` liberadas na sessão.

---

## 🛠️ Correções Anteriores (v3.67 / v3.6 / v3.5) (`v3.6.7`)

- **🖼️ Fim das Falhas com Botão de Download em Figurinhas Maiores:**
  - Desativado `HTTP/3 QUIC` (`--disable-quic`) para que downloads de figurinhas animadas em `mmg.whatsapp.net` / `*.fna.whatsapp.net` trafeguem exclusivamente em **HTTP/2 TLS** estável sem quedas UDP.
  - Removido o `preconnect` agressivo na inicialização (`mmg.whatsapp.net` / `web.whatsapp.com` + 8 sockets de previews), passando a aquecer apenas **1 socket por host do YouTube/Spotify após o carregamento do WhatsApp Web (`did-finish-load`)**, preservando miniaturas rápidas de links sem conflitar com o pool de figurinhas.
  - Limpeza única do cache HTTP corrompido de versões anteriores (`ses.clearCache()` sem afetar login/conversas) e retry automático seguro para requisições `fetch` de mídia CDN do WhatsApp em quedas transitórias.

---

## 🛠️ Correções Anteriores (v3.6 / v3.5) (`v3.6.0`)

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

> Desenvolvido por **Douglas da Cunha Zanetti (Doguinha)** — Versão 3.7 (`3.7.0`).
