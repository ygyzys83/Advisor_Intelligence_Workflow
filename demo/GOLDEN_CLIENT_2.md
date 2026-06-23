# Golden Client 2

## Purpose

Golden Client 2 is the flagship fictional evaluation and demonstration case for the complete workflow.

## Household

Complex married household with multiple account types, debts, insurance
coverage, estate documents, cash-flow information, executive compensation,
business ownership, and long-term goals.

## Source Documents

Eleven fictional documents covering:

- Checking and savings
- Employer retirement plans
- Taxable brokerage assets
- Mortgage
- Credit-card debt
- Life insurance
- Living trust and estate information
- Financial-planning facts and goals
- Restricted stock and deferred compensation
- A 20% business ownership interest and \$75,000 personal guarantee

## Expected Authoritative Snapshot

- Annual household income: **\$270,000**
- Monthly expenses: **\$12,500**
- Listed financial accounts: **\$1,364,400**
- Home value: **\$780,000**
- Total liabilities: **\$412,500**
- Home equity: **\$382,000**
- Calculated net worth: **\$1,731,900**
- Annual cash-flow surplus: **\$120,000**

## Human Review Decisions

- Ignore overlapping reported asset total and use listed accounts
- Classify the \$5,000 and \$7,500 deposits as transfers
- Classify the \$3,200 deposit as a refund or reimbursement
- Preserve payroll deposits as income evidence without annualizing them
- Confirm current and retirement ages
- Acknowledge material insurance, estate, debt, and account-overlap warnings

## Demonstrated Result

The exercised end-to-end workflow produced:

- A schema-versioned canonical profile
- An explicit advisor-resolution overlay
- An approved authoritative snapshot
- Topic-specific retrieval from the CFP knowledge base
- A guarded financial-plan draft
- A readable 17-page PDF
- Fact-triggered executive and entrepreneur specialty retrieval

Golden Client 2 is also a repeatable automated acceptance case. Document
Review Agent scores the frozen canonical profile against expected household
facts, reconciliation semantics, and privacy requirements. ArchitectAI then
applies the expected human resolutions and scores the approved handoff,
authoritative calculations, and safety state.

Both stages currently score 100% across their defined checks using benchmark
version `2.1.0` and canonical profile schema `1.4.0`. The automated
case starts from the frozen canonical profile; live extraction of all eleven
documents remains a separate local-model evaluation.

The benchmark also confirms that the structured profile preserves a chief
financial officer role, a managing-partner role, \$240,000 of restricted
stock, deferred compensation, a 20% business interest valued at \$350,000, and
a \$75,000 personal guarantee. ArchitectAI activates specialty retrieval from
those approved facts rather than from generated recommendations.

Benchmark reports:

- [`../evidence/golden_client_2_dra_report.json`](../evidence/golden_client_2_dra_report.json)
- [`../evidence/golden_client_2_architectai_report.json`](../evidence/golden_client_2_architectai_report.json)

## Privacy

Every person, institution, account, policy, and document in this scenario is
fictional. Public artifacts must not include real financial records or local
paths.
