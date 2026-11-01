# pack-aws-aif — authoring rules

A quizmill content pack for the AWS Certified AI Practitioner (AIF-C01)
exam. Public repo: write commit messages, PR bodies and comments in terms
of what a change does for a learner or pack author.

## Files

- `pack.json` — manifest (schema v2). `categories` are the five exam
  domains with the exam guide's weights; `exam` holds the guide's numbers.
  Both are cited in `NOTICE.md` — change one, update the other.
- `questions.json` — the bank. `scenarios.json` is `[]` until a shared stem
  is needed.
- `concepts.json` — concept cards, linked from questions by `conceptId`.
- `.github/workflows/ci.yml` — validates every PR and push.
- `.github/workflows/deploy.yml` — calls the engine's reusable
  `deploy-pack.yml`; deploys on push to `main` only.

## Content rules

- **Every question is original**, written from the public AWS docs and the
  official exam guide. No imports from community banks, AWS official
  practice questions or pretests, or exam dumps — not even "adapted".
  Community posts may steer *coverage* (which topics, which traps), never
  the wording of an item.
- Every question has `source: "original"`, `reviewStatus: "draft"`, and a
  `sourceRef` to the AWS doc page it rests on. The explanation ends with
  `Read more: <url>` pointing at a page that supports the claim. Check the
  URL returns 200 before committing.
- Ids are `aws-aif-<tier>-d<domain>-<n>` (`n` runs per domain across
  tiers); tags are `aif-c01`, `domain-<n>` and `task-<n.n>` (the guide's
  task statement). The tier lives in `level`, not in `tags`. Never reuse or
  renumber an id: learner progress is keyed on it.
- Practitioner style: a short situation, then the question; four options
  (five for "Select TWO"), one best answer. Multi-answer stems say
  "(Select TWO.)" and use `correctKeys`. Negative stems capitalise NOT /
  EXCEPT; avoid a lowercase "not" in a scenario's constraints.
- **Distractors must be plausible**: a real AWS service or feature that
  fits a neighbouring use case, or a near-miss that meets every constraint
  but one. No joke options, no "all of the above", no distractor that
  announces its own defect, and no absolute words ("always", "never",
  "only") that give a distractor away.
- **No length cue**: the key is no longer than 1.25× the longest distractor.
- Every distractor carries a one-sentence `explanation` (≤ 300 characters)
  saying why it fails; keyed options carry none. The question
  `explanation` gives the reasoning for the key and why the tempting
  distractors fail.
- The exam guide is revised often and names new services (Amazon Bedrock
  AgentCore, Kiro, Amazon Quick, MCP). Check the current domain pages
  before writing an item on a newly listed service, and don't rely on older
  study material.
- Keep the domain mix close to the blueprint weights (20/24/28/14/14) as
  the bank grows.

## Before a PR

- Validator green, run from the engine on Node 22:
  `mise exec node@22 -- npx --yes quizmill@latest validate .`
  (or `npm run pack:validate -- <path>` in a `quizmill/quizmill` checkout).
  Quote its output in the PR.
- `quizmill/admin` evals lint clean of errors:
  `node src/lint.ts <this-dir> --strict` from `evals/`.
- **No screenshots, PNGs, build output or other generated files** in this
  repo. Describe how the engine renders a change in a sentence instead.
