# Advisor Intelligence Workflow

**From client documents to an advisor-approved financial plan**

Advisor Intelligence Workflow is an integrated, human-supervised AI product
that connects:

- **Document Review Agent (DRA):** extracts, normalizes, protects, and reconciles facts from financial documents into a canonical household profile.
- **ArchitectAI:** validates the approved profile, calculates an authoritative
  financial snapshot, retrieves topic-specific CFP knowledge, and generates a
  grounded financial-plan draft for advisor review.

The system is designed around privacy, explicit uncertainty, human approval,
structured handoffs, retrieval-augmented generation, deterministic
calculations, and model-independent plan generation.

## Repository Scope

The underlying Document Review Agent and ArchitectAI application repositories
are private. This public repository documents the integrated product
architecture, design decisions, evaluation approach, fictional demonstration
workflow, and resulting product evidence without exposing proprietary source
code, prompts, or planning-knowledge materials.

## Product Thesis

> The language model interprets and communicates. The application validates
> and calculates. The advisor resolves uncertainty and approves the result.

Instead of sending raw documents directly into a planning prompt, the workflow
creates a versioned canonical household profile. Material uncertainty is
resolved before approved facts and retrieved planning knowledge are combined
to draft the financial plan.

## Demonstrated Workflow

The flagship Golden Client 2 case moves eleven fictional documents through:

1. Local parsing, PII protection, and structured extraction
2. Cross-document reconciliation and canonical profile construction
3. Human classification of deposits, asset overlap, and planning gaps
4. Approved-profile handoff between applications
5. Deterministic calculation of core household totals
6. Topic-specific financial-planning knowledge retrieval
7. Guarded local-model generation and advisor review
8. Local PDF creation

The final approved snapshot contains \$1,364,400 in listed financial accounts
and a calculated net worth of \$1,731,900. These are fictional demonstration
figures, not client data.

## Product Walkthrough

### 1. Build a Governed Household Profile

![Document Review Agent canonical profile summary](screenshots/dra_canonical_profile_summary.png)

Document Review Agent produces a schema-versioned profile from eleven
fictional source documents, keeps material review requirements visible, and
blocks cloud processing when protected PII is present.

### 2. Resolve Ambiguity Before Generation

![ArchitectAI profile review](screenshots/architectai_profile_review.png)

The advisor confirms household facts, resolves overlapping asset totals,
classifies ambiguous deposits, and acknowledges material planning gaps before
the profile can be approved.

### 3. Generate From Approved Facts

![ArchitectAI authoritative financial snapshot](screenshots/architectai_financial_snapshot.png)

ArchitectAI calculates core financial totals from the approved profile in
application code. The model explains those values and combines them with
retrieved planning knowledge without replacing the authoritative snapshot.

## Package Contents

- [`case-study/CASE_STUDY.md`](case-study/CASE_STUDY.md): recruiter-facing case study
- [`architecture/SYSTEM_ARCHITECTURE.md`](architecture/SYSTEM_ARCHITECTURE.md): system boundaries and workflow
- [`demo/GOLDEN_CLIENT_2.md`](demo/GOLDEN_CLIENT_2.md): fictional demonstration scenario
- [`evidence/EVALUATION_RESULTS.md`](evidence/EVALUATION_RESULTS.md): evaluation methods and results
- [`evidence/golden_client_2_summary.html`](evidence/golden_client_2_summary.html): visual benchmark summary
- [`screenshots/`](screenshots/): product workflow and generated-plan evidence

## Portfolio Positioning

> An advisor-controlled AI workflow that transforms heterogeneous financial
> documents into a verified household profile and uses approved facts plus
> retrieved planning knowledge to generate a grounded financial-plan draft.

## Current Boundary

This is a working product prototype and portfolio case study, not a production
financial-advice service. Commercial deployment would require broader
evaluation, enterprise security and records controls, regulatory knowledge
governance, integrations, and measured user validation.

## Privacy

All demonstration materials must use fictional data. Real financial records,
secrets, licensed reference documents, local model files, and generated
outputs containing real client information must not be committed.
