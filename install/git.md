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

Add this to `.bashrc` or similar to show current branch in the prompt:

```shell
parse_git_branch() {
 git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
```

Then change default prompt to include it, e.g.:

```shell
if [ "$color_prompt" = yes ]; then
 PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[01;31m\]$(parse_git_branch)\[\033[00m\]\$ '
else
 PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w$(parse_git_branch)\$ '
fi
```

Here are some useful aliases to configure:

```shell
git config --global alias.s 'status --short'
git config --global alias.graph 'log --all --decorate --oneline --graph'
git config --global alias.unstage 'reset HEAD --'
```
