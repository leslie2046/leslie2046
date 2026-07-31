# Profile README Badges Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add a linked GitHub Roast score badge and 13 grouped technology badges to Leslie's profile README.

**Architecture:** This is a Markdown-only change. The README will keep its existing prose and add one linked dynamic badge plus a compact `Languages and Tools` section whose three rows communicate AI and retrieval, speech and vision, and infrastructure and observability.

**Tech Stack:** GitHub Flavored Markdown, Shields.io, ghfind.com

## Global Constraints

- Preserve all existing README prose, project links, and section order after the new badge section.
- Use Shields.io `flat-square` badges throughout the technology section.
- Use official logos only where Shields.io supports them reliably; otherwise use text-only badges.
- Link every technology badge to its official GitHub repository.
- Add no generated assets, scripts, workflows, or dependencies.
- Push the completed commits to the current remote branch.

---

### Task 1: Add and deliver the profile badges

**Files:**
- Modify: `README.md:1-5`
- Create: `docs/superpowers/plans/2026-07-31-profile-readme-badges.md`
- Test: Markdown and remote image URL checks from the repository root

**Interfaces:**
- Consumes: Existing opening introduction in `README.md` and public badge endpoints from ghfind.com and Shields.io.
- Produces: A profile README containing one linked score badge and 13 technology badges in three thematic rows.

- [ ] **Step 1: Insert the score badge and grouped technology badges**

Immediately after the opening paragraph, add this exact Markdown:

```markdown
[![GitHub Roast 评分徽章](https://ghfind.com/api/badge/leslie2046?lang=zh)](https://ghfind.com/u/leslie2046?ref=badge)

## Languages and Tools

[![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)](https://github.com/python/cpython)
[![Xinference](https://img.shields.io/badge/-Xinference-4B32C3?style=flat-square)](https://github.com/xorbitsai/inference)
[![Dify](https://img.shields.io/badge/-Dify-1C64F2?style=flat-square&logo=dify&logoColor=white)](https://github.com/langgenius/dify)
[![RAGFlow](https://img.shields.io/badge/-RAGFlow-FF5C35?style=flat-square)](https://github.com/infiniflow/ragflow)

[![Kaldi](https://img.shields.io/badge/-Kaldi-4B8BBE?style=flat-square)](https://github.com/kaldi-asr/kaldi)
[![sherpa-onnx](https://img.shields.io/badge/-sherpa--onnx-1F6FEB?style=flat-square)](https://github.com/k2-fsa/sherpa-onnx)
[![Ultralytics YOLO](https://img.shields.io/badge/-Ultralytics_YOLO-111F68?style=flat-square&logo=ultralytics&logoColor=white)](https://github.com/ultralytics/ultralytics)
[![PaddlePaddle](https://img.shields.io/badge/-PaddlePaddle-0062B0?style=flat-square&logo=paddlepaddle&logoColor=white)](https://github.com/PaddlePaddle/Paddle)
[![FunASR](https://img.shields.io/badge/-FunASR-5B45DE?style=flat-square)](https://github.com/modelscope/FunASR)

[![Docker](https://img.shields.io/badge/-Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://github.com/docker/docker-ce)
[![Langfuse](https://img.shields.io/badge/-Langfuse-000000?style=flat-square&logo=langfuse&logoColor=white)](https://github.com/langfuse/langfuse)
[![Grafana](https://img.shields.io/badge/-Grafana-F46800?style=flat-square&logo=grafana&logoColor=white)](https://github.com/grafana/grafana)
[![RustFS](https://img.shields.io/badge/-RustFS-CE422B?style=flat-square)](https://github.com/rustfs/rustfs)
```

- [ ] **Step 2: Verify badge inventory and Markdown structure**

Run:

```powershell
$readme = Get-Content -Raw -Encoding UTF8 README.md
@(
  'GitHub Roast 评分徽章', 'Python', 'Xinference', 'Dify', 'RAGFlow',
  'Kaldi', 'sherpa-onnx', 'Ultralytics YOLO', 'PaddlePaddle', 'FunASR',
  'Docker', 'Langfuse', 'Grafana', 'RustFS'
) | ForEach-Object {
  if ($readme -notmatch [regex]::Escape("![$_]")) { throw "Missing badge: $_" }
}
if (($readme | Select-String -Pattern 'style=flat-square' -AllMatches).Matches.Count -ne 13) {
  throw 'Expected exactly 13 flat-square technology badges.'
}
```

Expected: the command exits successfully with no output.

- [ ] **Step 3: Check every remote URL**

Run:

```powershell
$readme = Get-Content -Raw -Encoding UTF8 README.md
$urls = [regex]::Matches($readme, 'https://[^)\s]+') | ForEach-Object Value | Sort-Object -Unique
$badgeUrls = $urls | Where-Object { $_ -match 'ghfind\.com|img\.shields\.io' }
foreach ($url in $badgeUrls) {
  $response = Invoke-WebRequest -Uri $url -Method Get -MaximumRedirection 5
  if ($response.StatusCode -lt 200 -or $response.StatusCode -ge 400) {
    throw "URL failed: $url ($($response.StatusCode))"
  }
}
```

Expected: every ghfind.com and Shields.io URL returns HTTP 2xx or 3xx after redirects.

- [ ] **Step 4: Inspect repository checks and final diff**

Run:

```powershell
git diff --check
git diff -- README.md docs/superpowers/plans/2026-07-31-profile-readme-badges.md
git status --short --branch
```

Expected: `git diff --check` emits no errors; the diff contains only the approved badge section and this plan; the branch is `main` and is ahead of `origin/main` by the design commit.

- [ ] **Step 5: Commit the implementation**

Run:

```powershell
git add -- README.md docs/superpowers/plans/2026-07-31-profile-readme-badges.md
git diff --cached --check
git commit -m "docs: add profile technology badges"
```

Expected: Git creates one commit containing the README and implementation plan.

- [ ] **Step 6: Push both commits**

Run:

```powershell
git push origin main
git status --short --branch
```

Expected: the push succeeds and `main` matches `origin/main` with a clean working tree.
