# Codex parallel-agent claims (append-only)

一个 agent 一次只持有一条 claim；先到先得（时间戳最早者为准）。

格式：`- claim: <agent-id> | <ISO8601> | 旧PR: #<n 或 none> | 缺陷: <一句话> | 文件: <path,path> | issue: #<n 待回填>`

- claim: agn7c3a | 2026-10-11T12:10:00+08:00 | 旧PR: none | 缺陷: Windows 上 npm test 的 4 个 verify 因与所测代码无关的原因失败（3 个删临时库时被未关闭的 SQLite 连接挡住，1 个把 Windows 路径拼进 RegExp） | 文件: server/storage/sqlite-store.ts,server/storage/fulltext-search.ts,server/storage/semantic-vectors.ts,cli/cli.verify.ts,server/key-probes.verify.ts | issue: #<n 待回填>
- claim: q2v6 | 2026-10-11T12:34:13+08:00 | 旧PR: none | 缺陷: 桌面 whisper.cpp 转写把 BPE token 当单词（俄语等字幕按字母拆开、句末标点被丢弃） | 文件: desktop/native-asr-utils.ts,desktop/native-asr-worker.verify.ts | issue: #206 | PR: #207
