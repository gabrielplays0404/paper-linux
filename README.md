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
- **Suporte ARM64:** Agora o Paper Linux pode ser emulado ou rodar em dispositivos ARM.
- **Kernel:** Atualizado para **v6.12.63** (maior estabilidade e suporte a hardware).
- **Particionamento:** Transição de MBR para **GPT** na versão ARM64.
- **Boot Moderno:** Compatibilidade com sistemas UEFI/EDK2 (ARM64).

> [!IMPORTANT]
> **Compatibilidade UEFI (v1.1.1):**
> O Paper Linux agora suporta UEFI, mas **não possui suporte a Secure Boot ainda**. 
> Se o sistema não iniciar, desative o "Secure Boot" e habilite o "Legacy Support" ou "CSM" (se necessário) nas configurações da sua BIOS.

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
