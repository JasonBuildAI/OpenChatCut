# Codex parallel-agent claims (append-only)

一个 agent 一次只持有一条 claim；先到先得（时间戳最早者为准）。

格式：`- claim: <agent-id> | <ISO8601> | 旧PR: #<n 或 none> | 缺陷: <一句话> | 文件: <path,path> | issue: #<n> | PR: #<n 或 待创建>`

- claim: agn7c3a | 2026-10-11T12:10:00+08:00 | 旧PR: none | 缺陷: Windows 上 npm test 的 4 个 verify 因与所测代码无关的原因失败（3 个删临时库时被未关闭的 SQLite 连接挡住，1 个把 Windows 路径拼进 RegExp） | 文件: server/storage/sqlite-store.ts,server/storage/fulltext-search.ts,server/storage/semantic-vectors.ts,cli/cli.verify.ts,server/key-probes.verify.ts | issue: #208 | PR: #209
- claim: q2v6 | 2026-10-11T12:34:13+08:00 | 旧PR: none | 缺陷: 桌面 whisper.cpp 转写把 BPE token 当单词（俄语等字幕按字母拆开、句末标点被丢弃） | 文件: desktop/native-asr-utils.ts,desktop/native-asr-worker.verify.ts | issue: #206 | PR: #207

- claim: dx7m4 | 2026-10-11T13:11:41+08:00 | 旧PR: none | 缺陷: Windows 上 verify 只重定向 HOME 而 os.homedir() 读 USERPROFILE，导致 10+ 个 verify 读写用户真实 %USERPROFILE%\.openchatcut：按残留状态失败（checkpoint v2 不支持、readiness 建库、向量数 4!==2、legacy chat 丢失、ENOENT）并写入 fixture 数据（15 个 KV 键）与假 xai-oauth-session.json，真实数据被破坏 | 文件: shared/verify-home.ts,server/storage/sqlite-store.verify.ts,server/storage/sqlite-migration-http.verify.ts,server/storage/semantic-vectors.verify.ts,server/storage/fulltext-search.verify.ts,server/storage/hybrid-search.verify.ts,server/external-agent/offline-mcp.verify.ts,server/external-agent/offline-project-store.verify.ts,server/external-agent/mcp-recovery-race.verify.ts,server/outbound-proxy.verify.ts,server/xai-oauth-session.verify.ts,src/export/export-reachability.verify.ts,desktop/embedded-project-store-http.verify.ts | issue: #210 | PR: 待创建 | 备注: 与 agn7c3a(#208/#209) 仅在 mcp-recovery-race.verify.ts、embedded-project-store-http.verify.ts 各 2 行清理重叠，其余文件不重叠
