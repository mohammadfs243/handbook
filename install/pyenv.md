`git clone https://github.com/pyenv/pyenv.git ~/.pyenv`

Optionally do this (No worries if it fails):

`cd ~/.pyenv && src/configure && make -C src`

For more details of the instructions below, read on.

- Define environment variable `PYENV_ROOT` to point to the path where Pyenv will
  store its data. `$HOME/.pyenv` is the default. If you installed Pyenv via Git
  checkout, we recommend to set it to the same location as where you cloned it.
- Add the pyenv executable to your `PATH` if it's not already there.
- run `eval "$(pyenv init -)"` to install pyenv into your shell as a shell
  function, enable shims and autocompletion.
  - You may run eval "$(pyenv init --path)" instead to just enable shims,
    without shell integration

For bash add these to the end of `.bashrc` and `.profile` if exists:

```shell
export PYENV_ROOT="$HOME/.pyenv"
command -v pyenv >/dev/null || export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init -)"
```

To upgrade _Pyenv_ if installed using _Git_ checkout simply do:

```shell
cd $(pyenv root)
git pull
```
