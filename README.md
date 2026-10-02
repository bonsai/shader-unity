# shader-unity

Unity Shader を題材に、**イベント → ドメイン → 技術 → トーク**をつなぐための小さなオントロジー実装。

## Ontology

- **Concept**: Shader
- **Domain / Technology**: Unity
- **Technologies**: ShaderLab, Cg/HLSL, Surface Shader, Shader Graph, Compute Shader
- **Event**: Unity Shader 完全に理解した勉強会
- **Format**: Online / Offline

データは `ontology.jsonl` に JSONL として保持する。

## Semantic chain

```
Event
  └─ hasTheme → Concept: Shader
       └─ hasDomain → Technology: Unity
            └─ hasTechnology → ShaderLab / Cg-HLSL / Surface Shader / Shader Graph / Compute Shader
                 └─ hasFormat → Online / Offline
```

このリポジトリは、告知文を単なる文章として扱わず、**文中の意味を型と関係へ分解し、後続の talkscript / TTS / knowledge processing へ渡せる形にする**ための実例とする。
