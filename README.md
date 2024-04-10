# Binary distributions for Python via pyenv on Linux

[pyenv](https://github.com/pyenv/pyenv) is good at managing multiple versions of Python on Linux. However, everytime you install a new version of Python, you have to compile it from source. So I created this repository to provide binary distributions for Python via pyenv on Linux.

The idea behind how this repository works is, while most of the Linux distributions have a official Docker image, they share same ABI, linked libraries, etc. So the binary compiled on a clean, minimal Docker image should work on the same version of other OS.

## How to use
The project assumes you use a global directory, `/usr/local/share/pyenv`, as the `PYENV_ROOT` directory. Which means you must have `root` access to install these binary distributions.

You can install pyenv with overwrited `PYENV_ROOT`:
```bash
curl https://pyenv.run | PYENV_ROOT=/usr/local/share/pyenv bash
```

Then find the binary distribution in [GitHub Release](https://github.com/baobao1270/pyenv-builds/releases). Download the binary distribution matches your OS.

Unarchive it:
```bash
tar -xf python-*.tar.zst
mv <version> /usr/local/share/pyenv/versions/
```

Then you can try run the downloaded python:
```bash
/usr/local/share/pyenv/versions/<version>/bin/python --version
```

You can also check if the binary distribution is correctly installed by running:
```bash
pyenv versions
```

## License?

These are few misc scripts. I don't think it needs a license. You can do whatever you want with it.
