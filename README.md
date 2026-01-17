<p align="center">
  <img src="https://github.com/gabrielplays0404/paper-linux/raw/main/logo.png" width="200" alt="Paper Linux Logo">
</p>

<p align="center">
  <a href="#-paper-linux-português">Português</a> | 
  <a href="#-paper-linux-english">English</a>
</p>

---

# 📄 Paper Linux (Português)
> Uma distribuição Linux leve, modular e multi-arquitetura, focada em simplicidade e performance.

O **Paper Linux** é um sistema operativo minimalista projetado para ser educativo e eficiente. Utiliza o gestor de janelas **IceWM** para garantir uma interface gráfica fluida, sendo capaz de reviver hardware antigo ou rodar em dispositivos modernos de última geração.

---

## 📜 Histórico de Lançamentos
* **v1.0.0 (Lançamento Original):** Estreia oficial do Paper Linux com foco total em arquiteturas de PC (**x86_64** e **i386**), utilizando o script de construção automatizado `paper-build.sh`.
* **v1.1.0 (Versão Atual):** Expansão para a arquitetura **ARM64**, migração para tabela de partição **GPT** e atualização para o Kernel **6.12.63**.

---

## 🚀 Novidades da v1.1.0
* **Suporte ARM64:** Agora o Paper Linux pode ser emulado ou rodar em dispositivos ARM.
* **Kernel:** Atualizado para **v6.12.63** (maior estabilidade e suporte a hardware).
* **Particionamento:** Transição de MBR para **GPT** na versão ARM64.
* **Boot Moderno:** Compatibilidade com sistemas UEFI/EDK2 (ARM64).

> [!IMPORTANT]
> **Compatibilidade UEFI (v1.1.1):**
> O Paper Linux agora suporta UEFI, mas **não possui suporte a Secure Boot ainda**. 
> Se o sistema não iniciar, desative o "Secure Boot" e habilite o "Legacy Support" ou "CSM" (se necessário) nas configurações da sua BIOS.

---

## 🖥️ Versões Disponíveis
| Versão | Arquitetura | Foco de Uso | Formato |
| :--- | :--- | :--- | :--- |
| **Desktop 64** | `x86_64` | PCs modernos e VMs com alta performance. | `.iso` |
| **Legacy 32** | `i386` | Hardware antigo e baixo consumo de RAM. | `.iso` |
| **Mobile/Dev** | `ARM64` | Emulação via QEMU e dispositivos ARM. | `.img` |

---

## 🛠️ Como Testar (Emulação com QEMU)

### 1. Pré-requisitos
Certifique-se de ter o **QEMU** instalado.
* **Windows:** Instale o QEMU para Windows (w64).
* **Linux:** `sudo apt install qemu-system-x86 qemu-system-arm`

### 2. Execução
* **No Windows:** Execute o ficheiro `testar_paper_linux.bat`. 
* **No Linux:**
    ```bash
    chmod +x testar_paper.sh
    ./testar_paper.sh
    ```

---

## 📥 Download dos arquivos de construção

* **Link para Download (MEGA):** [Clique Aqui](https://mega.nz/file/AFtm2YCR#Wv2PqExmsF4AhStQIjydQ9wm9YX743ydMVPbaLqqxME)
* **Tamanho:** 4,3 GB (Compactado) / 6-15 GB (Extraído)
* **Requisitos** Linux (Debian/Ubuntu e derivados Recomendado) ou wsl2 (para usar no windows)

---

## 🚀 Diferenciais do Paper Linux
| Componente | Especificação |
| :--- | :--- |
| **Base** | Debian (Build no Zorin OS) |
| **Interface** | IceWM (Ultra-leve) |
| **Consumo de RAM** | ~250MB - 400MB (Em repouso) |
| **Navegador** | Firefox-ESR |

---

# 📄 Paper Linux (English)
> A lightweight, modular, and multi-architecture Linux distribution focused on simplicity and performance.

**Paper Linux** is a minimalist operating system designed to be educational and efficient. It uses the **IceWM** window manager to ensure a fluid graphical interface, capable of reviving legacy hardware or running on modern high-end devices.

---

## 📜 Release History
* **v1.0.0 (Original Release):** Official debut focusing on PC architectures (**x86_64** and **i386**), using the `paper-build.sh` automated build script.
* **v1.1.0 (Current Version):** Expansion to **ARM64** architecture, migration to **GPT** partition table, and update to Kernel **v6.12.63**.

---

## 🚀 What's New in v1.1.0
* **ARM64 Support:** Paper Linux can now be emulated or run on ARM devices.
* **Kernel:** Updated to **v6.12.63** (increased stability and hardware support).
* **Partitioning:** Transitioned from MBR to **GPT** in the ARM64 version.
* **Modern Boot:** Compatibility with UEFI/EDK2 systems (ARM64).

> [!IMPORTANT]
> **UEFI Compatibility (v1.1.1):**
> Paper Linux now supports UEFI, but **does not support Secure Boot yet**. 
> If the system fails to start, disable "Secure Boot" and enable "Legacy Support" or "CSM" (if necessary) in your BIOS settings.

---

## 🖥️ Available Versions
| Version | Architecture | Primary Use Case | Format |
| :--- | :--- | :--- | :--- |
| **Desktop 64** | `x86_64` | Modern PCs and high-performance VMs. | `.iso` |
| **Legacy 32** | `i386` | Legacy hardware and low RAM usage. | `.iso` |
| **Mobile/Dev** | `ARM64` | QEMU Emulation and ARM devices. | `.img` |

---

## 🛠️ How to Test (QEMU Emulation)

### 1. Prerequisites
Ensure you have **QEMU** installed.
* **Windows:** Install QEMU for Windows (w64).
* **Linux:** `sudo apt install qemu-system-x86 qemu-system-arm`

### 2. Execution
* **On Windows:** Run the `testar_paper_linux.bat` file. 
* **On Linux:**
    ```bash
    chmod +x testar_paper.sh
    ./testar_paper.sh
    ```

---

## 📥 Download the build files

* **Download Link (MEGA):** [Click Here](https://mega.nz/file/AFtm2YCR#Wv2PqExmsF4AhStQIjydQ9wm9YX743ydMVPbaLqqxME)
* **Size:** 4.3 GB (Compressed) / 6-15 GB (Extracted)
* **Requirements:** Linux (Debian/Ubuntu and derivatives recommended) or WSL2 (for use on Windows)

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
## 🤝 Contribuições / Contributions
Sinta-se à vontade para abrir Issues ou enviar Pull Requests. / Feel free to open Issues or submit Pull Requests.
