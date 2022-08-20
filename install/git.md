First add the PPA repository:

`add-apt-repository ppa:git-core/ppa`

then do:

```shell
apt update
apt install git
```

> ```shell
> hint: Using 'master' as the name for the initial branch. This default branch name
> hint: is subject to change. To configure the initial branch name to use in all
> hint: of your new repositories, which will suppress this warning, call:
> hint:
> hint:   git config --global init.defaultBranch <name>
> hint:
> hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
> hint: 'development'. The just-created branch can be renamed via this command:
> hint:
> hint:   git branch -m <name>
> ```

So run this:

`git config --global init.defaultBranch main`

To identify:

```shell
git config --global user.name "Mohammad FS"
git config --global user.email "mohammad.fs243@gmail.com"
```
