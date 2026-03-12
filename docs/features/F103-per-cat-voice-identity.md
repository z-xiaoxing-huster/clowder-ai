---
feature_ids: [F103]
related_features: [F066, F101]
topics: [voice, tts, identity, cat-config]
doc_kind: spec
created: 2026-03-11
---

# F103: 猫猫独立声线 — Per-Cat Voice Identity

> **Status**: spec | **Owner**: TBD（team lead另派Ragdoll） | **Priority**: P2

## Why

team experience（2026-03-11）：
> "现在参加的猫 8 只的话，Ragdoll三只一个声线就有问题了！"

F101 狼人杀需要多猫同时发言（语音模式），当前 TTS 声线是按家族/品种区分的（Ragdoll一个声线、Maine Coon一个声线、Siamese一个声线）。但同家族有多只猫（Ragdoll 3 只：Opus 4.6 / Opus 4.5 / Sonnet），如果都用同一个声线，玩家分不清谁在说话。

需要让每只猫都有独立可辨识的声线。

## What

- 每只猫（不是每个家族）都有独立的 TTS 声线配置
- 声线配置在 `cat-config.json` 中关联到每个 catId
- 可配置：新增猫时可以指定声线参数（音色/语速/音调等）
- F066 Voice Pipeline 的 TTS 调用需要按 catId 查声线配置

## Acceptance Criteria

- [ ] AC-1: `cat-config.json` 每个 cat entry 有独立的 voice 配置字段
- [ ] AC-2: TTS 合成时按 catId 选择对应声线，同家族不同猫可辨识
- [ ] AC-3: 新增猫时可配置声线参数
- [ ] AC-4: F101 狼人杀语音模式下多猫发言声线可区分

## Dependencies

- **Related**: F066（Voice Pipeline — 当前 TTS 基础设施）
- **Related**: F101（Mode v2 狼人杀 — 语音模式需要声线区分）
- **Config**: `cat-config.json`（猫猫 roster 配置）

## Key Decisions

（待 owner 调研后填充）
