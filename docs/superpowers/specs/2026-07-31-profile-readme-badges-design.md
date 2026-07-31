# Profile README Badges

## Goal

Add a compact badge section inspired by `QIN2DIM/QIN2DIM` while preserving the current profile README's concise, engineering-first presentation. The badges should reflect Leslie's actual AI infrastructure, retrieval, inference, speech, vision, and observability work.

## Layout

Place the linked GitHub Roast score badge directly below the opening introduction so it is visible without dominating the technical content.

Add a `Languages and Tools` section between the introduction and `What I build`. Organize the technology badges into three short rows:

- AI and retrieval: Python, Xinference, Dify, and RAGFlow.
- Speech and vision: Kaldi, sherpa-onnx, Ultralytics YOLO, PaddlePaddle, and FunASR.
- Infrastructure and observability: Docker, Langfuse, Grafana, and RustFS.

Keep the rest of the README copy and section order unchanged.

## Badge Presentation

- Use Shields.io badges with the `flat-square` style for a consistent visual rhythm.
- Use recognizable official logos and brand colors when Shields.io supports them reliably.
- Use clear text-only badges when a dependable official logo is unavailable.
- Link the GitHub Roast badge to `https://ghfind.com/u/leslie2046?ref=badge` and load its image from `https://ghfind.com/api/badge/leslie2046?lang=zh`.
- Keep technology badges informational rather than adding links that could imply endorsements or ownership.

## Repository Changes

- Update `README.md` with the GitHub Roast badge and the new grouped badge section.
- Add no generated assets, scripts, workflows, or dependencies.
- Preserve the existing English prose and project links.

## Validation

- Check every badge image URL and the GitHub Roast destination URL.
- Confirm the Markdown renders as three compact technology rows.
- Confirm the visible labels use the intended product names.
- Run `git diff --check` and inspect the final diff before committing.

## Delivery

Commit the design document first. After the design review gate, implement the README change, verify it, commit it, and push both commits to the current remote branch.
