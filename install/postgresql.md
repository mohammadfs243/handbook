Add repositories:

```shell
sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
wget --quiet -O - https://www.postgresql.org/media/keys/ACCC4CF8.asc | sudo apt-key add -
sudo apt-get update
sudo apt-get -y install postgresql
```

After updating `APT`, run appropriate install commands, e.g.
`install postgresql-12` for specific version or
`apt install postgresql-client-12` for only client binaries.

Finally if there's an error related to architecture:

`N: Skipping acquire of configured file 'main/binary-i386/Packages' as repository 'http://apt.postgresql.org/pub/repos/apt focal-pgdg InRelease' doesn't support architecture 'i386'`

edit the _APT_ source to include architecture like:
`deb [arch=amd64] http://apt.postgresql.org/pub/repos/apt focal-pgdg main`
