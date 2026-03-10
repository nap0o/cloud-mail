# 🛡️ 安全审计与透明度报告

[English](README.md) | 中文

![安全评级](https://img.shields.io/badge/安全评级-D-red?style=for-the-badge)

> [!IMPORTANT]
> 本报告由 **GitHub Actions** 自动生成。为确保数据主权的绝对透明度，所有核心模块的安全扫描结果均实时公开。

| 📅 审计时间 | 📝 运行 ID | 🛠️ 环境 |
| :--- | :--- | :--- |
| `2026-03-10 04:45:15 UTC` | [#22887476553](https://github.com/nap0o/cloud-mail/actions/runs/22887476553) | `GitHub CI/CD` |

---

## 📉 实时安全仪表盘

| 工具 | 状态 | 发现项 |
| :--- | :--- | :--- |
| **Credential Leak (Gitleaks)** | ![Fail](https://img.shields.io/badge/Status-FAIL-red?style=for-the-badge) | `2` 泄露 |
| **Dependency Scan (Snyk)** | ![Warning](https://img.shields.io/badge/Status-NOTICE-orange?style=for-the-badge) | `2` 漏洞 |
| **Static Analysis (CodeQL)** | ![Warning](https://img.shields.io/badge/Status-NOTICE-orange?style=for-the-badge) | `34` 告警 |
| **Container Scan (Trivy)** | ![Pass](https://img.shields.io/badge/Status-PASS-success?style=for-the-badge) | `0` 发现项 |

---

## 🔍 扫描覆盖范围

| 模块 | 已审计文件 | 覆盖率 |
| :--- | :---: | :---: |
| **GitHub Actions** | `2` | ✨ **100%** |
| **JavaScript (Frontend)** | `189` | ✨ **100%** |
| **TypeScript (Backend)** | `1` | ✨ **100%** |

---

## 🔍 详细发现项

### 🔑 凭据泄露检查 (Gitleaks)
`检测代码历史记录中硬编码的 API 密钥、密码或其他敏感令牌。` `扫描范围：所有代码更改和 Git 历史记录 (Gitleaks 全量扫描)`

| 规则 ID | 位置 | 描述 |
| :--- | :--- | :--- |
| `generic-api-key` | `mail-worker/wrangler-test.toml` | generic-api-key has detected secret for file mail-worker/wrangler-test.toml at commit 3264f0d25a072fa7dc1e17eeda86d48f97021dd4. |
| `generic-api-key` | `mail-worker/wrangler-dev.toml` | generic-api-key has detected secret for file mail-worker/wrangler-dev.toml at commit 82905173ef77266122500b09c56be356f035e8e0. |

### 🛡️ 容器配置安全 (Trivy)
`检测 Dockerfile 和容器配置中的安全风险与最佳实践。`

✅ **安全**：未发现容器配置缺陷。

### 📦 第三方依赖
| 软件包 | 严重程度 | 描述 | 修复方案 |
| :--- | :---: | :--- | :--- |
| `undici@5.29.0` | 🟡 medium | [Allocation of Resources Without Limits or Throttling](undefined) | Upgrade to `6.23.0, 7.18.2` |
| `wrangler@4.20.0` | 🟠 high | [Improper Input Validation](undefined) | Upgrade to `3.114.17, 4.59.1` |

### 💻 代码质量与安全 (CodeQL)
#### 摘要
- **已检查规则**: `227`
- **告警总数**: `34`

| 规则 ID | 级别 | 位置 | 描述 |
| :--- | :---: | :--- | :--- |
| [actions/missing-workflow-permissions](https://codeql.github.com/codeql-query-help/github-actions/actions-missing-workflow-permissions/) | 🟠 warning | `.github/workflows/deploy-cloudflare.yml:13` | Actions job or workflow does not limit the permissions of the GITHUB_TOKEN. Consider setting an explicit permissions block, using the following as a minimal starting point: {{contents: read}} |
| [actions/unpinned-tag](https://codeql.github.com/codeql-query-help/github-actions/actions-unpinned-tag/) | 🟠 warning | `.github/workflows/deploy-cloudflare.yml:41` | Unpinned 3rd party Action '🚀 Deploy cloud-mail to Cloudflare Workers' step [Uses Step](1) uses 'pnpm/action-setup' with ref 'v4.1.0', not a pinned commit hash |
| [actions/unpinned-tag](https://codeql.github.com/codeql-query-help/github-actions/actions-unpinned-tag/) | 🟠 warning | `.github/workflows/deploy-cloudflare.yml:247` | Unpinned 3rd party Action '🚀 Deploy cloud-mail to Cloudflare Workers' step [Uses Step](1) uses 'GitRML/delete-workflow-runs' with ref 'main', not a pinned commit hash |
| [js/incomplete-multi-character-sanitization](https://codeql.github.com/codeql-query-help/javascript/js-incomplete-multi-character-sanitization/) | 🟠 warning | `mail-vue/src/components/email-scroll/index.vue:548` | This string may still contain [<iframe](1), which may cause an HTML element injection vulnerability. |
| [js/user-controlled-bypass](https://codeql.github.com/codeql-query-help/javascript/js-user-controlled-bypass/) | 🟠 warning | `mail-vue/src/views/login/index.vue:267` | This condition guards a sensitive [action](1), but a [user-provided value](2) controls it. |
| [js/unused-local-variable](https://codeql.github.com/codeql-query-help/javascript/js-unused-local-variable/) | 🟠 warning | `mail-worker/src/const/entity-const.js:1` | Unused import verifyRecordService. |
| [js/unused-local-variable](https://codeql.github.com/codeql-query-help/javascript/js-unused-local-variable/) | 🟠 warning | `mail-worker/src/entity/role-perm.js:1` | Unused import text. |
| [js/unused-local-variable](https://codeql.github.com/codeql-query-help/javascript/js-unused-local-variable/) | 🟠 warning | `mail-worker/src/service/account-service.js:250` | Unused variable a. |
| [js/unused-local-variable](https://codeql.github.com/codeql-query-help/javascript/js-unused-local-variable/) | 🟠 warning | `mail-worker/src/service/email-service.js:23` | Unused import telegramService. |
| [js/unused-local-variable](https://codeql.github.com/codeql-query-help/javascript/js-unused-local-variable/) | 🟠 warning | `mail-worker/src/service/telegram-service.js:14` | Unused import verifyUtils. |
| [js/useless-expression](https://codeql.github.com/codeql-query-help/javascript/js-useless-expression/) | 🟠 warning | `mail-vue/src/views/analysis/index.vue:558` | This expression has no effect. |
| [js/trivial-conditional](https://codeql.github.com/codeql-query-help/javascript/js-trivial-conditional/) | 🟠 warning | `mail-worker/src/service/setting-service.js:140` | This use of variable 'background' always evaluates to true. |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-vue/src/utils/icon-utils.js:4` | Avoid automated semicolon insertion (90% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/email/email.js:54` | Avoid automated semicolon insertion (90% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/email/email.js:78` | Avoid automated semicolon insertion (90% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/email/email.js:147` | Avoid automated semicolon insertion (90% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/email/email.js:169` | Avoid automated semicolon insertion (90% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/security/security.js:153` | Avoid automated semicolon insertion (92% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/security/security.js:161` | Avoid automated semicolon insertion (92% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/att-service.js:87` | Avoid automated semicolon insertion (95% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/att-service.js:133` | Avoid automated semicolon insertion (95% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/reg-key-service.js:39` | Avoid automated semicolon insertion (90% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/email-service.js:130` | Avoid automated semicolon insertion (95% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/email-service.js:226` | Avoid automated semicolon insertion (95% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/email-service.js:293` | Avoid automated semicolon insertion (95% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/email-service.js:363` | Avoid automated semicolon insertion (95% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/email-service.js:388` | Avoid automated semicolon insertion (95% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/email-service.js:468` | Avoid automated semicolon insertion (95% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/email-service.js:650` | Avoid automated semicolon insertion (93% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/email-service.js:705` | Avoid automated semicolon insertion (93% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/utils/req-utils.js:41` | Avoid automated semicolon insertion (94% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/utils/jwt-utils.js:82` | Avoid automated semicolon insertion (92% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/user-service.js:49` | Avoid automated semicolon insertion (93% of all statements in [the enclosing function](1) have an explicit semicolon). |
| [js/automatic-semicolon-insertion](https://codeql.github.com/codeql-query-help/javascript/js-automatic-semicolon-insertion/) | 🟠 warning | `mail-worker/src/service/user-service.js:213` | Avoid automated semicolon insertion (97% of all statements in [the enclosing function](1) have an explicit semicolon). |

### 📂 已审计文件列表
<details>
<summary><b>GitHub Actions (2)</b></summary>

| 模块 | 位置 | 状态 |
| :--- | :--- | :--- |
| `deploy-cloudflare.yml` | `.github/workflows/deploy-cloudflare.yml` | ✅ **已审计** |
| `security.yml` | `.github/workflows/security.yml` | ✅ **已审计** |

</details>

<details>
<summary><b>JavaScript (189)</b></summary>

| 模块 | 位置 | 状态 |
| :--- | :--- | :--- |
| `zh_CN.js` | `mail-vue/public/tinymce/langs/zh_CN.js` | ✅ **已审计** |
| `zh_TW.js` | `mail-vue/public/tinymce/langs/zh_TW.js` | ✅ **已审计** |
| `emojiimages.js` | `mail-vue/public/tinymce/plugins/emoticons/js/emojiimages.js` | ✅ **已审计** |
| `emojis.js` | `mail-vue/public/tinymce/plugins/emoticons/js/emojis.js` | ✅ **已审计** |
| `ar.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/ar.js` | ✅ **已审计** |
| `bg_BG.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/bg_BG.js` | ✅ **已审计** |
| `ca.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/ca.js` | ✅ **已审计** |
| `cs.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/cs.js` | ✅ **已审计** |
| `da.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/da.js` | ✅ **已审计** |
| `de.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/de.js` | ✅ **已审计** |
| `el.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/el.js` | ✅ **已审计** |
| `en.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/en.js` | ✅ **已审计** |
| `es.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/es.js` | ✅ **已审计** |
| `eu.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/eu.js` | ✅ **已审计** |
| `fa.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/fa.js` | ✅ **已审计** |
| `fi.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/fi.js` | ✅ **已审计** |
| `fr_FR.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/fr_FR.js` | ✅ **已审计** |
| `he_IL.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/he_IL.js` | ✅ **已审计** |
| `hi.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/hi.js` | ✅ **已审计** |
| `hr.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/hr.js` | ✅ **已审计** |
| `hu_HU.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/hu_HU.js` | ✅ **已审计** |
| `id.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/id.js` | ✅ **已审计** |
| `it.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/it.js` | ✅ **已审计** |
| `ja.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/ja.js` | ✅ **已审计** |
| `kk.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/kk.js` | ✅ **已审计** |
| `ko_KR.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/ko_KR.js` | ✅ **已审计** |
| `ms.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/ms.js` | ✅ **已审计** |
| `nb_NO.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/nb_NO.js` | ✅ **已审计** |
| `nl.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/nl.js` | ✅ **已审计** |
| `pl.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/pl.js` | ✅ **已审计** |
| `pt_BR.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/pt_BR.js` | ✅ **已审计** |
| `pt_PT.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/pt_PT.js` | ✅ **已审计** |
| `ro.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/ro.js` | ✅ **已审计** |
| `ru.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/ru.js` | ✅ **已审计** |
| `sk.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/sk.js` | ✅ **已审计** |
| `sl_SI.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/sl_SI.js` | ✅ **已审计** |
| `sv_SE.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/sv_SE.js` | ✅ **已审计** |
| `th_TH.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/th_TH.js` | ✅ **已审计** |
| `tr.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/tr.js` | ✅ **已审计** |
| `uk.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/uk.js` | ✅ **已审计** |
| `vi.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/vi.js` | ✅ **已审计** |
| `zh_CN.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/zh_CN.js` | ✅ **已审计** |
| `zh_TW.js` | `mail-vue/public/tinymce/plugins/help/js/i18n/keynav/zh_TW.js` | ✅ **已审计** |
| `content.js` | `mail-vue/public/tinymce/skins/content/dark/content.js` | ✅ **已审计** |
| `content.js` | `mail-vue/public/tinymce/skins/content/default/content.js` | ✅ **已审计** |
| `content.js` | `mail-vue/public/tinymce/skins/content/document/content.js` | ✅ **已审计** |
| `content.js` | `mail-vue/public/tinymce/skins/content/tinymce-5-dark/content.js` | ✅ **已审计** |
| `content.js` | `mail-vue/public/tinymce/skins/content/tinymce-5/content.js` | ✅ **已审计** |
| `content.js` | `mail-vue/public/tinymce/skins/content/writer/content.js` | ✅ **已审计** |
| `content.inline.js` | `mail-vue/public/tinymce/skins/ui/oxide-dark/content.inline.js` | ✅ **已审计** |
| `content.js` | `mail-vue/public/tinymce/skins/ui/oxide-dark/content.js` | ✅ **已审计** |
| `skin.js` | `mail-vue/public/tinymce/skins/ui/oxide-dark/skin.js` | ✅ **已审计** |
| `skin.shadowdom.js` | `mail-vue/public/tinymce/skins/ui/oxide-dark/skin.shadowdom.js` | ✅ **已审计** |
| `content.inline.js` | `mail-vue/public/tinymce/skins/ui/oxide/content.inline.js` | ✅ **已审计** |
| `content.js` | `mail-vue/public/tinymce/skins/ui/oxide/content.js` | ✅ **已审计** |
| `skin.js` | `mail-vue/public/tinymce/skins/ui/oxide/skin.js` | ✅ **已审计** |
| `skin.shadowdom.js` | `mail-vue/public/tinymce/skins/ui/oxide/skin.shadowdom.js` | ✅ **已审计** |
| `content.inline.js` | `mail-vue/public/tinymce/skins/ui/tinymce-5-dark/content.inline.js` | ✅ **已审计** |
| `content.js` | `mail-vue/public/tinymce/skins/ui/tinymce-5-dark/content.js` | ✅ **已审计** |
| `skin.js` | `mail-vue/public/tinymce/skins/ui/tinymce-5-dark/skin.js` | ✅ **已审计** |
| `skin.shadowdom.js` | `mail-vue/public/tinymce/skins/ui/tinymce-5-dark/skin.shadowdom.js` | ✅ **已审计** |
| `content.inline.js` | `mail-vue/public/tinymce/skins/ui/tinymce-5/content.inline.js` | ✅ **已审计** |
| `content.js` | `mail-vue/public/tinymce/skins/ui/tinymce-5/content.js` | ✅ **已审计** |
| `skin.js` | `mail-vue/public/tinymce/skins/ui/tinymce-5/skin.js` | ✅ **已审计** |
| `skin.shadowdom.js` | `mail-vue/public/tinymce/skins/ui/tinymce-5/skin.shadowdom.js` | ✅ **已审计** |
| `index.js` | `mail-vue/src/axios/index.js` | ✅ **已审计** |
| `db.js` | `mail-vue/src/db/db.js` | ✅ **已审计** |
| `index.js` | `mail-vue/src/echarts/index.js` | ✅ **已审计** |
| `account-enum.js` | `mail-vue/src/enums/account-enum.js` | ✅ **已审计** |
| `email-enum.js` | `mail-vue/src/enums/email-enum.js` | ✅ **已审计** |
| `setting-enum.js` | `mail-vue/src/enums/setting-enum.js` | ✅ **已审计** |
| `en.js` | `mail-vue/src/i18n/en.js` | ✅ **已审计** |
| `index.js` | `mail-vue/src/i18n/index.js` | ✅ **已审计** |
| `zh.js` | `mail-vue/src/i18n/zh.js` | ✅ **已审计** |
| `index.js` | `mail-vue/src/icons/index.js` | ✅ **已审计** |
| `init.js` | `mail-vue/src/init/init.js` | ✅ **已审计** |
| `main.js` | `mail-vue/src/main.js` | ✅ **已审计** |
| `perm.js` | `mail-vue/src/perm/perm.js` | ✅ **已审计** |
| `account.js` | `mail-vue/src/request/account.js` | ✅ **已审计** |
| `all-email.js` | `mail-vue/src/request/all-email.js` | ✅ **已审计** |
| `analysis.js` | `mail-vue/src/request/analysis.js` | ✅ **已审计** |
| `email.js` | `mail-vue/src/request/email.js` | ✅ **已审计** |
| `login.js` | `mail-vue/src/request/login.js` | ✅ **已审计** |
| `my.js` | `mail-vue/src/request/my.js` | ✅ **已审计** |
| `ouath.js` | `mail-vue/src/request/ouath.js` | ✅ **已审计** |
| `reg-key.js` | `mail-vue/src/request/reg-key.js` | ✅ **已审计** |
| `role.js` | `mail-vue/src/request/role.js` | ✅ **已审计** |
| `setting.js` | `mail-vue/src/request/setting.js` | ✅ **已审计** |
| `star.js` | `mail-vue/src/request/star.js` | ✅ **已审计** |
| `user.js` | `mail-vue/src/request/user.js` | ✅ **已审计** |
| `index.js` | `mail-vue/src/router/index.js` | ✅ **已审计** |
| `account.js` | `mail-vue/src/store/account.js` | ✅ **已审计** |
| `draft.js` | `mail-vue/src/store/draft.js` | ✅ **已审计** |
| `email.js` | `mail-vue/src/store/email.js` | ✅ **已审计** |
| `role.js` | `mail-vue/src/store/role.js` | ✅ **已审计** |
| `send.js` | `mail-vue/src/store/send.js` | ✅ **已审计** |
| `setting.js` | `mail-vue/src/store/setting.js` | ✅ **已审计** |
| `ui.js` | `mail-vue/src/store/ui.js` | ✅ **已审计** |
| `user.js` | `mail-vue/src/store/user.js` | ✅ **已审计** |
| `writer.js` | `mail-vue/src/store/writer.js` | ✅ **已审计** |
| `convert.js` | `mail-vue/src/utils/convert.js` | ✅ **已审计** |
| `day.js` | `mail-vue/src/utils/day.js` | ✅ **已审计** |
| `file-utils.js` | `mail-vue/src/utils/file-utils.js` | ✅ **已审计** |
| `icon-utils.js` | `mail-vue/src/utils/icon-utils.js` | ✅ **已审计** |
| `text.js` | `mail-vue/src/utils/text.js` | ✅ **已审计** |
| `time-utils.js` | `mail-vue/src/utils/time-utils.js` | ✅ **已审计** |
| `verify-utils.js` | `mail-vue/src/utils/verify-utils.js` | ✅ **已审计** |
| `vite.config.js` | `mail-vue/vite.config.js` | ✅ **已审计** |
| `account-api.js` | `mail-worker/src/api/account-api.js` | ✅ **已审计** |
| `all-email-api.js` | `mail-worker/src/api/all-email-api.js` | ✅ **已审计** |
| `analysis-api.js` | `mail-worker/src/api/analysis-api.js` | ✅ **已审计** |
| `email-api.js` | `mail-worker/src/api/email-api.js` | ✅ **已审计** |
| `init-api.js` | `mail-worker/src/api/init-api.js` | ✅ **已审计** |
| `login-api.js` | `mail-worker/src/api/login-api.js` | ✅ **已审计** |
| `my-api.js` | `mail-worker/src/api/my-api.js` | ✅ **已审计** |
| `oauth-api.js` | `mail-worker/src/api/oauth-api.js` | ✅ **已审计** |
| `public-api.js` | `mail-worker/src/api/public-api.js` | ✅ **已审计** |
| `r2-api.js` | `mail-worker/src/api/r2-api.js` | ✅ **已审计** |
| `reg-key-api.js` | `mail-worker/src/api/reg-key-api.js` | ✅ **已审计** |
| `resend-api.js` | `mail-worker/src/api/resend-api.js` | ✅ **已审计** |
| `role-api.js` | `mail-worker/src/api/role-api.js` | ✅ **已审计** |
| `setting-api.js` | `mail-worker/src/api/setting-api.js` | ✅ **已审计** |
| `star-api.js` | `mail-worker/src/api/star-api.js` | ✅ **已审计** |
| `telegram-api.js` | `mail-worker/src/api/telegram-api.js` | ✅ **已审计** |
| `test-api.js` | `mail-worker/src/api/test-api.js` | ✅ **已审计** |
| `user-api.js` | `mail-worker/src/api/user-api.js` | ✅ **已审计** |
| `constant.js` | `mail-worker/src/const/constant.js` | ✅ **已审计** |
| `entity-const.js` | `mail-worker/src/const/entity-const.js` | ✅ **已审计** |
| `kv-const.js` | `mail-worker/src/const/kv-const.js` | ✅ **已审计** |
| `analysis-dao.js` | `mail-worker/src/dao/analysis-dao.js` | ✅ **已审计** |
| `email.js` | `mail-worker/src/email/email.js` | ✅ **已审计** |
| `account.js` | `mail-worker/src/entity/account.js` | ✅ **已审计** |
| `att.js` | `mail-worker/src/entity/att.js` | ✅ **已审计** |
| `email.js` | `mail-worker/src/entity/email.js` | ✅ **已审计** |
| `oauth.js` | `mail-worker/src/entity/oauth.js` | ✅ **已审计** |
| `orm.js` | `mail-worker/src/entity/orm.js` | ✅ **已审计** |
| `perm.js` | `mail-worker/src/entity/perm.js` | ✅ **已审计** |
| `reg-key.js` | `mail-worker/src/entity/reg-key.js` | ✅ **已审计** |
| `role-perm.js` | `mail-worker/src/entity/role-perm.js` | ✅ **已审计** |
| `role.js` | `mail-worker/src/entity/role.js` | ✅ **已审计** |
| `setting.js` | `mail-worker/src/entity/setting.js` | ✅ **已审计** |
| `star.js` | `mail-worker/src/entity/star.js` | ✅ **已审计** |
| `user.js` | `mail-worker/src/entity/user.js` | ✅ **已审计** |
| `verify-record.js` | `mail-worker/src/entity/verify-record.js` | ✅ **已审计** |
| `biz-error.js` | `mail-worker/src/error/biz-error.js` | ✅ **已审计** |
| `hono.js` | `mail-worker/src/hono/hono.js` | ✅ **已审计** |
| `webs.js` | `mail-worker/src/hono/webs.js` | ✅ **已审计** |
| `en.js` | `mail-worker/src/i18n/en.js` | ✅ **已审计** |
| `i18n.js` | `mail-worker/src/i18n/i18n.js` | ✅ **已审计** |
| `zh.js` | `mail-worker/src/i18n/zh.js` | ✅ **已审计** |
| `index.js` | `mail-worker/src/index.js` | ✅ **已审计** |
| `init.js` | `mail-worker/src/init/init.js` | ✅ **已审计** |
| `result.js` | `mail-worker/src/model/result.js` | ✅ **已审计** |
| `security.js` | `mail-worker/src/security/security.js` | ✅ **已审计** |
| `user-context.js` | `mail-worker/src/security/user-context.js` | ✅ **已审计** |
| `account-service.js` | `mail-worker/src/service/account-service.js` | ✅ **已审计** |
| `analysis-service.js` | `mail-worker/src/service/analysis-service.js` | ✅ **已审计** |
| `att-service.js` | `mail-worker/src/service/att-service.js` | ✅ **已审计** |
| `email-service.js` | `mail-worker/src/service/email-service.js` | ✅ **已审计** |
| `kv-obj-service.js` | `mail-worker/src/service/kv-obj-service.js` | ✅ **已审计** |
| `login-service.js` | `mail-worker/src/service/login-service.js` | ✅ **已审计** |
| `oauth-service.js` | `mail-worker/src/service/oauth-service.js` | ✅ **已审计** |
| `perm-service.js` | `mail-worker/src/service/perm-service.js` | ✅ **已审计** |
| `public-service.js` | `mail-worker/src/service/public-service.js` | ✅ **已审计** |
| `r2-service.js` | `mail-worker/src/service/r2-service.js` | ✅ **已审计** |
| `reg-key-service.js` | `mail-worker/src/service/reg-key-service.js` | ✅ **已审计** |
| `resend-service.js` | `mail-worker/src/service/resend-service.js` | ✅ **已审计** |
| `role-service.js` | `mail-worker/src/service/role-service.js` | ✅ **已审计** |
| `s3-service.js` | `mail-worker/src/service/s3-service.js` | ✅ **已审计** |
| `setting-service.js` | `mail-worker/src/service/setting-service.js` | ✅ **已审计** |
| `star-service.js` | `mail-worker/src/service/star-service.js` | ✅ **已审计** |
| `telegram-service.js` | `mail-worker/src/service/telegram-service.js` | ✅ **已审计** |
| `turnstile-service.js` | `mail-worker/src/service/turnstile-service.js` | ✅ **已审计** |
| `user-service.js` | `mail-worker/src/service/user-service.js` | ✅ **已审计** |
| `verify-record-service.js` | `mail-worker/src/service/verify-record-service.js` | ✅ **已审计** |
| `email-html.js` | `mail-worker/src/template/email-html.js` | ✅ **已审计** |
| `email-msg.js` | `mail-worker/src/template/email-msg.js` | ✅ **已审计** |
| `email-text.js` | `mail-worker/src/template/email-text.js` | ✅ **已审计** |
| `crypto-utils.js` | `mail-worker/src/utils/crypto-utils.js` | ✅ **已审计** |
| `date-uitil.js` | `mail-worker/src/utils/date-uitil.js` | ✅ **已审计** |
| `domain-uitls.js` | `mail-worker/src/utils/domain-uitls.js` | ✅ **已审计** |
| `email-utils.js` | `mail-worker/src/utils/email-utils.js` | ✅ **已审计** |
| `file-utils.js` | `mail-worker/src/utils/file-utils.js` | ✅ **已审计** |
| `jwt-utils.js` | `mail-worker/src/utils/jwt-utils.js` | ✅ **已审计** |
| `req-utils.js` | `mail-worker/src/utils/req-utils.js` | ✅ **已审计** |
| `time-utils.js` | `mail-worker/src/utils/time-utils.js` | ✅ **已审计** |
| `verify-utils.js` | `mail-worker/src/utils/verify-utils.js` | ✅ **已审计** |
| `index.spec.js` | `mail-worker/test/index.spec.js` | ✅ **已审计** |
| `vitest.config.js` | `mail-worker/vitest.config.js` | ✅ **已审计** |

</details>

<details>
<summary><b>TypeScript (1)</b></summary>

| 模块 | 位置 | 状态 |
| :--- | :--- | :--- |
| `tinymce.d.ts` | `mail-vue/public/tinymce/tinymce.d.ts` | ✅ **已审计** |

</details>

--- 

## ⚠️ 操作指南

如果您看到 **FAIL** 状态或严重的代码问题：
1. **开发人员**：使用上方表格中的 **位置** 列找到确切的文件和行号。
2. **纠正**：遵循为每个规则提供的文档链接以提交修复。
3. **可追溯性**：完整的原始 `.sarif` 数据已附加到此分支。下载并将其导入您的 IDE（例如 VS Code SARIF 查看器）进行本地分析。

--- 

💡 *由 Antigravity AI 安全引擎生成。透明度是我们的承诺。*