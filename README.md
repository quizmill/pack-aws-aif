# pack-aws-aif — a quizmill learning pack

Practice for the **AWS Certified AI Practitioner (AIF-C01)** exam
(65 questions, 90 min, pass 700/1000, scaled): AI and ML fundamentals,
generative AI, applications of foundation models, responsible AI, and
security, compliance and governance for AI on AWS, across the Easy, Hard
and Very hard tiers. 200 questions and 52 concept cards.

Live at <https://aws-aif.quizmill.dev>.

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

The 52 concept cards in `concepts.json` (Bedrock, prompt engineering, RAG,
Guardrails, agents, SageMaker AI, the governance services and more) were
written the same way; each question links to one by `conceptId`.

## Categories & tiers

The categories are the exam guide's five content domains, with its
weights. The bank follows the blueprint mix exactly:

| Domain | Weight | Questions (Easy / Hard / Very hard) |
| --- | --- | --- |
| 1 · Fundamentals of AI and ML | 20% | 40 (16 / 16 / 8) |
| 2 · Fundamentals of Generative AI | 24% | 48 (19 / 19 / 10) |
| 3 · Applications of Foundation Models | 28% | 56 (22 / 22 / 12) |
| 4 · Guidelines for Responsible AI | 14% | 28 (11 / 11 / 6) |
| 5 · Security, Compliance, and Governance for AI Solutions | 14% | 28 (11 / 11 / 6) |
| **Total** | | **200 (79 / 79 / 42)** |

- **Every task statement.** All 14 of the guide's tasks (1.1 – 5.2) have
  questions, tagged `task-N.N`.
- **Both answer formats.** 16 of the 200 are "Select TWO".

## Quality bar

The whole bank passes the quizmill quality gate (`quizmill/admin` evals,
judged on `claude-fable-5-1`, rubric v1): every question is solved blind
and its key confirmed, the options are judged on their own for giveaways,
and each item is reviewed against the item-writing rubric. Result over all
200 questions: 0 fatal, 0 major, 0 keys not confirmed, 0 solve
disagreements, minor flaws on 1% (ceiling 10%), and lint clean of errors.

## Use it

Open <https://aws-aif.quizmill.dev>, or add it to any quizmill app from
the pack library (it is listed in the quizmill pack registry as
`aws-aif`). From the command line:

```
npx quizmill run quizmill/pack-aws-aif   # straight from GitHub
npx quizmill run .        # http://localhost:3000
npx quizmill validate .   # schema + cross-reference checks
```

`.github/workflows/deploy.yml` builds the pack onto the quizmill engine
(static app in `aws-aif-app/`, named after the manifest id) and publishes
it to Cloudflare Pages (project `aws-aif`, custom domain
`aws-aif.quizmill.dev`) on every push to `main` and daily. `.github/workflows/ci.yml` validates every PR.
