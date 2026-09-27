# Outline

Read when planning a new post or restructuring an existing one. The outline is the cheapest place to fix structure — treat it as a negotiation, not a draft.

## Skeleton

Adapt to the topic, don't force it:

```
前言              links back to the previous episode
为什么需要 X      motivation — the pain the technique solves
X 是什么          core definition and unified form
各方法 / 变体      one H1 per method; sub-sections per real dimension
结语              distilled takeaways; optional pointer to next episode
参考资料          bare link list
```

## Heading rules

- Short nouns. **No parentheses, no colons.** A heading that needs them covers too much — split it.
- No `## XX 是什么` — a method's definition lives directly under its H1.
- `##` exists for genuinely distinct dimensions only: limitations, properties, engineering details, `## 代码实现`.
- Fixed names: `结语` (not 总结), `参考资料` (not 参考).
- Merge subsections only when two topics share **one mechanism** (e.g. a bucketed bias is a scalar variant of a learned offset). Never merge just to shorten the TOC. List merge candidates and let the human rule each pair.

## Code slots

Each major section declares its `## 代码实现` intent in one line — what the snippet will prove, not the code itself. A catch-all section at the end exists only if earlier sections leave gaps.

## Propose additions

Offer 2–3 candidate topics that fit the scope bar from Intake, each labeled mainstream or niche, with a one-line reason. The human picks; nothing gets added silently.

## Gate

Present the tree plus decisions list — merges, additions, code-slot plan — as one review pass. Multiple rounds are normal; do not draft until approval unless the authorization mode says otherwise.
