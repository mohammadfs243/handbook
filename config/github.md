Create SSH key pairs:

`ssh-keygen -t ed25519 -C "your_email@example.com"`

And change file path to something like `/home/mohammad/.ssh/github_<name>` to
prevent further conflicts.

Adding SSH key to the ssh-agent:

```shell
eval "$(ssh-agent -s)"
```

Add SSH private key to the ssh-agent:

`ssh-add ~/.ssh/github_<name>`

Finally, add the SSH key to the GitHub account.

To workaround the proxy edit `~/.ssh/config` to include:

```
Host github.com
  Hostname ssh.github.com
  Port 443
```

Run `ssh -T git@github.com` to verify it is working.
