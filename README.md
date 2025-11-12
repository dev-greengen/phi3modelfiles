# Documenti Essenziali Watcher (Windows Ready)

This folder contains everything required to run the unified document watcher on a Windows workstation. The program monitors the sub‑directories under `documenti essenziali/` and automatically processes images dropped there.

## Prerequisites

1. **Python 3.10 (64‑bit)**  
   Install from the Microsoft Store or run:
   ```
   powershell -Command "Invoke-WebRequest -Uri https://www.python.org/ftp/python/3.10.11/python-3.10.11-amd64.exe -OutFile $env:TEMP\python310_x64.exe"
   %TEMP%\python310_x64.exe /quiet InstallAllUsers=0 PrependPath=1 Include_test=0
   ```

2. **Visual Studio Build Tools (Desktop development with C++)** – required for `llama-cpp-python`:  
   ```
   powershell -Command "Invoke-WebRequest -Uri https://aka.ms/vs/17/release/vs_BuildTools.exe -OutFile $env:TEMP\vs_buildtools.exe"
   %TEMP%\vs_buildtools.exe --add Microsoft.VisualStudio.Workload.VCTools --includeRecommended --passive --norestart
   ```
   Reboot after the installation completes.

3. **Optional (for notifications & RAM monitoring)**  
   - `plyer` and `psutil` are included in the requirements list.
   - `win10toast` is optional; if it causes issues, uninstall it after setup.

4. **Phi-3 model files**  
   Already included under `documenti essenziali/phi3_model_files/`. No extra download required.

## Setup

```powershell
cd path\to\project\v8
python -m venv .venv
.\.venv\Scripts\activate
python -m pip install --upgrade pip
pip install -r requirements_folder_watch.txt psutil plyer win10toast
```

If `win10toast` gives errors, remove it with `pip uninstall win10toast`.

## Run the Watcher

```powershell
cd path\to\project\v8
.\.venv\Scripts\activate
python controller.py
```

Leave the window open. Drop images into the appropriate subfolder (e.g. `Carta d'identita\fronte\`). The watcher outputs:

- `<filename>_result.json`
- `<filename>_raw.txt`

Notifications appear on Windows, and the watcher stops automatically if RAM usage reaches 90%.

Use `Ctrl+C` to stop the watcher manually.

