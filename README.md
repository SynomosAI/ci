# SynomosAI shared CI

Org-scoped reusable workflow for SynomosAI repositories.

SynomosAI 组织策略不允许调用其他组织的 reusable workflow，因此本仓是 `LGD-AI/lgd-ci` 的同源镜像。

调用方式（在任意 SynomosAI 仓新建 `.github/workflows/lgd-ci.yml`）：

```yaml
name: LGD CI
on:
  pull_request:
  push:
    branches: [ main ]
permissions:
  contents: read
jobs:
  ci:
    uses: SynomosAI/ci/.github/workflows/lgd-reusable-ci.yml@<40-hex-sha>
    with:
      python-version: "3.11"
      run-tests: false
      require-skill-md: false
```

改动本仓前请同步修改 `LGD-AI/lgd-ci`，两边必须保持同一份正文。