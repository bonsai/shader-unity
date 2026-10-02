# shader-unity

Unity Shader を題材に、**イベント告知を世界モデルへ変換する**ための小さなオントロジー実装。

## Ontology

connpass のイベント情報を、単なる文章ではなく Entity / Relation として表現する。

- **Event**: Unity Shader 完全に理解した勉強会
- **Concept**: Shader, Toon, Shadow, Volumetric Light Shafts
- **Domain / Technology**: Unity, URP, ShaderLab, Cg/HLSL, Shader Graph, Compute Shader, GPU Instancing
- **Session**: イントロ、4つの発表、スポンサー紹介、中締め、懇親会
- **Person**: 各登壇者
- **Audience**: Shaderを理解している人 / 理解したい人
- **Venue**: DeNA ラウンジ
- **Platform**: YouTube Live
- **Community**: Unity 〇〇完全に理解した 勉強会

データは `ontology.jsonl` に JSONL として保持する。

## Semantic chain

```
Event
├─ hasTheme → Concept: Shader
├─ hasDomain → Technology: Unity
├─ hasTechnology → ShaderLab / Cg-HLSL / Shader Graph / Compute Shader / URP
├─ hasSession → Session
│    ├─ hasSpeaker → Person
│    └─ hasTopic → Concept / Technology
├─ targets → Audience
├─ heldAt → Venue
└─ streamedOn → Platform
```

## Why this matters

告知文を

**文章 → Entity → Relation → Knowledge Graph → TalkScript → AST → TTS**

へ変換できる。

つまり、イベントページそのものが「読む文章」だけではなく、後続のAI処理に渡せる構造化された世界モデルの入口になる。

`shader-unity` は、その変換を Shader という具体的なドメインで試す実例。
