# Ciencia de Redes

## Instalación de Python

> **¿Ya tenés Python instalado?** Si ya tenés Python 3.x funcionando, podés saltar esta sección e ir directo a [Preparar el proyecto](#preparar-el-proyecto).

Usaremos Python 3.13+ (cualquier 3.x reciente funciona).

### Windows
1) Descargá el instalador desde `https://www.python.org/downloads/` (última 3.x)
2) Durante la instalación, marcá "Add Python to PATH" y asegurá incluir `pip`
3) Verificá en PowerShell:
```powershell
python --version
pip --version
# Alternativa con el lanzador oficial
py -V
py -m pip --version
```
O en CMD:
```cmd
python --version
pip --version
# Alternativa con el lanzador oficial
py -V
py -m pip --version
```
4) Si `python` no funciona pero `py` sí, usá el lanzador:
```powershell
py -m pip install --upgrade pip
```
```cmd
py -m pip install --upgrade pip
```

### macOS
Opción A (recomendada) con Homebrew:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install python@3.13
python3 --version
pip3 --version
```
Opción B: instalador oficial `https://www.python.org/downloads/macos/`
```bash
python3 --version
pip3 --version
```
Si `python3` no aparece, corré `brew doctor` y seguí las sugerencias, o reiniciá la terminal.

### Linux (Ubuntu/Debian)
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install -y python3 python3-venv python3-pip
python3 --version
pip3 --version
```
Versión más nueva (opcional, Ubuntu):
```bash
sudo apt install -y software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt update
sudo apt install -y python3.13 python3.13-venv python3.13-distutils
python3.13 --version
```
Consejo: en Linux/macOS usá `python3`/`pip3` y en Windows `python` o `py`.

---

## Preparar el proyecto

### Instalar Git
- Windows/macOS: `https://git-scm.com`
- Linux: `sudo apt install git -y`

### Instalar Visual Studio Code

#### Windows
1) Descargá el instalador desde `https://code.visualstudio.com/Download`
2) Durante la instalación, marcá la opción para agregar VS Code al PATH (si aparece)
3) Verificá en PowerShell o CMD:
```powershell
code -v
```

#### macOS
Opción A (Homebrew):
```bash
brew install --cask visual-studio-code
```
Opción B: descargá el `.zip`/`.dmg` desde `https://code.visualstudio.com/Download`

Habilitar el comando `code` en la terminal (si no funciona):
- Abrí VS Code → `Cmd+Shift+P` → buscá "Shell Command: Install 'code' command in PATH"
- Verificá:
```bash
code -v
```

#### Linux (Ubuntu/Debian)
Opción A (Snap, simple):
```bash
sudo snap install code --classic
code -v
```
Opción B (APT oficial de Microsoft):
```bash
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor | sudo tee /usr/share/keyrings/packages.microsoft.gpg > /dev/null
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
sudo apt update
sudo apt install -y code
code -v
```

### Clonar el repositorio
```bash
git clone https://github.com/andrestobelem/networkscience.git
cd networkscience
```

### Crear y activar el entorno virtual
- Windows (PowerShell):
```powershell
python -m venv venv
.\venv\Scripts\activate
```
- Windows (CMD):
```cmd
python -m venv venv
venv\Scripts\activate.bat
```
- macOS/Linux:
```bash
python3 -m venv venv
source venv/bin/activate
```

### Instalar dependencias
```bash
pip install --upgrade pip
pip install -r requirements.txt
```

---

## Abrir en VS Code (recomendado)

1. Abrir el proyecto
```bash
code .
```
2. Seleccionar el intérprete de Python
- `Ctrl+Shift+P` (Windows/Linux) o `Cmd+Shift+P` (macOS)
- Buscar "Python: Select Interpreter"
- Elegir el intérprete del entorno virtual:
  - macOS/Linux: `./venv/bin/python`
  - Windows: `./venv/Scripts/python.exe`

3. Extensiones recomendadas
- Python (Microsoft)
- Jupyter (Microsoft)
- GitHub Copilot
- GitHub Copilot Chat
- Language Pack Spanish
- Black Formatter
---
