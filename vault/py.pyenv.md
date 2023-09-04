---
id: dkub151sib74b2ujlg61d8b
title: pyenv
desc: ''
updated: 1687485023962
created: 1687444746643
---
pyenv is virtual envinronment version management for Python (virtual env) (windmill)
- pyenv intercepts Python commands using shim executables injected into your PATH, determines which Python version has been specified by your application, and passes your commands along to the correct Python installation.
- Shims are lightweight executables that simply pass your command along to pyenv.
- https://pycon.switowski.com/02-packages/pyenv/
- https://github.com/pyenv/pyenv#installation

## WSL Install
``` bash
curl https://pyenv.run | bash
## setup shell env for pyenv. Using .bashrc
echo 'export PYENV_ROOT="$HOME/.pyenv"' >> ~/.bashrc
echo 'command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(pyenv init -)"' >> ~/.bashrc
```
### Install Error on bash
/mnt/c/Users/tarat/.pyenv/pyenv-win/bin/pyenv: 3: cygpath: not found
/mnt/c/Users/tarat/.pyenv/pyenv-win/bin/pyenv: 3: exec: cmd: not found

Working with:
``` bash
export PYENV_ROOT="$HOME/.pyenv"
export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init --path)"
```
ref: https://stackoverflow.com/questions/67473902/pyenv-no-longer-sets-paths-correctly-when-activating-virtual-environments/67779866#67779866