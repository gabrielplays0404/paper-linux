# 📝 Registro de Mudanças (Changelog)

Todas as alterações notáveis neste projeto serão documentadas neste arquivo.

## [1.1.1] - 2026-01-14
### 🚀 Adicionado
- **Suporte Nativo a UEFI:** ISO agora é híbrida, compatível com máquinas modernas (GPT/EFI) e antigas (MBR/Legacy).
- **Instalador Oficial (`paper-install`):** Script definitivo para instalação no HD/SSD com detecção automática de modo de boot e particionamento inteligente.
- **Servidor SSH:** `openssh-server` integrado ao sistema base para permitir gerenciamento remoto e transferência de arquivos (SCP) durante o desenvolvimento.
- **Gestão de Versões:** Implementação de controle de versões via Proton Drive para manter links estáveis.

### 🛠️ Alterado
- **Processo de Build:** Atualização do `build_paper.sh` para utilizar `grub-mkrescue` em vez de `xorriso` puro, garantindo maior compatibilidade de boot.
- **Estrutura da ISO:** Reorganização dos diretórios (`/boot/grub` e `/EFI`) para seguir o padrão oficial de sistemas operacionais.
- **Comunicação Host/Guest:** Configuração otimizada de portas no VirtualBox para evitar erros de "Bad Port".

### 🔧 Corrigido
- Ajuste no `$PATH` do sistema para reconhecer scripts em `/usr/local/bin` sem necessidade de caminhos absolutos.
- Correção de permissões de acesso ao servidor gráfico Xorg quando operando via terminal SSH no Zorin OS.

---

## [1.1.0] - 2026-01-12
### Adicionado
- Suporte oficial à arquitetura **ARM64** (aarch64).
- Script `testar_paper.sh` para utilizadores de Linux (formato LF).
- Script `testar_paper_linux.bat` com menu de seleção para Windows.
- Tabela de partição **GPT** para ARM64.

---

## [1.0.0] - 2026-01-08
### 🚀 Lançamento Inicial
- **Sistema Base:** Mudança para base Debian com ambiente de build Zorin OS.
- **Navegador:** Implementação do Firefox ESR como navegador padrão.
- **VirtualBox:** Inclusão dos *Guest Additions* e sanitização de logs.
