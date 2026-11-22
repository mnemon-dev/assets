# mnemon-dev/assets

Public visual-evidence asset repository for Pull Requests and Issues across Mnemon-series projects (such as `dsh-mnemon`), keeping primary code repositories free of binary review bloat.

> **Maintainer & Automation Use Only / 维护者与自动化流程专用**
> External contributors do **not** need access to this repository — attach screenshots or short clips directly in GitHub Pull Request descriptions using GitHub's built-in drag-and-drop attachments.
> 外部贡献者**无需**向本仓库提交文件，直接在 GitHub PR 描述中拖拽上传截图或短视频附件即可。

## Directory Layout / 目录结构

```text
<project>/
  pr/
    <slug>/
      before.png
      after.png
  issues/
    <issue-id>/
      repro.png
```

- `<project>`: target repository name (for example, `dsh-mnemon`).
- `<slug>`: lowercase ASCII identifier for the Pull Request or branch (for example, `pr-722-locale`).
- `<file>`: descriptive ASCII filename (for example, `before-settings.png`, `after-settings.png`, `ja-sidebar.png`).

## Referencing Assets / 引用方式

Always pin links to the full 40-character commit SHA rather than `main`, so historical Pull Request descriptions never break:

```markdown
![after settings](https://raw.githubusercontent.com/mnemon-dev/assets/<40-char-sha>/dsh-mnemon/pr/<slug>/<file>)
```

From `dsh-mnemon`, maintainers and automated workflows can upload and generate pinned Markdown snippets in one command:

```bash
pnpm run pr:evidence -- --slug <slug> /path/to/before.png /path/to/after.png
```

## Content & Security Rules / 内容与安全规范

- **Synthetic or redacted data only**: capture WebUI screenshots from isolated synthetic fixtures (for example `pnpm run e2e:serve`). Never upload API keys, credentials, personal user paths, private memory, or real customer data.
- **Supported formats & sizing**: prefer `.png` or `.webp` for screenshots (target under 10 MiB per image) and `.mp4` or `.webm` for short recordings (under 25 MiB).
- **Before/after clarity**: for WebUI changes, include clear before/after pairs or key state views (for example light/dark theme or switched locales) at a consistent viewport.
