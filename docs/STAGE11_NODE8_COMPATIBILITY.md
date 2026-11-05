# Stage 11: Node 8 compatibility correction

The user-provided BMW runtime is Node.js 8.16.2. Stage 10 compiled Store included object-spread expressions in `apps/robertn_store/src/am_gpu.js`, notably `...W.DRAW`, `...S.DRAW`, `...Q.DRAW`, `...W.TRY`, and `...S.TRY`.

Stage 11 replaces those object merges with `Object.assign(DRAW, W.DRAW, S.DRAW, Q.DRAW)` and `Object.assign({}, W.TRY, S.TRY)`; the donor-linked build regenerated `bcs_store@1.0.2.tgz`. Three BCS image assets were restored byte-for-byte from the working V1 donor after build. 36 screen configurations / 896 checks passed.

Compiled candidate SHA-256: `4bcb4c2c0d196d991791f4942c056f3a033488b5848b6dbe6f74c42ae3a240b5`.

**Not yet validated:** full Node.js 8 syntax/runtime, BMW installation, BCS icon appearance on head unit, live GitHub catalog. Do not install over working V1. Full Stage 11 source is provided as a separate ZIP, not yet committed wholesale to GitHub.
