# Evidence Notes — Source Resolution (single_2)

- **Task:** `source-resolution` sub-task #2 of the LJT-Homepage review workflow
- **Target repository:** `mcpmark-eval-1031/LJT-Homepage`
- **Reviewed branch:** `master` (branch head `5d9f9272fe92f3fe8669d8c22a1ac272f7f966a4`, committed 2026-03-29T13:01:52Z by bugmaker00)
- **Review branch (this set):** `review/source-resolution-single-2`
- **Full reviewed target set:** `source_resolution_single_2.csv` (12 candidate rows, S01–S12)
- **Task notes / inputs:** `requested_homepage_fields.json`, `publication_fields.csv`, `homepage_content.json`, `memory_gap_report.json`; audits `homepage_code_link_audit.json`, `homepage_release_audit.json`
- **Method:** each publication code-link "source" was resolved against the live GitHub README/BibTeX of the canonical upstream repository, re-verified live in this session. A value is placed in the finalized set below only when it was both (a) confirmed against a live, public, title-exact source and (b) a change actually present (or confirmably absent) on the reviewed homepage.

## Summary

| | Count |
|---|---|
| Candidates reviewed (source_resolution_single_2.csv) | 12 (6 publications × 2 surfaces: `_pages/about.md` [Code] link + `_publications/*.md` codeurl) |
| Finalized — safe to apply live (REPAIR) | 6 rows → 3 unique corrected code URLs |
| Finalized — confirmed no-op / do-not-add (CONFIRM_NONE) | 6 rows → 3 publications, no code link published, none invented |

## Finalized subset — resolved values SAFE to apply live

### Group A — repaired code links (apply to both `_pages/about.md` and the matching `_publications/*.md` codeurl)

All three resolve a stale/redirected or dead `Vicent0205/*` link to the verified canonical upstream repository. Each canonical repo is **public**, matches the paper **title exactly** in its README, carries a **BibTeX entry whose author order puts Junteng Liu first**, and exposes **zero release tags** (`/tags -> []`), so `code_status = repo_exists_no_release` (resolves the link; not claimed as "released").

1. **SynLogic** — `https://github.com/Vicent0205/SynLogic` → **`https://github.com/MiniMax-AI/SynLogic`**
   - Live evidence: README = "SynLogic: Synthesizing Verifiable Reasoning Data at Scale for Learning Logical Reasoning and Beyond"; BibTeX `@misc{liu2025synlogic}`, eprint `2505.19641`, primaryClass cs.AI; repo description "[NeurIPS 2025] The official repo of SynLogic"; dataset `huggingface.co/datasets/MiniMaxAI/SynLogic`.
   - The old `Vicent0205/SynLogic` resolves via a rename/transfer redirect to `MiniMax-AI/SynLogic` (identical `main` HEAD).
   - S01, S02.

2. **On the Perception Bottleneck of VLMs for Chart Understanding** — `https://github.com/Vicent0205/Vision4Chart` → **`https://github.com/hkust-nlp/Vision4Chart`**
   - Live evidence: repo description "The official repo of \"On the Perception Bottleneck of VLMs for Chart Understanding\""; BibTeX `@misc{liu2025perceptionbottleneckvlmschart}`, eprint `2503.18435`; dataset `huggingface.co/datasets/Junteng/Vision4Chart`.
   - The old `Vicent0205/Vision4Chart` is dead (HTTP 404); no redirect. This is the only row where the canonical URL is a hard replacement rather than a redirect.
   - S03, S04.

3. **On the Universal Truthfulness Hyperplane Inside LLMs** — `https://github.com/Vicent0205/Universal_Truthfulness_Hyperplane` → **`https://github.com/hkust-nlp/Universal_Truthfulness_Hyperplane`**
   - Live evidence: README "Our paper is accepted by EMNLP 2024!"; arXiv `2407.08582`; BibTeX `@article{liu2024universal}`.
   - The old `Vicent0205/Universal_Truthfulness_Hyperplane` resolves via a rename/transfer redirect to the canonical `hkust-nlp` repo.
   - S05, S06.

### Group B — confirmed no-op (no code link published → none added), safe to leave unchanged

The homepage publishes **no** code link for these papers. Their verified upstream repositories exist and are public but carry **zero release tags**, so even a confirmed repository does not qualify as "released", and no URL is invented or back-filled (keeps the homepage consistent and avoids a source that was never published).

4. **In-Context Sharpness as Alerts** — no code link published. Upstream verified: `hkust-nlp/Activation_Decoding` (README matches paper, arXiv `2403.01548`, BibTeX `chen2024incontext`), 0 release tags. S07, S08.
5. **C-Eval** — no code link published. Upstream verified: `hkust-nlp/ceval` (NeurIPS 2023, arXiv `2305.08322`, BibTeX `huang2023ceval`, dataset `ceval/ceval-exam`), 0 release tags. S09, S10.
6. **Composing Parameter-Efficient Modules with Arithmetic Operations** — no code link published. Upstream verified: `hkust-nlp/PEM_composition` (NeurIPS 2023, arXiv `2306.14870`, BibTeX `zhang2023composing`, dataset `jinghan23/DatasetofPEMCompostition`), 0 release tags. S11, S12.

## Scope boundaries applied (not part of the safe-to-apply subset)

The following were reviewed but deliberately **excluded** from the live-applicable resolved values, consistent with `homepage_release_audit.json` and `memory_gap_report.json`:

- **Publication status promotion.** The two currently-labelled preprints (`synlogic`, `vlm-chart` / "Perception Bottleneck") were **not** promoted to a published venue during source resolution. Status promotion requires a title-exact acceptance notice; none was available to this workflow, so titles/venues/status are left as-is. Only the code-link source was resolved here.
- **`publications_in_about_section`.** Publications are rendered inside the about page itself (no split-out publications page); per-paper metadata beyond title+year, author lists, venue strings and the three repaired [Code] links are not memory-backed and are not re-derived here.
- **Unsupported requested fields.** `awards`, `phone`, `portrait_url`, `service`, `teaching` have no memory backing; nothing about them is resolved or applied from site-rendered content (e.g. the homepage's "Zhiyuan Honor Scholarship" and `profile.png` avatar are not adopted as resolved values).
- **Release status.** No paper is asserted as "released"; all candidate upstream repositories reported 0 non-draft release tags.

## Resulting change set staged on `review/source-resolution-single-2`

The reviewed change set consists of correcting the three stale/dead `Vicent0205/*` code links to their verified canonical upstream URLs (each applied in both the publications collection `codeurl` front-matter and the matching `[Code]` link in `_pages/about.md`), and explicitly confirming the three remaining papers keep **no** code link. No other live homepage content is modified by this source-resolution step.
