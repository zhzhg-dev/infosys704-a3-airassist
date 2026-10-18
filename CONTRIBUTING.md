# 小组修改流程

先阅读 [README](README.md)。每次修改说明它改善了什么，以及对应的 A3 评分项；不要仅为了增加功能而扩大范围。

## 代码与 Markdown

1. 先同步 `main`，为自己的修改建立分支，例如 `fix/refund-form` 或 `docs/pitch-script`。
2. 一次处理一个明确问题，尽量避免同时重写多人正在修改的文件。
3. 提交前检查 Git 文件列表，确保没有 `.env`、API key、本机数据库、私人信息或无关课程文件。
4. 创建 pull request，写明修改内容、涉及的页面/流程、实际做过的检查，并请另一位组员审阅后合并。

GitHub Desktop 可以完成克隆、分支、提交和 push；也可以在 GitHub 网页编辑 Markdown。请保留 `app/` 的位置，这样已有相对链接仍然可用。

涉及软件行为的修改，在 `app` 目录运行现有检查：

```sh
python3 -B -m unittest discover -s tests -v
node tests/frontend-state.cjs
```

第二条需要 Node.js。界面布局改动还要在浏览器检查实际页面和手机宽度；不能只根据自动测试判断设计完成。只修改小段说明时，核对内容和链接即可，不需要无关的软件测试。

## 测试证据与最终导出

日常开发改 `app/`，**不要修改既有 PASS 结果或改写 OpenCode/SAP 来源记录**。

提交前由一位组员统一核查最新源码，重新运行与改动相关的检查，并为新的交付版本生成独立 ZIP 和结果。SAP key 在每位组员自己的电脑本地配置；课堂临时账号不能用于项目。课程若规定特定的 OpenCode App 导出操作，按老师的操作要求核对后再提交 Canvas。

当前仓库已有 Vercel 公开课程演示，部署入口、范围、环境变量和重新部署步骤见 [README 的部署说明](README.md#deploy-to-vercel)。GitHub 自动发布尚未连接，代码提交不会自动更新线上版本。演示只使用合成数据；SAP 和 Blob 密钥只通过环境变量配置，不要将密钥或真实个人记录暴露到公网。
