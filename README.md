# ss-privacy

乐谱学伴儿（ScoreStudio）iOS / iPadOS 应用的**隐私政策与支持页**，用于 App Store Connect。

## 已在线（GitHub Pages）

| 页面 | 网址 | Connect 里填在哪 |
|---|---|---|
| 中文支持页 | `https://caiyc-xd.github.io/ss-privacy/` | 中文区 **Support URL** |
| 中文隐私政策 | `https://caiyc-xd.github.io/ss-privacy/privacy.html` | 中文区 **Privacy Policy URL** |
| English support | `https://caiyc-xd.github.io/ss-privacy/support-en.html` | English (U.S.) **Support URL** |
| English privacy policy | `https://caiyc-xd.github.io/ss-privacy/privacy-en.html` | English (U.S.) **Privacy Policy URL** |

联系方式：codelint@foxmail.com ｜ 政策生效日期：2026-09-25

> **Pages 源分支是 `gh-pages`**（推送该分支时 GitHub 自动开启，实测四个页面均返回 200）。
> 若想以后只维护一个分支，可在仓库 Settings → Pages 里把 Source 改成 `main` + `/ (root)`；
> 不改也没问题，按下面的方式同时更新两个分支即可。

## 内容从哪里来

页面由主工程仓库 `ScoreStudio` 的 `Tools/Pages/build.py` 生成（正文来源
`AppStore/Privacy-Policy.md` 与 `AppStore/Privacy-Policy-en.md`）。**不要直接手改本仓库的 HTML**：
改主工程的源 markdown → 重新生成 → 拷过来，避免两处不一致。

```bash
# 1) 在主工程 ScoreStudio 仓库里重新生成
python3 Tools/Pages/build.py

# 2) 拷到本仓库并推送到两个分支（main 存源码，gh-pages 才是当前发布分支）
cp docs/privacy.html docs/privacy-en.html docs/index.html docs/support-en.html docs/style.css docs/.nojekyll <本仓库>/
cd <本仓库> && git add -A && git commit -m "更新隐私政策" && git push origin main
git checkout gh-pages && git checkout main -- . && git commit -m "更新隐私政策" && git push origin gh-pages && git checkout main
```

## 内容说明

- 中英各 13 节：不收集数据的具体范围、系统权限、网络访问、乐谱与导出文件的处理、
  本机偏好设置、随包第三方内容与许可、无第三方 SDK / 广告 / 内购、儿童隐私、
  GDPR/CCPA 口径的你的权利、数据保留与跨境传输、政策变更、联系方式与回复时限。
- 页面自包含：`style.css`（深色模式自适应）+ `.nojekyll`（跳过 Jekyll 处理），无外部依赖。
