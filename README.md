# pack-aws-aif — a quizmill learning pack

Practice for the **AWS Certified AI Practitioner (AIF-C01)** exam
(65 questions, 90 min, pass 700/1000, scaled): AI and ML fundamentals,
generative AI, applications of foundation models, responsible AI, and
security, compliance and governance for AI on AWS, across the Easy, Hard
and Very hard tiers.

> **Unofficial.** Not affiliated with or endorsed by AWS. This is community
> study material — every question is `reviewStatus: "draft"`; cross-check
> against the AWS docs and the official practice set.

## Where the questions come from

Every question is **original** (`source: "original"`), written for this
pack from the public AWS documentation and the official exam guide — no
community banks, official practice questions or dumps. Each one's
`sourceRef` is the AWS doc page it rests on, and its explanation ends with
a "Read more" link to it. Every distractor carries a one-line note saying
why it is wrong, shown under it once the answer is checked. See
[`NOTICE.md`](NOTICE.md).

The 30 concept cards in `concepts.json` (Bedrock, prompt engineering, RAG,
Guardrails, SageMaker AI, the governance services and more) were written
the same way; each question links to one by `conceptId`.

## Categories & tiers

The categories are the exam guide's five content domains, with its
weights. The seed bank has 12 questions per domain:

| Domain | Weight | Questions (Easy / Hard / Very hard) |
| --- | --- | --- |
| 1 · Fundamentals of AI and ML | 20% | 12 (5 / 5 / 2) |
| 2 · Fundamentals of Generative AI | 24% | 12 (5 / 5 / 2) |
| 3 · Applications of Foundation Models | 28% | 12 (3 / 7 / 2) |
| 4 · Guidelines for Responsible AI | 14% | 12 (4 / 6 / 2) |
| 5 · Security, Compliance, and Governance for AI Solutions | 14% | 12 (3 / 5 / 4) |
| **Total** | | **60 (20 / 28 / 12)** |

- **Every task statement.** All 14 of the guide's tasks (1.1 – 5.2) have at
  least one question, tagged `task-N.N`.
- **Both answer formats.** Five of the 60 are "Select TWO".
- Even domains for now; the manifest's weights let the app's readiness
  estimate weight each domain by the blueprint, and new questions will
  bring the bank's own mix toward 20/24/28/14/14.

## Use it

```
npx quizmill run quizmill/pack-aws-aif   # straight from GitHub
npx quizmill run .        # http://localhost:3000
npx quizmill validate .   # schema + cross-reference checks
```

To deploy as its own app, `.github/workflows/deploy.yml` builds it onto the
quizmill engine (static app in `aws-aif-app/`, named after the manifest id)
and publishes to Cloudflare Pages (project `aws-aif`) once the repo's
`CLOUDFLARE_*` secrets are set. `.github/workflows/ci.yml` validates every
PR.
