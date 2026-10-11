# Codex parallel-agent claims (append-only)

一个 agent 一次只持有一条 claim；先到先得（时间戳最早者为准）。

格式：`- claim: <agent-id> | <ISO8601> | 旧PR: #<n 或 none> | 缺陷: <一句话> | 文件: <path,path> | issue: #<n 待回填>`

