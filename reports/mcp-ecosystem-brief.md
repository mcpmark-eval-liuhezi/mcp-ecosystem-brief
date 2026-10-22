# MCP Ecosystem Brief

Scope: the organization behind the Model Context Protocol (GitHub login `modelcontextprotocol`) and its official `servers` repository. Every figure below was read live from GitHub on 2026-10-22 — nothing is carried over from notes.

## 1. Organization snapshot

| Field | Value (as GitHub reports it) |
| --- | --- |
| Login | `modelcontextprotocol` |
| Description | **Not available** — no GitHub lookup used for this brief returned an organization description (org search returns only login/profile; a direct org-profile read was not available). Left blank rather than filled from memory. |
| Public repositories | **45** |

The public-repository count is GitHub's repository-search total for `user:modelcontextprotocol`; none of the 45 are forks (`fork:only` returns 0).

## 2. CI cost sample — the `servers` repository's main CI workflow

**Main CI workflow:** "TypeScript" — `.github/workflows/typescript.yml` (workflow ID `129263192`), triggered on `push` and `workflow_dispatch`; its own header comment states that PR checks report from these runs. (For the record: the repo's older `.github/workflows/ci.yml` no longer exists on the default branch — the file returns 404 — and that workflow has only 2 recorded runs, the newest from 2025-10-20. The `python.yml` workflow is the sibling CI for the Python servers; TypeScript is the de-facto main CI.)

**The three most recently completed runs** (each: status `completed`, conclusion `success`, event `push`):

### Run #9787
- Run ID: 39211896906 · branch `v2.0.0`
- Billable time: **0 ms on UBUNTU (17 jobs), 0 ms on WINDOWS (4 jobs)** — 21 jobs total
- Run duration: **58,000 ms** (≈ 58 seconds)
- https://github.com/modelcontextprotocol/servers/actions/runs/39211896906

### Run #9786
- Run ID: 39211000669 · branch `main`
- Billable time: **0 ms on UBUNTU (17 jobs), 0 ms on WINDOWS (4 jobs)** — 21 jobs total
- Run duration: **57,000 ms** (≈ 57 seconds)
- https://github.com/modelcontextprotocol/servers/actions/runs/39211000669

### Run #9785
- Run ID: 39209955126 · branch `v2/chore/5159-release-v2.0.0`
- Billable time: **0 ms on UBUNTU (17 jobs), 0 ms on WINDOWS (4 jobs)** — 21 jobs total
- Run duration: **60,000 ms** (≈ 60 seconds)
- https://github.com/modelcontextprotocol/servers/actions/runs/39209955126

Summary:

| Run number | Billable UBUNTU | Billable WINDOWS | Run duration |
| --- | --- | --- | --- |
| #9787 | 0 ms (17 jobs) | 0 ms (4 jobs) | 58,000 ms |
| #9786 | 0 ms (17 jobs) | 0 ms (4 jobs) | 57,000 ms |
| #9785 | 0 ms (17 jobs) | 0 ms (4 jobs) | 60,000 ms |

GitHub reports 0 ms of billable time for these runs — as expected for Actions on a public repository, where usage is not billed. The figures above are exactly as the usage endpoint reports them.

## 3. Release anchor

- **Newest release:** `v2.0.0`
- **Tag resolves to SHA:** **`51b6382a3e827aceb6bce430b1208d69b93d95ea`** (merge commit of PR #5166, "Release v2.0.0: merge v2/main into main")
- Provenance note: the release endpoints (`get_latest_release`, `list_releases`, `get_release_by_tag`) each returned error-wrapped payloads whose content was consistent (tag `v2.0.0`); the tag→SHA mapping was independently confirmed by a clean `list_tags` call (`v2.0.0` → `51b6382a…`) and by CI run #9787 executing on branch `v2.0.0` at that head SHA. `get_tag` on that SHA 404s because it is a lightweight tag (no annotated tag object), not because the tag is missing.

## 4. Star list (account: HeziLiu)

- **Starred `modelcontextprotocol/servers`?** **No** — the servers repository is not among the starred repositories.
- **Total starred repositories:** **6**
  1. OpenBMB/AgentCPM
  2. PaddlePaddle/ERNIE
  3. FudanNLP/fastNLP
  4. maplezzz/NTU_ML2017_Hung-yi-Lee_HW
  5. fighting41love/funNLP
  6. 996icu/996.ICU

Verified by paging the authenticated user's starred-repository list (pages of 2: three full pages, then an empty fourth page) — `modelcontextprotocol/servers` appears nowhere in it.

## Lookups that errored or came back empty

Stated plainly, so nothing here is silently filled in from memory:

1. **Organization description** — not returned by any available lookup (org search exposes only login/profile; no direct org-profile read was available). Reported as unavailable in §1.
2. **`.github/workflows/ci.yml`** — 404 Not Found (the file is no longer on the default branch); the workflow of that name has only 2 recorded runs, none recent.
3. **Release endpoints** (`get_latest_release`, `list_releases`, `get_release_by_tag`) — all returned error-wrapped payloads carrying identical release content; corroborated via `list_tags` (see §3).
4. **`get_tag` on `51b6382a…`** — 404 (lightweight tag; no annotated tag object exists).
5. **Repository creation under the personal account** — 403 "Resource not accessible by personal access token" (two attempts). This brief was therefore committed to the identically-named public repository under the org `mcpmark-eval-liuhezi` instead.
