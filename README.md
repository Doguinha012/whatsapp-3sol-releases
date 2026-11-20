<div align="center">

<img src="assets/logo.gif" alt="WhatsApp 3 Sol Logo" width="128" />

# ☀️ WhatsApp 3 Sol — Finally Tests Versão 3

**Aplicativo desktop multi-contas para Windows baseado no WhatsApp Web, com sessões isoladas, privacidade granular, fixação ilimitada de conversas, transcrição 100% offline, equalizador e efeitos de voz ao vivo.**

[![Version](https://img.shields.io/badge/versão-3.0.0-25D366?style=for-the-badge)](https://github.com/Doguinha012/whatsapp-3sol-releases/releases)
[![Platform](https://img.shields.io/badge/Windows-x64-0078D6?style=for-the-badge&logo=windows)](#)

</div>

---

## ✨ Novidades da Versão 3 (`v3.0.0`)

### 🆕 Adições
- **📌 Fixados Ilimitados Aprimorados:** Fixe quantos contatos quiser na janela flutuante móvel, clique para abrir diretamente a conversa na conta correta, suporte automático para contatos renomeados e ícones visuais de status (`✓`, `✓✓`, `✓✓ azul`).
- **⌖ Botão Discreto de Fixar nas Conversas:** Ícone minimalista ao lado da hora de cada conversa na barra lateral (e botão no cabeçalho do chat aberto), configurável em **Configurações**.
- **🎵 Integração com Spotify no Topo:** Visualize a música que está tocando no Spotify e envie/insira ou copie o link direto no chat (ativável/desativável em Configurações).
- **🎤 Efeito de Envio de Áudio (Microfone ao Vivo):** Nova aba no Equalizador permitindo aplicar efeitos em tempo real diretamente ao gravar pelo microfone padrão do WhatsApp (Natural por padrão).
- **📦 Exportação e Importação `.3sol`:** Salve suas contas (com senhas de exclusão), configurações, temas e imagens de fundo em um arquivo portátil `.3sol` com validação de versão.
- **🛡️ Privacidade Granular Expandida:** Opções separadas para desfocar prévia da barra lateral vs conversa atual, descrições em grupos, horários das últimas mensagens e avatares sem foto/ícones padrão (`K`, `L`, WhatsApp).
- **🖼️ Exportação Flexível de Mídias:** Opções no menu de contexto para salvar GIFs, vídeos e figurinhas animadas em **GIF**, **WebM** ou **MP4**.
- **🎵 Aba Clematis Player:** Prévia oficial da futura integração entre o WhatsApp 3 Sol e o **Clematis Player**.
- **🔄 Atualizador Automático via GitHub:** Verificação discreta na barra superior com resumo de novidades, barra de progresso e fechamento automático do aplicativo ao instalar.

### 🛠️ Correções de Bugs & Melhorias
- Corrigida a sugestão ortográfica em português (`pt-BR`) em todas as abas de contas simultaneamente.
- Corrigido o efeito global **Voz de Esquilo** impedindo sobrescrita de velocidade pelo player do WhatsApp.
- Removido o botão de transcrição de GIFs animados.
- Corrigido o alinhamento de texto da Roleta para nunca colidir com o ícone central e fechamento automático do aviso de sorteio.
- Suavizado o brilho do cursor e melhorado o contraste dos botões no modo Liquid Glass (desativado por padrão).
- Clicar em notificações do Windows agora abre a conta e tenta abrir diretamente o contato/grupo correspondente.
- Redução de uso de RAM com throttling de observadores DOM, limite de cache de mídia e liberação automática do worker de transcrição após inatividade.
- O instalador NSIS fecha automaticamente qualquer instância aberta do WhatsApp 3 Sol antes de atualizar.

---

## 🚀 Principais Recursos

- **Múltiplas Contas Isoladas:** Sessões totalmente separadas (`persist:account-{id}`), ordenação e modo **Lado a Lado (Split View)**.
- **Transcrição Local 100% Offline:** Transcreva áudios longos em segundo plano sem depender de nuvem externa.
- **Personalização Avançada:** Temas visuais, cores personalizadas para os ícones nativos do WhatsApp, papel de parede e efeito evento **Bad Sun**.
- **Extensões Integradas:** Privacidade dinâmica, Disparador, Estragar Imagem & Criador de Figurinhas, Roleta, Equalizador & Voz e integração futura **Clematis Player**.

---

## 🛠️ Desenvolvimento & Build (Windows)

```bash
npm install
npm run lint
npm test
npm run pack:all
```

> Desenvolvido por **Douglas da Cunha Zanetti (Doguinha)** — Versão 3 (`3.0.0`).
