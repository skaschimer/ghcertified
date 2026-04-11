---
question: "マトリックスジョブ `example_matrix` を定義しました。最大で2つのジョブのみ実行するようマトリックスを制限するにはどうすれば良いですか？"
title: "Question 036"
---

```yaml
  jobs:
    example_matrix:
      strategy:
        matrix:
          version: [10, 12, 14]
          os: [ubuntu-latest, windows-latest]
```
> https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions#jobsjob_idstrategymax-parallel
1. [x] `jobs.example_matrix.strategy.max-parallel` を2に設定する
1. [ ] `jobs.example_matrix.strategy.concurrency` を2に設定する
1. [ ] GitHubのREST APIを使用してジョブ数が2未満であることを確認する
1. [ ] 不可能です。ランナーが利用可能な場合には、マトリックスは常にすべてのジョブを並行して実行します。
