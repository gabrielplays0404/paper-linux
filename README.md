<p align="center">
  <img src="https://github.com/gabrielplays0404/paper-linux/raw/main/logo.png" width="200" alt="Paper Linux Logo">
</p>

<p align="center">
  <a href="#-paper-linux-português">Português</a> | 
  <a href="#-paper-linux-english">English</a>
</p>

---

# 🇧🇷 Paper Linux (Português)
> Uma distribuição Linux leve, modular e multi-arquitetura, focada em simplicidade e performance.

O **Paper Linux** é um sistema operativo minimalista projetado para ser educativo e eficiente. Utiliza o gestor de janelas **IceWM** para garantir uma interface gráfica fluida, sendo capaz de reviver hardware antigo ou rodar em dispositivos modernos de última geração.

---

## 📜 Histórico de Lançamentos
* **v1.0.0:** Estreia oficial focada em arquiteturas de PC (**x86_64** e **i386**).
* **v1.1.0 (Atual):** Suporte a **ARM64**, migração para **GPT**, suporte **UEFI**, Kernel **6.12.63** (ARM) e Kernel **6.1.0-39** (i386, amd64).

---

## 💻 Requisitos do Sistema / System Requirements

### 🇧🇷 Português
**Para rodar o Paper Linux:**
* **x86 (32/64 bits):** Processador 1GHz, 256MB RAM (i386) / 512MB RAM (x86_64).
* **ARM64:** Dispositivos compatíveis com ARMv8 (ex: Raspberry Pi 3/4/5, Pine64) ou máquinas virtuais QEMU com suporte a EFI.
* **Recomendado:** 1GB RAM ou mais para uma experiência fluida no IceWM.

**Para compilar/extrair os arquivos de construção:**
* **Espaço em Disco:** 6 GB (Compactado) / 15-20 GB (Extraído para build).
* **Sistema Hospedeiro:** Linux (Debian, Ubuntu ou Zorin OS recomendados) ou WSL2.

---

## 💾 Instalação e Pós-Instalação

### 1. Criando o Pendrive Bootável
* **Windows:** Recomendamos o **Rufus** (use o modo "DD") ou o **Ventoy**.
* **Linux:** Recomendamos o **Ventoy** ou o comando `dd`:
  `sudo dd if=paper-linux.iso of=/dev/sdX bs=4M status=progress conv=fsync`

### 2. Instalação no Disco (HD/SSD)
Uma vez iniciado pelo pendrive, você pode instalar o sistema permanentemente usando o comando:
`sudo paper-install`

### 3. Configurações Iniciais (Pós-Instalação)
* **Wi-Fi:** `nmcli dev wifi list` e `sudo nmcli dev wifi connect "REDE" password "SENHA"`
* **Hora:** `sudo timedatectl set-ntp true` e `sudo timedatectl set-timezone America/Sao_Paulo`
* **Teclado:** `setxkbmap br`

---

### 📱 Paper Linux Mobile (Android Chroot)

Versão especial otimizada para tablets e smartphones (Testado em Multilaser M7 com Android Go).
<p align="center">
  <img src="https://raw.githubusercontent.com/gabrielplays0404/paper-linux/main/mobile_demo.png" width="600" alt="Paper Linux Mobile Demo">
  <br>
  <b>Paper Linux v1.0 rodando no Multilaser M7</b>
</p>
**Instalação Mobile:**

1.  **Dependências:** Root (Magisk), MacroDroid e um cliente VNC.
    
2.  **Arquivos:** Baixe o `paperlinux.img` e o script `entrar_paper.sh`.
    
3.  **Localização:** - Coloque a imagem em `/sdcard/`.
    
    -   Coloque o script em `/data/local/` e dê permissão `chmod +x`.
        
4.  **Execução:** Importe a macro no MacroDroid e inicie pelo **Atalho da Tela Inicial**.
    
5.  **Acesso VNC:** - **Endereço:** `127.0.0.1:5901`
    
    -   **Senha:** `paperlin`

---

## 📥 Download e Requisitos
* **Link para Download (MEGA):** [Clique Aqui](https://mega.nz/file/AFtm2YCR#Wv2PqExmsF4AhStQIjydQ9wm9YX743ydMVPbaLqqxME)
* **Tamanho:** 4,3 GB (Compactado)
* **Requisitos:** Ambiente Linux (Debian/Ubuntu recomendado) ou WSL2.

---

## 🚀 Diferenciais do Paper Linux
| Componente | Especificação |
| :--- | :--- |
| **Base** | Debian (Build no Zorin OS) |
| **Interface** | IceWM (Ultra-leve) |
| **Consumo de RAM** | ~250MB - 400MB (Em repouso) |
| **Navegador** | Firefox-ESR |

---
## 🔨 Script de Compilação ARM64
```bash
#!/bin/bash
# Construtor de Imagem Paper Linux ARM64
IMAGE_NAME="paper_linux_arm64.img"
IMAGE_SIZE="4G"

echo "[1] Criando arquivo de imagem vazio..."
qemu-img create -f raw $IMAGE_NAME $IMAGE_SIZE

echo "[2] Criando tabela de partições GPT..."
parted $IMAGE_NAME mklabel gpt
parted $IMAGE_NAME mkpart primary fat32 1MiB 512MiB
parted $IMAGE_NAME set 1 esp on
parted $IMAGE_NAME mkpart primary ext4 512MiB 100%
```
---

## 🤝 Contribuições
Sinta-se à vontade para abrir **Issues** ou enviar **Pull Requests**. Toda ajuda para melhorar o Paper Linux é bem-vinda!

---

<br><br>

# 🇺🇸 Paper Linux (English)
> A lightweight, modular, and multi-architecture Linux distribution focused on simplicity and performance.

---

## 📜 Release History
* **v1.0.0:** Official debut focusing on PC architectures (**x86_64** and **i386**).
* **v1.1.0 (Current):** **ARM64** support, **GPT** partition table, **UEFI** support, Kernel **v6.12.63**  (ARM) and Kernel **6.1.0-39 (i386, amd64).

---

## 💻 System Requirements

### 🇺🇸 English
**To run Paper Linux:**
* **x86 (32/64 bits):** 1GHz CPU, 256MB RAM (i386) / 512MB RAM (x86_64).
* **ARM64:** ARMv8 compatible devices (e.g., Raspberry Pi 3/4/5, Pine64) or QEMU virtual machines with EFI support.
* **Recommended:** 1GB RAM or more for a smooth IceWM experience.

**To build/extract build files:**
* **Disk Space:** 6 GB (Compressed) / 15-20 GB (Extracted for building).
* **Host OS:** Linux (Debian, Ubuntu, or Zorin OS recommended) or WSL2.

---
  
## 💾 Installation and Setup

### 1. Creating a Bootable USB
* **Windows:** We recommend **Rufus** (use "DD mode") or **Ventoy**.
* **Linux:** We recommend **Ventoy** or the `dd` command:
  `sudo dd if=paper-linux.iso of=/dev/sdX bs=4M status=progress conv=fsync`

### 2. Disk Installation (HDD/SSD)
After booting from the USB, you can install Paper Linux permanently using:
`sudo paper-install`

### 3. Post-Installation Steps
* **Wi-Fi:** `nmcli dev wifi list` then `sudo nmcli dev wifi connect "SSID" password "PASSWORD"`
* **Time Sync:** `sudo timedatectl set-ntp true`
* **Keyboard Layout:** `setxkbmap us` (or your preferred layout)

---

### 📱 Paper Linux Mobile (Android Chroot)

Special edition optimized for tablets and smartphones (Tested on Multilaser M7 running Android Go).

<p align="center">
  <img src="https://raw.githubusercontent.com/gabrielplays0404/paper-linux/main/mobile_demo.png" width="600" alt="Paper Linux Mobile Demo">
  <br>
  <b>Paper Linux v1.0 running in Multilaser M7</b>
</p>

**Mobile Setup:**

1.  **Dependencies:** Root (Magisk), MacroDroid, and a VNC client.
    
2.  **Files:** Download `paperlinux.img` and the `entrar_paper.sh` script.
    
3.  **Placement:** - Move the image to `/sdcard/`.
    
    -   Move the script to `/data/local/` and run `chmod +x`.
        
4.  **Execution:** Import the macro into MacroDroid and launch via the **Home Screen Shortcut**.
    
5.  **VNC Access:** - **Address:** `127.0.0.1:5901`
    
    -   **Password:** `paperlin`

---

## 📥 Download (Build Files)
* **MEGA Download:** [Click Here](https://mega.nz/file/AFtm2YCR#Wv2PqExmsF4AhStQIjydQ9wm9YX743ydMVPbaLqqxME)
* **Size:** 4.3 GB (Compressed)
* **Requirements:** Linux (Debian/Ubuntu) or WSL2.

---

## 🚀 Paper Linux Key Features
| Component | Specification |
| :--- | :--- |
| **Base** | Debian (Build on Zorin OS) |
| **Interface** | IceWM (Ultra-lightweight) |
| **RAM Usage** | ~250MB - 400MB (Idle) |
| **Browser** | Firefox-ESR |

---

## 🔨 ARM64 Build Script
```bash
#!/bin/bash
# Paper Linux ARM64 Image Builder
IMAGE_NAME="paper_linux_arm64.img"
IMAGE_SIZE="4G"

echo "[1] Creating empty image file..."
qemu-img create -f raw $IMAGE_NAME $IMAGE_SIZE

echo "[2] Creating GPT partition table..."
parted $IMAGE_NAME mklabel gpt
parted $IMAGE_NAME mkpart primary fat32 1MiB 512MiB
parted $IMAGE_NAME set 1 esp on
parted $IMAGE_NAME mkpart primary ext4 512MiB 100%
```
---

## 🤝 Contributions
Feel free to open **Issues** or submit **Pull Requests**. Your help to improve Paper Linux is appreciated!

---

<p align="center">Desenvolvido por Paper Linux Team - 2026</p>
