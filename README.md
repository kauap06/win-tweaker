# OptimizerByKeka

## Visão Geral

Software de ajustes e automação para Windows que reúne scripts em **Python** e **PowerShell** para otimizar desempenho, remover bloatwares e facilitar tarefas avançadas do sistema. O projeto inclui também um executável pronto para uso.

## Funcionalidades Principais

### Automação de Executáveis (`apps.py`)

As funções abaixo executam utilitários localizados em `C:\\tweaker\\Programas\\` com privilégios de administrador:

| Função                    | Executável                  | Objetivo                                    |
| ------------------------- | --------------------------- | ------------------------------------------- |
| `execute_autoruns()`      | `AutoRuns.exe`              | Gerenciar programas iniciados com o sistema |
| `execute_msi()`           | `MSI Util V3.exe`           | Ajustes de placas‑mãe MSI                   |
| `execute_pwrset()`        | `PowerSettingsExplorer.exe` | Ajustar planos de energia ocultos           |
| `execute_temp()`          | `Temp Cleaner.exe`          | Limpar arquivos temporários                 |
| `execute_unpark()`        | `unparkcpu.exe`             | Liberar núcleos “adormecidos” do CPU        |
| `execute_uwt4()`          | `uwt4.exe`                  | Aplicar tweaks do Ultimate Windows Tweaker  |
| `execute_deviceCleanup()` | `DeviceCleanup.exe`         | Remover drivers órfãos                      |
| `execute_wub()`           | `Wub.exe`                   | Habilitar/Desabilitar o Windows Update      |
| `execute_dism()`          | `Dism++x64.exe`             | Manutenção de imagens e sistema             |

> Todas essas funções chamam o helper `execute_exe_as_admin(exe_path)` que encapsula a execução elevada via *PowerShell*.

### Interface Gráfica (`main.py`)

- Verifica/move automaticamente a pasta **tweaker** para `C:\`.
- Carrega a interface em **CustomTkinter** com ícones do diretório interno.
- Exibe mensagens de status usando a API nativa `MessageBoxW`.

### Funções Utilitárias (`funcoes.py`)

- **Abertura de links** do autor (GitHub, Instagram, Pix QR‑Code).
- **Notificações nativas** (`show_notification`, `show_message`).
- **Execução de scripts** e `.reg` com privilégios de administrador (`run_script_as_admin`).

## Uso Rápido

```powershell
# Executar interface Python
python tweaker\main.py

# Debloat do Windows (exemplo)
powershell -ExecutionPolicy Bypass -File tweaker\Debloat\Windows10DebloaterGUI.ps1
```

## Contribuindo

Pull requests são bem‑vindos! Abra uma *issue* primeiro para discutir mudanças significativas.

