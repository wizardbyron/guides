# Git

## Alias

```shell
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.ap "add -p"
```

## Submodule

更新 Submodule:

```shell
git submodule update --remote
```

## tag

添加本地 tag:

```shell
git tag -a v1.2 9fceb02 -m "my tag"
```

添加远程 tag:

```shell
git push --tags
```

删除本地 tag:

```shell
git tag -d tag-name
```

删除远程 tag:

```shell
git push origin :refs/tags/tag-name
```
