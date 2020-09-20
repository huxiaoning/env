```shell
$ git update-index --skip-worktree /file/to/path
$ git update-index --no-skip-worktree /file/to/path
# 查找所有忽略的文件
$ git ls-files -v | grep ^S

git update-index --assume-unchanged /file/to/path
git update-index --no-assume-unchanged
git ls-files -v | grep ^h

```

