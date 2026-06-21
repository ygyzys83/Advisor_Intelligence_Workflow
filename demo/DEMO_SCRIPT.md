# Five-Minute Demo Script

## Objective

Demonstrate how Advisor Intelligence Workflow turns a complex fictional
household's documents into an advisor-approved financial plan while preserving
privacy controls and human judgment.

## Opening - 30 Seconds

"Financial planning does not begin with a clean data set. Client facts are
spread across statements, policies, debt records, estate documents, and
planning notes. Advisor Intelligence Workflow turns those documents into an
approved household profile and then uses that profile to generate a grounded
financial-plan draft.

The key design principle is simple: the model interprets and communicates, the
application validates and calculates, and the advisor resolves uncertainty and
approves the result."

## Document Review Agent - 90 Seconds

1. Show the eleven fictional Golden Client 2 documents.
2. Upload them in Document Review Agent and start canonical-profile creation.
3. Explain while processing:
   - Documents are classified and parsed locally.
   - Microsoft Presidio and domain-specific rules detect and redact PII.
   - Structured schemas constrain the extraction output.
   - Facts are reconciled across documents rather than summarized independently.
4. Show the resulting profile:
   - Household facts and goals
   - Accounts and liabilities
   - Insurance and estate information
   - Sanitized source references
   - Planning gaps and cloud-processing decision

Narration:

"The output is not yet advice. It is a versioned household data contract. Raw
document text is excluded, source filenames are sanitized, and unresolved
questions remain visible."

## Profile Review and Approval - 90 Seconds

Import the canonical profile into ArchitectAI and open the review panel.

Demonstrate these decisions:

- Use listed accounts rather than the overlapping aggregate asset total
- Classify \$5,000 and \$7,500 deposits as transfers
- Classify the \$3,200 deposit as a refund
- Confirm current age and retirement age
- Acknowledge debt, beneficiary, trust-funding, and asset-overlap gaps

Narration:

"These are deliberately human decisions. The amount of a deposit does not tell
us whether it is income, a transfer, or a refund. The application records the
resolution separately, preserves the imported profile, and prevents generation
until material review items are handled."

Show the frozen authoritative snapshot:

- \$270,000 annual income
- \$150,000 annual expenses
- \$1,364,400 listed financial accounts
- \$412,500 liabilities
- \$1,731,900 calculated net worth

## ArchitectAI Plan Generation - 90 Seconds

Start local plan generation.

Explain the two grounding paths:

1. Approved client facts come from the canonical profile and authoritative
   snapshot.
2. Planning knowledge is retrieved by topic from a separate Chroma vector store.

Narration:

"ArchitectAI retrieves relevant CFP context for each selected section, but
retrieved knowledge cannot overwrite approved client facts. Core totals are
calculated in code, while the local model drafts explanations and
recommendations."

Show the completed plan and briefly open:

- Plan basis and assumptions
- Client profile and goals
- One planning section
- Consolidated recommendations
- Illustrative charts
- Final PDF

## Evaluation Evidence and Closing - 30 Seconds

Open the Golden Client 2 evaluation evidence and show:

- DRA: 100% facts, semantics, and safety checks
- ArchitectAI: 100% planning-input, semantics, and safety checks
- 183 combined automated tests across both applications
- Deliberate regression tests for asset double-counting, PII leakage,
  incorrect net worth, and unsafe cloud-processing state

Narration:

"The final review confirmed that approved totals remained consistent,
statement transfers were not converted into income, internal evidence IDs did
not leak into client prose, and unsupported legal, tax, and investment claims
were qualified or removed.

The flagship household is also a repeatable acceptance benchmark. The
deterministic test begins with a frozen canonical profile so CI can verify the
same facts, review decisions, calculations, and privacy contracts on every
change. Live extraction of all eleven documents remains a separate
model-dependent evaluation.

This is a working prototype, not a production advice service. The next product
priorities are broader household and document diversity, RAG quality
measurement, versioned regulatory rules, advisor-facing provenance, and
enterprise security controls."

## Recording Checklist

- [ ] Use only fictional Golden Client 2 materials
- [ ] Close unrelated applications and browser tabs
- [ ] Hide local usernames and private paths where practical
- [ ] Preload local models
- [ ] Confirm both applications start cleanly
- [ ] Rehearse all review decisions
- [ ] Keep the final recording between four and six minutes
- [ ] Show the final PDF briefly
- [ ] End with both Golden Client 2 benchmark reports and known limitations
