```shell
python3 -m pip install --user pipx
python3 -m pipx ensurepath
```

Run `pipx completions` to get appropriate script for different shells, e.g. in
bash add code below to the end of `.bashrc` or similar:

```shell
eval "$(register-python-argcomplete pipx)"
```
