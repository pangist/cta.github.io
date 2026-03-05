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

## VSCode Copilot 显示"Contact your admin"使用 Claude 模型的原因

**问题**：在 VSCode 中使用 GitHub Copilot 时，选择 Claude（Anthropic）等第三方模型时提示"请联系管理员"，但在 GitHub.com 的 Copilot Chat 页面中可以正常使用。

**原因**：GitHub 组织管理员可以通过组织级别的 Copilot 策略，控制成员在 IDE 插件（如 VSCode）中可以使用哪些 AI 模型。当组织策略限制了某个模型（例如 Claude）的访问权限时，VSCode 中的 Copilot 插件会显示"Contact your admin"（请联系管理员）提示。GitHub.com 网页端的 Copilot Chat 可能采用不同的策略配置，因此不受相同限制。

**解决方法**：组织管理员需要登录 GitHub，进入组织设置页面，开放对应模型的访问权限：

1. 访问 `https://github.com/organizations/<组织名>/settings/copilot/policies`
2. 在"模型访问"或"Copilot 功能"部分，启用 Claude（或其他所需模型）的使用权限
3. 保存设置后，成员在 VSCode 中重新加载 Copilot 即可使用该模型

> 如果你不是组织管理员，请将上述步骤转发给你的 GitHub 组织管理员处理。
