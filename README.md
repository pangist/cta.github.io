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

## 为什么 VSCode 的 Copilot 使用 Claude 模型时提示"Contact your admin"？

### 问题说明

在 VSCode 中使用 GitHub Copilot 时，切换到 Claude（Anthropic）模型可能会看到提示：

> **"To use this model, contact your administrator"**（需要联系管理员才能使用此模型）

而在 GitHub.com 的 Copilot Chat 界面中，同一个账号却可以直接使用 Claude 模型。

### 原因解释

这两个入口的模型可用性由**不同层级的权限**控制：

| 入口 | 模型访问控制方 |
|------|--------------|
| VSCode Copilot（组织账号） | 组织（Organization）管理员 |
| GitHub.com Copilot Chat | GitHub 账号级别 / 个人订阅 |

**具体原因：**

1. **组织策略限制**：如果你的 GitHub Copilot 许可证由公司/组织分配（Copilot Business 或 Copilot Enterprise），组织管理员可以控制成员可使用的 AI 模型。当管理员未启用 Claude 模型时，VSCode 端会显示"Contact your admin"。

2. **GitHub.com 的独立入口**：在 GitHub.com 的 Copilot Chat 中，有时会通过个人订阅或不同的权限路径访问模型，因此不受组织策略限制，Claude 模型可以正常使用。

### 解决方法

**方法一：联系组织管理员启用 Claude 模型**

组织管理员可通过以下步骤开启：

1. 进入 GitHub 组织设置：`Settings` → `Copilot` → `Policies`
2. 在 **"Editor preview features"** 或 **"Model selection"** 中启用 Claude 等第三方模型
3. 保存后，组织成员即可在 VSCode 中使用 Claude 模型

**方法二：使用个人 Copilot 订阅**

如果你拥有个人的 GitHub Copilot 订阅（非组织分配），可以在 VSCode 中切换到个人账号登录，个人订阅不受组织策略限制。

**方法三：在 GitHub.com 上使用**

如当前情况所示，可以直接在 [github.com/copilot](https://github.com/copilot) 的 Copilot Chat 界面中使用 Claude 模型，功能与 VSCode 端基本一致。

### 参考资料

- [Managing Copilot policies for your organization](https://docs.github.com/en/copilot/managing-copilot/managing-github-copilot-in-your-organization/managing-policies-for-copilot-in-your-organization)
- [Changing the AI model for Copilot Chat](https://docs.github.com/en/copilot/using-github-copilot/ai-models/changing-the-ai-model-for-copilot-chat)
