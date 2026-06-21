# Evaluation Results

## Evaluation Philosophy

The system is evaluated at multiple layers rather than treating a plausible final narrative as proof of correctness.

## Evaluation Layers

1. Document parsing and classification
2. PII detection and redaction
3. Structured extraction
4. Canonical profile mapping
5. Cross-document reconciliation
6. Schema validation
7. Human review and approval
8. Plan factual grounding
9. Language and regulatory guardrails
10. PDF presentation

## Automated Test Evidence

Both component repositories run automated tests through GitHub Actions on
Python 3.12.

Verified locally on June 21, 2026:

| Application | Result | Runtime |
|---|---:|---:|
| Document Review Agent | 142 passed, 1 warning | 2.33 seconds |
| ArchitectAI | 41 passed, 2 warnings | 6.27 seconds |
| **Combined** | **183 passed** | **8.60 seconds** |

The warnings did not fail either test suite. Warning details should be reviewed
again before publication and after dependency upgrades.

Coverage includes:

- **Document Review Agent:** parsing, extraction, PII policy, profile mapping,
  export contracts, shared schemas, and golden evaluation
- **ArchitectAI:** profile import, schema validation, resolution overlays,
  approved snapshots, deterministic planning inputs, plan guardrails, PDF
  output, and golden handoff

Both repositories also run their test suites through GitHub Actions on pushes
and pull requests to the main branches. Public CI links will be added when the
portfolio package is published.

## Golden Cases

### Golden Client 1

Golden Client 1 uses a fictional financial plan and bank statement. The saved
DRA report passes every expected fact, semantic, and safety check. The saved
ArchitectAI handoff report also passes every planning-input, semantic, and
safety check.

Latest saved benchmark scores:

| Stage | Overall | Facts or planning inputs | Semantics | Safety |
|---|---:|---:|---:|---:|
| Document Review Agent | 100% | 100% | 100% | 100% |
| ArchitectAI handoff | 100% | 100% | 100% | 100% |

Validated behavior includes:

- Correct household planning values
- Separation of verified income from an unclassified deposit
- Preservation and resolution of asset overlap
- Prevention of transfer annualization
- Unsupported high-interest claims remaining absent without rate evidence
- Cloud processing remaining blocked
- Sanitized source references
- Forbidden PII strings remaining absent

### Golden Client 2

Golden Client 2 uses eleven fictional documents for a complex married
household. Its saved canonical profile and approved-profile handoff now have
repeatable automated acceptance benchmarks covering repeated monthly
accounts, transfers, a tax refund, overlapping asset totals, explicit
high-interest debt, insurance-beneficiary issues, and trust-funding review.

The approved snapshot contains:

- \$270,000 annual household income
- \$150,000 annual expenses
- \$1,364,400 in listed financial accounts
- \$412,500 in liabilities
- \$1,731,900 calculated net worth

The final plan preserved approved values, kept transfers out of income,
qualified unsupported legal and tax language, removed internal evidence
artifacts, and rendered as a readable 17-page PDF.

Both benchmark stages currently score 100% across their defined fact or
planning-input, semantic, and safety checks. Regression tests intentionally
alter asset balances, net worth, PII, and cloud-safety state to confirm that
the benchmark fails when these contracts are violated.

Machine-readable reports:

- [`golden_client_2_dra_report.json`](golden_client_2_dra_report.json)
- [`golden_client_2_architectai_report.json`](golden_client_2_architectai_report.json)
- [`golden_client_2_summary.html`](golden_client_2_summary.html), a
  recruiter-friendly visual summary of the benchmark

The deterministic benchmark begins with the frozen canonical profile. Running
all eleven source documents through a live local model remains a separate,
model-dependent evaluation rather than a CI requirement.

## Failures That Improved the Product

- Legal jurisdictions were initially classified as personal locations.
- Repeated names and grouped bank-account numbers escaped early redaction.
- Statement deposits were initially interpreted as income.
- Aggregate asset totals could overlap with separately listed accounts.
- High-interest risk language was inferred without rate evidence.
- Redaction placeholders appeared in account names and summaries.
- Internal evidence identifiers appeared in client-facing plans.
- RMD and beneficiary language exposed stale or overbroad model knowledge.

Each failure produced a domain rule, schema change, review requirement,
guardrail, or regression test.

## Known Evaluation Limits

- Benchmark diversity remains limited
- More scanned PDFs and poor OCR cases are needed
- More household structures and document combinations are needed
- Extraction accuracy needs field-level scoring over a larger labeled dataset
- Current results demonstrate workflow quality, not production-grade accuracy
- Retrieval quality does not yet have recall-at-k or expert relevance scoring
- Live extraction of all eleven Golden Client 2 documents is not part of CI

## Interpretation

The passing test count demonstrates regression protection and contract
coverage; it is not a product-accuracy percentage. The 100% golden scores mean
the applications passed every check defined in the current Golden Client 1
and Golden Client 2 benchmarks. They do not imply 100% accuracy across unseen
financial documents.
