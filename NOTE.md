# 工程维护笔记

## 代理配置

Windows 下 `git push` 失败（`Failed to connect to github.com port 443`）：
- 原因：代理工具配置了系统代理，浏览器能用，但 Git 不会自动读取
- 已配全局代理：`git config --global http.proxy http://127.0.0.1:12334`
- 查看：`git config --global --get http.proxy`
- 如果换代理端口，同步更新即可

## 远程仓库

| 远程名 | URL | 权限 |
|--------|-----|------|
| origin | https://github.com/jaxiangjie/ai-berkshire.git | 读写（自己的 fork） |
| upstream | https://github.com/xbtlin/ai-berkshire.git | 只读（原作者） |

## 同步原作者更新

```bash
git pull --rebase upstream main
git push origin main
```

## 注意事项

- 所有报告按公司名建文件夹，放在 `reports/` 下
- 写新报告前确认在 `main` 分支上（或在 worktree 中工作）
- 推送前先 `git pull --rebase upstream main`
- CLAUDE.md 中有完整的项目结构和命名规范
