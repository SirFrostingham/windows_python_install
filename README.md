# Python install on Windows
Best, most flexible way to install Python on a Windows system, whether you are a software engineer, python script experimenter, or a newbie! This is the most optimal way I've found to manage Python on Windows.

# Why put this out there?
- Because the native Windows Python install is dumb and tries to guide you to use the Windows App Store
- This gives you the most flexibility of selecting your Python version, installing multiple versions, and using the version you want
- Once Pyenv is installed...
  - See what python versions are install: `pyenv versions`
  - List new versions: `pyenv install --list`
  - Set your global python version (based off of what is installed on you system): `pyenv global 3.11.9`
  - Run to see help: `pyenv`

# Installing Python on Windows

- Install Chocolatey (if not already installed):
  - Open an elevated Command Prompt (Run as Administrator).
  - Run: `@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"`

- Install pyenv via Chocolatey:
  - Run: `choco install pyenv-win -y`
 
- Update pyenv cache after install, especially if you already had pyenv installed
  - Run: `pyenv update`

- Disable Microsoft Store Python alias:
  - Windows > Open Settings > Apps > Apps & features > App execution aliases.
  - Find "Python" and toggle it off to disable `python.exe` and `python3.exe` aliases.
  - If you don't do this, trying to run Python will keep pointing you to the Microsoft App Store, which is very dumb.

- Install Python using pyenv:
  - List available Python versions: `pyenv install --list`
  - Install a specific version (e.g., 3.11.9): `pyenv install 3.11.9`

- Set global Python version:
  - Run: `pyenv global 3.11.9`

- Update Environment Variables:
  - Open System Properties: `sysdm.cpl`
  - Go to Advanced tab > Environment Variables.
  - In User variables, edit or create `Path`.
  - Add:
    - `%USERPROFILE%\.pyenv\pyenv-win\bin`
    - `%USERPROFILE%\.pyenv\pyenv-win\shims`

- Verify installation:
  - Open a new Command Prompt.
  - Run: `python --version` to confirm the set Python version.
