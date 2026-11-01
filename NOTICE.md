# Notices

## Original questions

Every question in this pack has `source: "original"` (ids
`aws-aif-<tier>-d<domain>-<n>`). They were written for this pack and are
not derived from any community question bank, from AWS's official practice
questions or Official Pretest, or from any third-party practice exam or
"dump". Each one is grounded in the public AWS documentation page named in
its `sourceRef`; the AWS docs are cited, not reproduced.

The concept cards in `concepts.json` were written for this pack in the same
way, each ending with a link to the AWS page it summarizes.

## Exam blueprint

The manifest's `exam` block and category weights come from the official
exam guide and certification page, checked on 2026-11-01:

- **AWS Certified AI Practitioner (AIF-C01) exam guide**
  <https://docs.aws.amazon.com/aws-certification/latest/ai-practitioner-01/ai-practitioner-01.html>
  - "The exam includes 50 questions that affect your score." and "The exam
    includes 15 unscored questions that do not affect your score." —
    65 questions in total (`exam.questionCount: 65`).
  - "Your results for the exam are reported as a scaled score of
    100–1,000." and "The minimum passing score is 700." — `exam.passPct: 70`
    with `exam.scaled: true` (the raw-to-scaled mapping is not public, so
    the app's readiness estimate is a raw-accuracy target, not a scaled
    score).
  - Content domains, used as this pack's categories with their weights:
    Domain 1 Fundamentals of AI and ML (20% of scored content), Domain 2
    Fundamentals of GenAI (24%), Domain 3 Applications of Foundation Models
    (28%), Domain 4 Guidelines for Responsible AI (14%), Domain 5 Security,
    Compliance, and Governance for AI Solutions (14%).
  - Each question's `task-N.N` tag is the guide's task statement it
    exercises (Task 1.1 "Explain basic AI concepts and terminologies"
    through Task 5.2 "Recognize governance and compliance regulations for
    AI systems"), read from the guide's domain pages
    (`ai-practitioner-01-domain1.html` … `ai-practitioner-01-domain5.html`).
- **AWS Certified AI Practitioner certification page**
  <https://aws.amazon.com/certification/certified-ai-practitioner/>
  - "Exam duration 90 minutes" (`exam.durationMinutes: 90`; the exam guide
    itself does not state a duration) and "Exam format 65 questions".

## Not included

No AWS-copyrighted material is included in this pack. AWS Skill Builder's
official practice questions, the Official Pretest, and any commercial
question banks are proprietary and are **not** redistributed here. Study
those directly on AWS Skill Builder — they are the authoritative source.

AWS and the AWS certification names are trademarks of Amazon.com, Inc. or
its affiliates. This pack is unofficial and not affiliated with or endorsed
by AWS.
