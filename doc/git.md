# git 操作问题记录

---

#### git push 需要一直输入用户名？

- 在 git 上创建 Personal access tokens (个人访问令牌)，用该用户和密码进行登录
- 或者在用户目录找到.gitconfig 文件直接修改

#### git merge 合并分支出错了怎么办？
- 代码回滚: git reset --hard [commitId]
