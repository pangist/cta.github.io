# cta.github.io

```text
收益率(%)
 3.6 |                             * (30Y)
 3.4 |                          *
 3.2 |                       * (10Y)
 3.0 |                   * (5Y)
 2.8 |               * (2Y)
 2.6 |           * (1Y)
 2.4 |       * (6M)
 2.2 |   * (1M)
     +---------------------------------------------------> 期限
       1M   3M   6M    1Y     2Y        5Y      10Y   30Y
```

---

## 关于 VS Code 中 Copilot 使用 Claude 模型提示"contact your admin"的说明

### 原因

VS Code 中的 GitHub Copilot 会受到 **GitHub 组织（Organization）层面的 Copilot 模型访问策略** 控制。当你的账号隶属于某个 GitHub 组织，且该组织的管理员尚未在组织设置中启用 Claude（Anthropic）等第三方模型时，VS Code 会提示 **"Contact your admin"**（请联系管理员）。

而在 GitHub.com 的 Copilot Chat 网页界面中，若你使用的是个人 Copilot 订阅（Copilot Individual），则不受组织策略限制，因此可以直接使用 Claude 模型。这就是两端体验不一致的根本原因。

### 解决方法

**（适用于 GitHub 组织管理员）**

1. 进入 GitHub 组织的 **Settings（设置）**。
2. 在左侧菜单选择 **Copilot** > **Policies（策略）**。
3. 在模型选择或"编辑器预览功能"（Editor preview features）区域，启用 **Claude** 或所需的第三方模型。
4. 保存设置后，组织成员在 VS Code 中即可使用 Claude 模型，不再提示需要联系管理员。

**（适用于个人用户）**

如果你并非通过组织订阅使用 Copilot，请确认：
- 使用的是 **Copilot Individual** 或支持模型选择的订阅计划。
- VS Code 中的 GitHub Copilot 扩展已更新至最新版本。
- 在 VS Code 的 Copilot Chat 界面，点击模型选择器（Model Picker）并选择 Claude 模型。

---

## Why VS Code Copilot Shows "Contact Your Admin" for Claude Model

### Root Cause

GitHub Copilot in VS Code is subject to **organization-level Copilot model-access policies**. When your account belongs to a GitHub Organization and the organization's administrator has not enabled third-party models (such as Claude by Anthropic) in the organization's Copilot settings, VS Code will display **"Contact your admin"**.

In contrast, the Copilot Chat web interface on GitHub.com operates under your personal Copilot subscription (Copilot Individual) which is not restricted by organization policies, so Claude models are accessible there.

### Resolution

**For GitHub Organization Administrators:**

1. Go to your organization's **Settings**.
2. Navigate to **Copilot** > **Policies** in the left sidebar.
3. Under model selection or **Editor preview features**, enable **Claude** or the desired third-party model.
4. After saving, organization members can use the Claude model in VS Code without the admin restriction message.

**For Individual Users:**

If you are not using Copilot through an organization subscription:
- Ensure you have a **Copilot Individual** plan or a plan that supports the model picker.
- Keep the GitHub Copilot extension in VS Code updated to the latest version.
- In the VS Code Copilot Chat panel, click the **Model Picker** to select the Claude model.
