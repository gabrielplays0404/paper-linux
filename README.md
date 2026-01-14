<p align="center">
  <img src="https://github.com/gabrielplays0404/paper-linux/raw/main/logo.png" width="200" alt="Paper Linux Logo">
</p>

# 📄 Paper Linux
> Uma distribuição Linux leve, modular e multi-arquitetura, focada em simplicidade e performance.

O **Paper Linux** é um sistema operativo minimalista projetado para ser educativo e eficiente. Utiliza o gestor de janelas **IceWM** para garantir uma interface gráfica fluida, sendo capaz de reviver hardware antigo ou rodar em dispositivos modernos de última geração.

---

## 📜 Histórico de Lançamentos
* **v1.0.0 (Lançamento Original):** Estreia oficial do Paper Linux com foco total em arquiteturas de PC (**x86_64** e **i386**), utilizando o script de construção automatizado `paper-build.sh`.
* **v1.1.0 (Versão Atual):** Expansão para a arquitetura **ARM64**, migração para tabela de partição **GPT** e atualização para o Kernel **6.12.63**.

---

## 🚀 Novidades da v1.1.0
- **Suporte ARM64:** Agora o Paper Linux pode ser emulado ou rodar em dispositivos ARM.
- **Kernel:** Atualizado para **v6.12.63** (maior estabilidade e suporte a hardware).
- **Particionamento:** Transição de MBR para **GPT** na versão ARM64.
- **Boot Moderno:** Compatibilidade com sistemas UEFI/EDK2 (ARM64).

---

## 🖥️ Versões Disponíveis

| Versão | Arquitetura | Foco de Uso | Formato |
| :--- | :--- | :--- | :--- |
| **Desktop 64** | `x86_64` | PCs modernos e máquinas virtuais com alta performance. | `.iso` |
| **Legacy 32** | `i386` | Hardware antigo (Pentium, Core Duo) e baixo consumo de RAM. | `.iso` |
| **Mobile/Dev** | `ARM64` | Emulação via QEMU, Raspberry Pi e dispositivos ARM. | `.img` |

---

## 🛠️ Como Testar (Emulação com QEMU)

Fornecemos scripts de automação para facilitar o teste em diferentes sistemas:

### 1. Pré-requisitos
Certifique-se de ter o **QEMU** instalado.
- **Windows:** Instale o QEMU para Windows (w64).
- **Linux:** `sudo apt install qemu-system-x86 qemu-system-arm`

### 2. Execução
#### 🪟 No Windows:
Execute o ficheiro `testar_paper_linux.bat`. 

#### 🐧 No Linux:
Dê permissão de execução e inicie o script:
```bash
chmod +x testar_paper.sh
./testar_paper.sh
```
---

## 📥 Download da Máquina Virtual (VM) De Construção

A imagem foi sanitizada e otimizada para ocupar o menor espaço possível, garantindo privacidade e performance.

* **Link para Download (MEGA):** https://mega.nz/file/5cVT2SyA#3OwfSUHbWYuZA1TEbnapEUE51NjiuuO08GqDGqui814
* **Tamanho do arquivo:** 14 GB (Compactado), 34 GB (extraído)
* **Formato:** OVF/VDI (Compatível com VirtualBox)

### 👤 Credenciais de Acesso
* **Usuário:** `Minha-Máquina-Virtual`
* **Senha:** `231645`

---

## 🛠️ Como Importar no VirtualBox
1. Faça o download e extraia o arquivo `.tar.gz`.
2. No VirtualBox, vá em **Máquina > Acrescentar**.
3. Selecione o arquivo `.vbox` dentro da pasta extraída.
4. Ajuste a memória RAM (mínimo 4GB recomendado) e inicie o sistema.

## 🚀 Diferenciais da VM
- **Privacidade:** Navegador Brave pré-instalado com limpeza automática.
- **Eficiência:** Disco "zero-filled" para melhor compressão e performance.
- **Base Sólida:** Compatibilidade total com pacotes `.deb` do Debian.

## 🚀 Diferenciais do Paper Linux
- **Componente,Especificação**
- **Base:** Debian (Build no Zorin OS)
- **Interface:** (WM),IceWM (Ultra-leve)
- **Gerenciador de Janelas:** IceWM Window Manager
- **Consumo de RAM:** ~250MB - 400MB (Em repouso)
- **Navegador Padrão:** Firefox-ESR
- **Foco:** Performance Extrema e Estabilidade

## 🔨 Build System
- **amd64 & i386:** Geradas via ./paper-build.sh.
- **ARM64:** Imagem GPT gerada via debootstrap e distribuída como Bundle (IMG + Kernel).

## 🔨 Script Construção ARM64
faça o script build-paper-arm.sh e siga as instruções embutidas no arquivo
``` Bash
#!/bin/bash
# Paper Linux ARM64 Image Builder

IMAGE_NAME="paper_linux_arm64.img"
IMAGE_SIZE="4G"

echo "[1] Criando arquivo de imagem vazio..."
qemu-img create -f raw $IMAGE_NAME $IMAGE_SIZE

echo "[2] Criando tabela de partição GPT..."
parted $IMAGE_NAME mklabel gpt
parted $IMAGE_NAME mkpart primary fat32 1MiB 512MiB  # Partição EFI
parted $IMAGE_NAME set 1 esp on
parted $IMAGE_NAME mkpart primary ext4 512MiB 100%   # Partição Root

echo "[3] Formatando e Montando (Requer Sudo)..."
# Aqui você usaria o 'losetup' para montar a imagem como um disco real
# e instalaria o sistema base via debootstrap para ARM64.
```

---

## 🤝 Contribuições
Sinta-se à vontade para abrir Issues ou enviar Pull Requests. O Paper Linux é um projeto comunitário!

---

## AVISO IMPORTANTE UEFI
**Desative o Secure Boot antes de instalar o Paper Linux. Atualmente, Não dá para usar o Paper Linux em Dual Boot Com o Windows 11**
