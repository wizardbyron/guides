# Git

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
