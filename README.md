# ss-privacy

乐谱学伴儿（ScoreStudio）iOS / iPadOS 应用的**隐私政策与支持页**，用于 App Store Connect：

| 页面 | 文件 | 用途 |
|---|---|---|
| 中文隐私政策 | `privacy.html` | Connect 中文区 Privacy Policy URL |
| English privacy policy | `privacy-en.html` | Connect English (U.S.) Privacy Policy URL |
| 中文支持页 | `index.html` | Connect 中文区 Support URL（站点根） |
| English support page | `support-en.html` | Connect English (U.S.) Support URL |

联系方式：codelint@foxmail.com ｜ 政策生效日期：2026-09-25

## 内容从哪里来

页面由主工程仓库 `ScoreStudio` 的 `Tools/Pages/build.py` 生成（正文来源
`AppStore/Privacy-Policy.md` 与 `AppStore/Privacy-Policy-en.md`），生成后拷到本仓库发布。
**不要直接手改本仓库的 HTML**：改主工程里的源 markdown，重新生成后再拷过来，避免两处不一致。

```bash
# 在主工程 ScoreStudio 仓库里：
python3 Tools/Pages/build.py
cp docs/privacy.html docs/privacy-en.html docs/index.html docs/support-en.html docs/style.css docs/.nojekyll <本仓库>/
```

## 部署（GitHub Pages）

本仓库 `main` 分支根目录即站点；在 GitHub 仓库 **Settings → Pages** 选择
`Deploy from a branch` → `main` → `/ (root)` 即可，得到：

- 支持（中文）：`https://caiyc-xd.github.io/ss-privacy/`
- Support (EN)：`https://caiyc-xd.github.io/ss-privacy/support-en.html`
- 隐私政策（中文）：`https://caiyc-xd.github.io/ss-privacy/privacy.html`
- Privacy (EN)：`https://caiyc-xd.github.io/ss-privacy/privacy-en.html`
