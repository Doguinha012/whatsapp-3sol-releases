<div align="center">

<img src="assets/logo.gif" alt="WhatsApp 3 Sol Logo" width="128" />

# WhatsApp 3 Sol — Finally Tests Versão 3.2

**Aplicativo desktop multi-contas para Windows baseado no WhatsApp Web, com sessões isoladas, privacidade granular, fixação ilimitada de conversas, transcrição 100% offline, equalizador e efeitos de voz ao vivo.**

[![Version](https://img.shields.io/badge/versão-3.2.0-f97316?style=for-the-badge)](https://github.com/Doguinha012/whatsapp-3sol-releases/releases)
[![Platform](https://img.shields.io/badge/Windows-x64-0078D6?style=for-the-badge&logo=windows)](#)
[![Clematis](https://img.shields.io/badge/Clematis_Player-GitHub-6366f1?style=for-the-badge)](https://github.com/Doguinha012/Clematis-Player)

</div>

---

## Novidades da Versão 3.2 (`v3.2.0`)

- **Fotos de Perfil & Grupos Restauradas nos Fixados (`⌖`):** Captura aprimorada de avatares no WhatsApp Web com download automático em base64 pelo processo principal, garantindo que fotos de contatos e grupos apareçam com nitidez e não expirem.
- **Spotify Oficial no Chat:** Ícone oficial do Spotify, exibição da **capa do álbum** da música em reprodução e resolução automática para o **link direto da faixa** (`https://open.spotify.com/track/...`) ao invés de link de pesquisa.
- **Tema Laranja Padrão no WhatsApp (`#f97316`):** Cor padrão dos ícones e indicadores ajustada para laranja, cobrindo também a bolinha numérica de não lidas na aba de conversas e os marcadores de **Status** e **Canais** na barra lateral esquerda.
- **Interface com Ícones em Caracteres:** Todos os ícones internos da interface do WhatsApp 3 (topo, Fixados, Configurações e Extensões) substituídos por símbolos tipográficos limpos no lugar de emojis.
- **Seletor Completo de Emojis para Contas:** Criação e edição de abas de contas agora contam com seletor completo separado por categorias (Populares, Rostos, Gatos & Animais, Pessoas, Comida, Objetos & Trabalho, Jogos & Música, Símbolos e Todos) com barra de rolagem e busca.
- **Link Oficial do Clematis Player:** Aba Clematis atualizada com link direto para https://github.com/Doguinha012/Clematis-Player enquanto preparamos a integração da próxima versão.

---

## Principais Recursos

- **Múltiplas Contas Isoladas:** Sessões totalmente separadas (`persist:account-{id}`), ordenação e modo **Lado a Lado (Split View)**.
- **Transcrição Local 100% Offline:** Transcreva áudios em segundo plano com motor Whisper ONNX sem depender de nuvem externa.
- **Fixados Ilimitados (`⌖`):** Fixe contatos na janela flutuante com status visuais (`✓`, `✓✓`, `✓✓ azul`), busca automática após renomear contatos e abertura direta da conversa.
- **Backup Portátil `.3sol`:** Exporte e importe todas as contas, configurações, temas e papéis de parede em um único arquivo.
- **Extensões Integradas:** Privacidade dinâmica granular, Disparador, Estragar Imagem & Figurinhas, Roleta, Equalizador & Efeitos de Voz ao vivo no microfone, e prévia do **Clematis Player**.
- **Atualizador Automático via GitHub:** Verificação discreta com changelog, progresso de download e fechamento automático pelo instalador NSIS.

---

## Desenvolvimento & Build (Windows)

```bash
npm install
npm run lint
npm test
npm run pack:all
```

> Desenvolvido por **Douglas da Cunha Zanetti (Doguinha)** — Versão 3.2 (`3.2.0`).
