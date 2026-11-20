<div align="center">

<img src="assets/logo.gif" alt="WhatsApp 3 Sol Logo" width="128" />

# ☀️ WhatsApp 3 Sol — Finally Tests Versão 3.3

**Aplicativo desktop multi-contas para Windows baseado no WhatsApp Web, com sessões isoladas, privacidade granular, fixação ilimitada de conversas, transcrição 100% offline, equalizador e efeitos de voz ao vivo.**

[![Version](https://img.shields.io/badge/versão-3.3.0-f97316?style=for-the-badge)](https://github.com/Doguinha012/whatsapp-3sol-releases/releases)
[![Platform](https://img.shields.io/badge/Windows-x64-0078D6?style=for-the-badge&logo=windows)](#)
[![Clematis](https://img.shields.io/badge/Clematis_Player-GitHub-6366f1?style=for-the-badge)](https://github.com/Doguinha012/Clematis-Player)

</div>

---

## ✨ Novidades da Versão 3.3 (`v3.3.0`)

- **😀 Ícones em Emojis Restaurados:** Todos os ícones de botões, abas, Fixados, Configurações e Extensões voltaram ao visual clássico em emojis, mantendo o novo **Seletor Completo de Emojis** por categorias para criação e edição de contas.
- **🎧 Logo Oficial do Spotify Corrigida:** Ícone SVG oficial do Spotify redimensionado (`18px`/`20px`) com contraste e proporções corrigidas (sem cortes), exibindo capa do álbum e link direto da faixa (`open.spotify.com/track/...`).
- **🔥 Evento Bad Sun (Death Sun) com Tremulação de Fogo:** Durante o evento Bad Sun, além das cores quentes dessaturadas e da censura sobre o sol, a tela recebe um piscar escuro sutil e irregular imitando clarão/luz de fogo em segundo plano.
- **📌 Botão de Fixar Maior na Lista de Conversas:** Aumentado o tamanho e área clicável do botão de fixar em frente a cada conversa na barra lateral do WhatsApp (`24x24px`).

---

## Versão 3.2 (`v3.2.0`) & Principais Recursos

- **Fotos de Perfil & Grupos nos Fixados (`📌`):** Captura aprimorada com armazenamento local em base64 PNG pelo processo principal.
- **Tema Laranja Padrão no WhatsApp (`#f97316`):** Cor padrão laranja cobrindo ícones, botões de ação e bolinhas de não lidas em Conversas, Status e Canais.
- **Múltiplas Contas Isoladas:** Sessões totalmente separadas (`persist:account-{id}`), ordenação e modo **Lado a Lado (Split View)**.
- **Transcrição Local 100% Offline:** Transcreva áudios em segundo plano com motor Whisper ONNX sem depender de nuvem externa.
- **Backup Portátil `.3sol`:** Exporte e importe todas as contas, configurações, temas e papéis de parede em um único arquivo.
- **Extensões Integradas:** Privacidade dinâmica granular, Disparador, Estragar Imagem & Figurinhas, Roleta, Equalizador & Efeitos de Voz ao vivo no microfone, e prévia do **Clematis Player** (`https://github.com/Doguinha012/Clematis-Player`).
- **Atualizador Automático via GitHub:** Verificação discreta com changelog, progresso de download e fechamento automático pelo instalador NSIS.

---

## 🛠️ Desenvolvimento & Build (Windows)

```bash
npm install
npm run lint
npm test
npm run pack:all
```

> Desenvolvido por **Douglas da Cunha Zanetti (Doguinha)** — Versão 3.3 (`3.3.0`).
