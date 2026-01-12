# 📝 Registro de Mudanças (Changelog)

Todas as alterações notáveis neste projeto serão documentadas neste arquivo.

## [1.0.0] - 2026-01-08
### 🚀 Lançamento Inicial
- **Sistema Base:** Mudança para base Debian com ambiente de build Zorin OS.
- **Navegador:** Implementação do Firefox ESR como navegador padrão com foco em privacidade.
- **Otimização:** Execução de script de sanitização e zeramento de blocos de disco para compressão do arquivo final.
- **VirtualBox:** Inclusão dos *Guest Additions* para suporte a pastas compartilhadas e redimensionamento automático de tela.
- **Segurança:** Limpeza total de logs, históricos de terminal e caches antes da geração do arquivo VDI final.

---

## [1.1.0] - 2026-01-12
### Adicionado
- Suporte oficial à arquitetura **ARM64** (aarch64).
- Script `testar_paper.sh` para utilizadores de Linux (formato LF).
- Script `testar_paper_linux.bat` com menu de seleção para Windows.
- Tabela de partição **GPT** para ARM64.
- Documentação de build para ARM64 no README.

### Alterado
- Kernel atualizado para a versão estável **6.12.63**.
- README.md reformulado para destacar a prioridade histórica das versões x86.
- Melhoria na emulação de vídeo para a versão i386 (vga std).

---
